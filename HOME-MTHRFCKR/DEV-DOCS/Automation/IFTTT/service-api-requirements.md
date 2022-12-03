## General API requirements

This document specifies how to implement an API for your service according to the IFTTT Service Protocol. It is recommended that you treat this document as a reference and follow the workflow outlined in our [overview](https://ifttt.com/docs).

We also provide an OpenAPI definition file that describes the IFTTT Service API. You can use this file to generate some of your server code. This should save you time and effort implementing your service. See [OpenAPI definition](https://ifttt.com/docs/api_reference#openapi-definition) for more details.

###### HTTPS

The production version of your service API must be served over HTTPS.

###### API URL prefix

Designate an **API URL prefix** for all of your API endpoints in your service configuration.

###### Examples

-   https://api.service.com
-   https://service.com/api

###### Endpoint paths

Endpoints are scoped to the current version of the IFTTT Service Protocol by appending your API URL prefix with `/ifttt/v1` for all requests.

###### Examples

-   {{api\_url\_prefix}}/ifttt/v1/triggers/any\_new\_photo
-   {{api\_url\_prefix}}/ifttt/v1/actions/post\_photo

Use **UTF-8** as the response encoding and support HTTP-level **compression**. Requests from IFTTT to your service API have the following headers:

###### Headers

-   ```
    
    Accept:          application/json
    Accept-Charset:  utf-8
    Accept-Encoding: gzip, deflate
    Content-Type:    application/json
    ```
    

###### HTTP status codes

Use the following set of HTTP response status codes:

| status | Description |
| --- | --- |
| `200` | The request was a success. |
| `400` | There was something wrong with incoming data from IFTTT. Provide an error response body to clarify what went wrong. |
| `401` | IFTTT sent an OAuth2 access token that isn’t valid. |
| `404` | IFTTT is trying to reach a URL that doesn’t exist. |
| `500` | There was an error in your application logic. |
| `503` | Your service is not available at the moment, but IFTTT should try again later. |

###### Response body format

Provide response bodies as **JSON objects**. Success responses have a top-level wrapper object called `data`.

###### Raw body on success

-   `` ``` {   "data": {     // The value of `data` varies, but is typically     // either an object or array     ...   } }  ``` ``
    

Error responses have a top-level `errors` array. Each element of `errors` is an object with a `message` property whose value is a user-friendly error message.

###### Raw body on error

-   ` ``` {   "errors": [     {       "message": "Something went wrong!"     }   ] }  ``` `
    

### Service authentication

If your service requires user authentication, users must connect your service before they can use its Applets.

Service authentication has two steps:

1.  [Authentication flow](https://ifttt.com/docs/api_reference#authentication-flow). This step authorizes IFTTT to make requests to your service API on behalf of the user.
2.  Fetching and storing basic [user information](https://ifttt.com/docs/api_reference#user-information) from your service API.

**Note:** If your service interacts with user data, authentication is required. Trigger/query/action fields designed to circumvent that requirement (ex. a user's API key) will not be approved.

##### Authentication flow

IFTTT’s protocol supports [OAuth2](http://tools.ietf.org/html/rfc6749) authentication, including support for [refresh tokens](https://ifttt.com/docs/api_reference#refresh-tokens) if so desired.

Your service API should use access tokens for authentication _and_ as a source of identity. A single access token should correspond to a single user account or resource owner on your service.

If refresh tokens are used, they must be **non-expiring**. If refresh tokens are not used, access tokens must be **non-expiring**.

###### IFTTT client credentials

When configuring your service, provide IFTTT with a **client ID** and **client secret** for authentication-related requests.

###### Request

To begin authentication, IFTTT redirects the user to your **OAuth2 Authorization URL**, specified in the Service Authentication settings, and makes the following request:

###### Request

-   Method
    
    GET
    
    URL
    
    Your OAuth2 Authorization URL
    

###### Parameters

-   client\_id
    
    IFTTT’s client ID for your service as set in your service configuration.
    
    response\_type
    
    code
    
    scope
    
    ifttt
    
    The ifttt scope should provide access to resources for every trigger and action in your service. This way, users will not need to repeat the authentication flow to use all of your queries, triggers, and actions.
    
    You may override this parameter by specifying your own scope in the OAuth2 Authorization URL specified in the Service Authentication settings.
    
    state
    
    An anti-forgery token provided by IFTTT.
    
    redirect\_uri
    
    `https://ifttt.com/channels/{{service_id}}/authorize`
    
    `service_id` is a string used to represent your service in URLs. You can set in your service configuration.
    
    Though we provide the `redirect_uri` parameter, we encourage you to always use the redirect URL provided in [Authentication settings](https://platform.ifttt.com/mkt/api%2Fauthentication) over simply redirecting users to the parameter’s value.
    

###### Example

-   ```
    https://api.example-service.org/oauth2/authorize?client_id=94b26e58a3a88d5c&response_type=code&redirect_uri=https%3A%2F%2Fifttt.com%2Fchannels%2Fexample_channel%2Fauthorize&scope=ifttt&state=a00caec8dbd08e50
    ```
    

###### Response

After the user is redirected to your authorization request endpoint, you should authenticate the user and prompt to grant IFTTT access to the user’s resources on your service.

###### Authorization grant

Once a user authorizes IFTTT, you should redirect the user to IFTTT’s **channel authorization URL** along with an authorization code which IFTTT can exchange for a bearer token in the next step.

###### Redirect

###### URL

-   `https://ifttt.com/channels/{{service_id}}/authorize`  
    The `service_id` is a string used to represent your service in URLs. You can set it in your service configuration.

###### Parameters

-   code
    
    The authorization code you generated.
    
    state
    
    The anti-forgery token provided by IFTTT in the original request.
    

###### Example

-   ```
    https://ifttt.com/channels/example_channel/authorize?code=67a8ad40341224c1&state=a00caec8dbd08e50
    ```
    

###### User denies IFTTT

Should the user deny IFTTT access to your service, you should redirect them to IFTTT indicating access was denied.

###### Request

-   URL
    
    `https://ifttt.com/channels/{{service_id}}/authorize`  
    `service_id` is a string used to represent your service in URLs. You can set it in your service configuration.
    
    Parameters
    
    `error` access\_denied
    

###### Example

-   ```
    https://ifttt.com/channels/example_channel/authorize?error=access_denied
    ```
    

###### Token exchange

###### Request

After IFTTT has received an authorization code for the user, it will make a `POST` request to your **OAuth2 Token URL**, specified in the Service Authentication settings, and exchange the code for an access token.

###### Body Parameters

-   grant\_type
    
    authorization\_code
    
    code
    
    The authorization code generated earlier in this flow.
    
    client\_id
    
    IFTTT’s client ID for your service as set in your service configuration.
    
    client\_secret
    
    IFTTT’s client secret for your service as set in your service configuration.
    
    redirect\_uri
    
    https://ifttt.com/channels/{{service\_id}}/authorize  
    `service_id` is a string used to represent your service in URLs. You can set it in your service configuration.
    

###### Example

-   ```
    
    POST /oauth2/token HTTP/1.1
    Host: api.example-service.com
    Content-Type: application/x-www-form-urlencoded
    
    grant_type=authorization_code&code=67a8ad40341224c1&client_id=83465ab42&client_secret=c4f7defe91df9b23&redirect_uri=https%3A//ifttt.com/channels/service_id/authorize
    ```
    

###### Response

If the authorization code is **valid**, provide the following response:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type application/json; charset=utf-8`
    

###### Body

-   `token_type`
    
    Bearer
    
    `access_token`
    
    A token IFTTT will use to make authenticated calls to your API.
    
    `refresh_token`
    
    (optional) If enabled, refresh token IFTTT will use to refresh access tokens.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "token_type": "Bearer",
      "access_token": "b29a71b4c58c22af116578a6be6402d2"
    }
    ```
    

If the authorization code is **not valid**, respond with a 400 status code and body as shown in the following example:

###### HTTP

-   Status
    
    400
    
    Headers
    
    `Content-Type application/json; charset=utf-8`
    

###### Body

-   `error`
    
    invalid\_grant
    
    `error_description`
    
    (optional) Description of the error. Do not disclose specific tokens or authentication codes here
    

###### Example

-   ```
    
    HTTP/1.1 400 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "error": "invalid_grant",
      "error_description": "The code or token used is not valid"
    }
    ```
    

### Refresh Tokens

You can indicate that your API uses refresh tokens under the “Authentication” tab. IFTTT will continue to use an access token until a 401 is received indicating the token is no longer valid. Once this occurs IFTTT will attempt to obtain a new access token using a refresh token via the [token refresh](https://ifttt.com/docs/api_reference#token-refresh) endpoint before attempting the request again.

Please note that refresh tokens cannot have a time-based expiry. The only time it is technically permissible for a refresh token to expire is after an access token has been refreshed. At that time, it is acceptable to return a new refresh token; however, we require that the previous refresh token not immediately expire.

###### Token refresh

###### Request

After token expiry, IFTTT will make a `POST` request to your **OAuth2 Token Endpoint**, specified in the Service Authentication settings, and use the refresh token to retrieve a new access token.

###### HTTP

-   Method
    
    POST
    
    URL
    
    OAuth2 Token Endpoint
    
    Headers
    
    `Content-Type application/x-www-form-urlencoded`
    

###### Body

-   `grant_type`
    
    refresh\_token
    
    `client_id`
    
    IFTTT’s client ID for your service as set in your service configuration.
    
    `client_secret`
    
    IFTTT’s client secret for your service as set in your service configuration.
    
    `refresh_token`
    
    The refresh token retrieved in the [token exchange](https://ifttt.com/docs/api_reference#token-exchange) step of the [Authentication Flow](https://ifttt.com/docs/api_reference#authentication-flow)
    

###### Example

-   ```
    
    POST /oauth2/token HTTP/1.1
    Host: api.example-service.com
    Content-Type: application/x-www-form-urlencoded
    
    grant_type=refresh_token&client_id=83465ab42&client_secret=c4f7defe91df9b23&refresh_token=c8764378d9879ffeadfcc233effafb23bbdbfe
    ```
    

###### Response

If the refresh token is **valid**, provide the following response:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

###### Body

-   `access_token`
    
    The updated access token.
    
    `refresh_token`
    
    The updated refresh token.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "access_token": "c547cdfecf7e86cde678bc87de6fc87",
      "refresh_token": "d7676beda76c38762349bac98cba799"
    }
    ```
    

If the refresh token is **not valid**, respond with a 400 status code and body as shown in the following example:

###### HTTP

-   Status
    
    400
    
    Headers
    
    `Content-Type application/json; charset=utf-8`
    

###### Body

-   `error`
    
    invalid\_grant
    
    `error_description`
    
    (optional) Description of the error. Do not disclose specific tokens or authentication codes here
    

###### Example

-   ```
    
    HTTP/1.1 400 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "error": "invalid_grant",
      "error_description": "The code or token used is not valid"
    }
    ```
    

### User information

###### Request

After acquiring an access token, IFTTT will make a request to your **user information endpoint**. This information is considered private, and will only be displayed to the user who activated your service.

Occasionally, IFTTT will make requests to this endpoint to verify that the user’s access token is still valid.

###### HTTP

-   Method
    
    GET
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/user/info`
    
    Headers
    
    ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Example

-   ```
    
    GET /ifttt/v1/user/info HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: 434d757081c94013b1b28f2087d28a98
    ```
    

###### Response

Requests to the user information endpoint should generate the following response:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

The body of the response is a JSON object with one top-level field, `data`, with three fields:

###### Body

-   `name`
    
    (string) Full name, username, email, or other identification to display to the user.
    
    `id`
    
    (string) An unchangeable, permanent identifier to uniquely identify the resource owner within your service. We advise against using access tokens, emails, usernames, or phone numbers for this as the identifier cannot be changed. \*\*Up to 200 characters.\*\*
    
    `url`
    
    (optional string) URL to user’s dashboard or configuration page on your service’s website.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": {
        "name": "Walter White",
        "id": "heisenberg",
        "url": "http://example.com/users/heisenberg"
      }
    }
    ```
    

As with all other endpoints which require authentication via access token, you should return a [401 status](https://ifttt.com/docs/api_reference#http-status-codes) to indicate that the access token is invalid or expired.

### Triggers

Each trigger requires a unique API endpoint. For each Applet using a given trigger, IFTTT will poll that trigger’s endpoint once about every hour. For each **new** item returned by the trigger, IFTTT will fire the Applet’s associated action.

**Note**: To ensure a great Applet experience for your users, triggers are required to use the [Realtime API](https://ifttt.com/docs/api_reference#realtime-api) if a user would expect its Applets to run in realtime.

A trigger endpoint should return (by default) the 50 most recent _events_, regardless of whether or not we have seen them before. The number of returned items can be overridden by IFTTT when a `limit` parameter is present in the request. Please do not limit the number of events returned except as specified by the `limit` parameter in the request. Events should remain on the timeline indefinitely and should not expire, although they may roll off the bottom of the list once the timeline exceeds 50 items.

###### Request

To fetch new items IFTTT will make the following request to your **trigger endpoints**:

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/triggers/{{trigger_slug}}`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: {{random_uuid}}
    ```
    

###### Body

-   `trigger_identity`
    
    (string) A unique identifier for this set of trigger fields for a given Applet (see [Trigger Identity](https://ifttt.com/docs/api_reference#trigger-identity)).
    
    `triggerFields`
    
    (object) Map of trigger field slugs to values.
    
    `limit`
    
    (optional integer) Maximum number of items to be returned, default 50.
    
    `user`
    
    (object) Information about the IFTTT user related to this request.
    
    `ifttt_source`
    
    (optional object) Information about the personal Applet on IFTTT that triggered this request. If present, this will have an id uniquely identifying the Applet and a url pointing to a web page describing it. Note that only the user will be able to see this page, since personal Applets are private. In the future, these fields may point to an entity other than a personal Applet.
    

This example excludes the optional limit parameter. Only the 50 most recent items should be returned, in descending chronological order.

###### EXAMPLE: default limit

-   ```
    
    POST /ifttt/v1/triggers/new_photo_in_album_with_hashtag HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 7f7cd9e0d8154531bbf36da8fe24b449
    
    {
      "trigger_identity": "92429d82a41e93048",
      "triggerFields": {
        "album_name": "Street Art",
        "hashtag": "banksy"
      },
      "ifttt_source": {
        "id": "2",
        "url": "https://ifttt.com/myrecipes/personal/2"
      },
      "user": {
        "timezone": "America/Los_Angeles"
      }
    }
    ```
    

This example provides the limit parameter.

###### EXAMPLE: explicit limit

-   ```
    
    POST /ifttt/v1/triggers/new_photo_in_album_with_hashtag HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 7f7cd9e0d8154531bbf36da8fe24b449
    
    {
      "triggerFields": {
        "album_name": "Street Art",
        "hashtag": "banksy"
      },
      "limit": 10,
      "ifttt_source": {
        "id": "2",
        "url": "https://ifttt.com/myrecipes/personal/2"
      },
      "user": {
        "timezone": "America/Los_Angeles"
      }
    }
    ```
    

###### Response

Responses contain an array of item objects. Items are **a stream of unique events on a timeline**, and each item has:

-   One field for every [ingredient](https://ifttt.com/docs/api_reference#ingredients) in the trigger.
-   A **unique identifier** used to prevent Applets from firing more than once on the same item.
-   A **timestamp** in Unix seconds. Items in the stream must be in **descending** order by the timestamp.

Responses should be structured as follows:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type application/json; charset=utf-8`
    

For the Body you get a JSON object which contains an array, data, of item objects. Items have one key-value pair for each ingredient slug and value, and a meta object with two fields:

###### BODY

-   ```
    
      "data": [
        {
          "slug 1": "value for ingredient 1",
          "slug 2": "value for ingredient 2",
          ...
          "slug n": "value for ingredient n",
          "meta": {
            "id": "14b9-1fd2-acaa-5df5", //(string) a unique identifier for the item.
            "timestamp": 1383597267 // (integer) a Unix timestamp in seconds.
          }
        }
      ]
    ```
    

###### Response Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "image_url": "http://example.com/images/128",
          "tags": "banksy, brooklyn",
          "posted_at": "2013-11-04T09:23:00-07:00",
          "meta": {
            "id": "14b9-1fd2-acaa-5df5",
            "timestamp": 1383597267
          }
        },
        {
          "image_url": "http://example.com/images/125",
          "tags": "banksy, nyc",
          "posted_at": "2013-11-04T03:23:00-07:00",
          "meta": {
            "id": "ffb27-a63e-18e0-18ad",
            "timestamp": 1383596355
          }
        }
      ]
    }
    ```
    

### Trigger Identity

A `trigger_identity` field is sent when an Applet is enabled and then with every subsequent trigger endpoint request. The `trigger_identity` can be thought of as a unique signature of a specific user, trigger, and trigger fields. You should recieve a trigger check request with a `trigger_identity` in the first minute after an Applet is enabled.

For example, if a user has multiple Applets with the same trigger fields/values they will each have the same `trigger_identity`. We recommend that your service stores the relationship between a `trigger_identity` and the specific user, trigger, and trigger fields to assist in troubleshooting.

Note that this field can safely be ignored. However, it becomes powerful when used to notify your API that a user no longer has any Applets with a given `trigger_identity`.

###### Example

Consider the following hypothetical publish/subscribe scenario for a connected car product:

1.  A user creates an Applet (or many Applets) that trigger on “Check Engine Light”.
2.  The trigger endpoint is immediately called and the API stores the `trigger_identity` for that user and associates that value with a “Check Engine Light” event on their vehicle.
3.  The API notifies the vehicle that it wants to subscribe to “Check Engine Light” events and the vehicle begins sending this data to the cloud.
4.  At some point in the future, a user deletes or updates their Applet(s) such that they no longer have any Applets that trigger on the event “Check Engine Light”.
5.  IFTTT calls the `DELETE` endpoint (example below).
6.  The API does a lookup on `trigger_identity` for that user and notifies the associated vehicle to stop sending “Check Engine Light” events.
7.  The API may then clean up or remove the storage of all the events associated with “Check Engine Light” for that user.

###### Request

###### HTTP

-   Method
    
    DELETE
    
    URL
    
    ```
    {{api_url_prefix}}/ifttt/v1/triggers/{{trigger_slug}}/trigger_identity/{{trigger_identity}}
    ```
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: {{random_uuid}}
    ```
    

###### Example

-   ```
    
    DELETE /ifttt/v1/triggers/new_photo_in_album_with_hashtag/trigger_identity/92429d82a41e93048 HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 7f7cd9e0d8154531bbf36da8fe24b449
    ```
    

###### Response

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    ```
    

### Realtime API

With IFTTT’s Realtime API, you can have Applets involving user-oriented triggers from your service run near-instantly. Simply write a hook to notify IFTTT of any changes related to a given user which would correspond to a trigger they **may** be using. Rather than sending data directly, the Realtime API is used to _notify_ IFTTT that there are new events available at your service for a specific `user_id` or `trigger_identity` that we can then fetch through polling.

If your API does not support user authentication you can still leverage the Realtime API by relying on trigger identities alone.

**Note:** You still should return the `limit` (50 by default) number of most recent _events_, not just the ones related to the Realtime notification you sent, regardless of whether or not we have seen them before.

If you are utilizing the Realtime API, we will limit the load on your service by performing trigger checks less frequently.

Note that you will be able to tell that a trigger was checked by a Realtime notification by the presence of the `X-IFTTT-Realtime: 1` header in the trigger check request.

###### Request

You can find your Service Key under the “Details” tab. Include it in your `IFTTT-Service-Key` header to immediately start making Realtime requests.

We also recommend that you send an `X-Request-ID` header with a UUID. Should the need to debug arise in the future, this will help reconcile server logs.

###### HTTP

-   Method
    
    POST
    
    URL
    
    `https://realtime.ifttt.com/v1/notifications`
    

###### Headers

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: {{random_uuid}}
    ```
    

A JSON object which contains an array, `data`, of objects which each have a `user_id` or `trigger_identity`:

###### Body

-   data\[user\_id\]
    
    (string) The same id for the user that is returned by your user information endpoint.
    
    data\[trigger\_identity\]
    
    (string) A unique identifier for a given set of trigger fields, sent to your API with every trigger endpoint request.
    

**Using `trigger_identity` will improve the performance of your integration with IFTTT**. When the IFTTT Realtime API receives a `user_id` each of that user's triggers must be polled for, even though likely only a few of them have fresh data. For example, if a user had 100 Applets using your service's triggers, when that `user_id` is sent to the Realtime API IFTTT will need to run 100 checks for fresh data. This is a lot of extra time spent processing for both you and IFTTT, and reducing this time means your users' Applets will run faster. By using `trigger_identity`, IFTTT can poll your service for only the relevant fresh data.

The Realtime request can contain up to 1000 user\_ids and/or trigger\_identities, although generally one would send either all `user_id`s or all `trigger_identity`s:

###### Example

-   ```
    
    POST /v1/notifications HTTP/1.1
    Host: realtime.ifttt.com
    IFTTT-Service-Key: WlWFGKXFsXBaFMt8yZ7aLOafdqo7mAhY
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 619fd42930f74b78abc4394ca7bfec5b
    
    {
      "data": [
        {
          "user_id": "23489759"
        },
        {
          "user_id": "77956024"
        },
        {
          "trigger_identity": "c5559d12d393b25c140364d891292e02233933a5"
        },
        ...
      ]
    }
    ```
    

### Trigger fields

Trigger fields can have a [**dynamic validation of a text input**](https://ifttt.com/docs/api_reference#trigger-field-dynamic-validation), [**location-based input**](https://ifttt.com/docs/api_reference#location-based-input), or [**dynamic options via a drop-down**](https://ifttt.com/docs/api_reference#trigger-field-dynamic-options).

With a drop-down, we provide two different choices:

1.  A dynamic drop-down selector. We provide you with a unique API endpoint based on the trigger field's name you can use to dynamically grab the list of options from your server.
2.  A manual drop-down to manually add a list of options that the user can select from.

It is possible to validate all trigger fields using a single unique endpoint using [**contextual validation**](https://ifttt.com/docs/api_reference#trigger-field-contextual-validation).

#### Trigger field dynamic options

##### Dynamic dropdowns

Options have a label, which the user sees, and a value, which is sent when the trigger is executed. If you're using the dynamic drop-down instead of the manual drop-down, options can be placed into categories one level deep. Users may select categorized options but may not select the category itself.

###### Request

For **drop-down selector** trigger fields, you can dynamically provide user-specific options. Each time the drop-down is displayed, IFTTT will fetch a list of options from your trigger field’s **dynamic options endpoint**.

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/triggers/{{trigger_slug}}/fields/{{trigger_field_slug}}/options`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Example

-   ```
    
    POST /ifttt/v1/triggers/new_photo_in_album_with_hashtag/fields/album_name/options HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: 37ccb881af5542fe8c5534e9744b6116
    
    {}
    ```
    

###### Response

Your trigger field’s dynamic options endpoint should generate the following response:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

A JSON object which contains an array, `data`, of option objects:

###### Body

-   label
    
    (string) A user-facing label.
    
    value
    
    (string) The actual field value.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "label": "Street Art",
          "value": "12345"
        },
        {
          "label": "Technology",
          "value": "43245"
        },
        {
          "label": "Animals",
          "values": [
            {
              "label": "Cats",
              "value": "32143"
            },
            {
              "label": "Dogs",
              "value": "51231"
            }
          ]
        }
      ]
    }
    ```
    

##### Dynamic checkboxes

Options have a label, which the user sees, and a value, which is sent when the trigger is executed.

###### Request

For **checkbox** trigger fields, you can dynamically provide user-specific options. Each time the checkbox list is displayed, IFTTT will fetch a list of options from your trigger field’s **dynamic options endpoint**.

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/triggers/{{trigger_slug}}/fields/{{trigger_field_slug}}/options`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Example

-   ```
    
    POST /ifttt/v1/triggers/new_photo_in_album_with_hashtag/fields/album_name/options HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: 37ccb881af5542fe8c5534e9744b6116
    
    {}
    ```
    

###### Response

Your trigger field’s dynamic options endpoint should generate the following response:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

A JSON object which contains an array, `data`, of option objects:

###### Body

-   label
    
    (string) A user-facing label.
    
    value
    
    (string) The actual field value.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "label": "Street Art",
          "value": "12345"
        },
        {
          "label": "Technology",
          "value": "43245"
        },
        {
          "label": "Animals",
          "values": [
            {
              "label": "Cats",
              "value": "32143"
            },
            {
              "label": "Dogs",
              "value": "51231"
            }
          ]
        }
      ]
    }
    ```
    

##### Trigger field dynamic validation

###### Request

For **text** trigger fields, you can dynamically validate user input. IFTTT will make the following request to your service API:

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/triggers/{{trigger_slug}}/fields/{{trigger_field_slug}}/validate`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Body

-   value
    
    (string) User input to be validated
    

###### Example

-   ```
    
    POST /ifttt/v1/triggers/new_photo_in_album_with_hashtag/fields/album_name/validate HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: b959f481ef4f4a8ab0ec414f58991674
    
    {
      "value": "Street Art"
    }
    ```
    

###### Response

Your trigger field’s dynamic validation endpoint should generate the following response:

###### HTTP

-   Status
    
    200, regardless of whether or not the user input is valid
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

For the body you get a JSON object which contains an object, `data`:

###### Body

-   data\[valid\]
    
    (boolean) Validity of user’s input.
    
    data\[message\]
    
    (optional string) Explanation to display to user if input was invalid.
    

###### Example: Valid Input

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": {
        "valid": true
      }
    }
    ```
    

###### Example: Invalid Input

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": {
        "valid": false,
        "message": "Sorry, no album exists with the name \"Street Art\"."
      }
    }
    ```
    

##### Trigger field contextual validation

Contextual Validation allows you to validate a trigger field based on the values of other trigger fields. It is incredibly useful for validating multiple trigger fields in a single API call. Because Contextual Validation is a trigger setting, validation will be available to every trigger field. When Contextual Validation is enabled, all trigger field [**dynamic validation**](https://ifttt.com/docs/api_reference#trigger-field-dynamic-validation) endpoints for the trigger will not be used in favor of the single validate endpoint.

To enable this option for your trigger, please contact support.

###### Request

IFTTT will make the following request to your service API:

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/triggers/{{trigger_slug}}/validate`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Body

-   values
    
    (object) Trigger fields with their values
    

###### Example

-   ```
    
    POST /ifttt/v1/triggers/new_comment_on_card/validate HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: b959f481ef4f4a8ab0ec414f58991674
    
    {
      "values": {
        "board": "New Features",
        "card": "Potential Ideas"
      }
    }
    ```
    

###### Example

The use of contextual validation comes in handy when a trigger field needs to be validated, but the validation depends on another trigger field. Take the following scenario:

1.  The trigger has two trigger fields, `board` and `card`.
2.  The `board` name is unique, and a `card` exists within a `board`. However, cards can have the same name across different boards.
3.  Validating that the `card` exists becomes simple because the value of `board` is known.

If [**dynamic validation**](https://ifttt.com/docs/api_reference#trigger-field-dynamic-validation) is used for the `card` trigger field, it is difficult to know which `card` the user intends to trigger on during validation if the user has multiple `cards` with the same name.

###### Response

Your trigger’s contextual validation endpoint should generate the following response:

###### HTTP

-   Status
    
    200, regardless of whether or not the user input is valid
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

For the body you get a JSON object which contains an object, `data`:

###### Body

-   data
    
    (object) [dynamic validation](https://ifttt.com/docs/api_reference#trigger-field-dynamic-validation) objects for each trigger field.
    

###### Example: Valid Input

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": {
        "board": {
          "valid": true
        },
        "card": {
          "valid": true
        }
      }
    }
    ```
    

###### Example: Invalid Input

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": {
        "board": {
          "valid": true
        },
        "card": {
          "valid": false,
          "message": "Sorry, no card exists with the name \"Potential Ideas\" in the \"New Features\" board."
        }
      }
    }
    ```
    

##### Location-based input

Location-based trigger fields enable users to specify whether Applets should run based on _a point_, _an area_, _entering an area_, _exiting an area_, or _entering or exiting an area_. These fields can be [**dynamically validated**](https://ifttt.com/docs/api_reference#trigger-field-dynamic-validation). Below is an example of how location-based fields are represented.

###### Example

-   ```
    "triggerFields": {
      "location": {
        "lat": 37.783923707779095,
        "lng": -122.40864549999998,
        "radius": 0,
        "address": "923 Market St, San Francisco, CA 94103, USA",
        "description": "923 Market St, San Francisco, CA 94103, USA",
        "zoom": 16
      },
    }
    ```
    

### Applet Templates

When you create a new trigger and define the data the trigger will make available via ingredients, we'll ask you to provide examples of how the trigger would be best used in various categories of actions. These examples should guide users to create powerful Applets more efficiently from helpful defaults instead of empty fields.

Below you'll find helpful tips for each of the action categories:

#### 📱 Mobile push notification tips:

-   Should be friendly and personal! Use 'you' instead of 'my'.
-   Don't make the content too dense. Inform the user of the most important information about the event.
-   Avoid ingredients that point to URLs.

#### 💬 Short message tips:

-   Provide the most important information using ingredients that keep the message contextual to the event.
-   Keep in mind that the message might be truncated based on character restrictions.
-   Include a URL ingredient if one is available.

#### 📜 Long post tips:

-   Use the 'Post body' field to craft a delightful message for users. HTML is accepted, so be sure to add formatting that might enhance the message.
-   Keep in mind that this content is used in email actions, which are widely used. 'Post title' is the subject and 'Post body' is the body of the email.

#### 📃 Plaintext file tips:

-   Plaintext files are great for record keeping. Be sure to use all relevant ingredients in the 'Plaintext body'.
-   If the 'Filename' is static (ex. Saved tracks on Spotify), one document will be created and then appended to for each subsequent event.
-   If the 'Filename' contains a dynamic ingredient (ex. Track saved on `{{SavedAt}}`), a new file will be created with each event because it will have a unique filename.
-   The 'Folder path' specified will be created if it does not yet exist for the user.

#### 📊 Spreadsheet tips:

-   Spreadsheets are great for record keeping. Be sure to use all relevant ingredients.
-   Use ||| to separate cells in a row of a spreadsheet (ex. "`{{Ingredient1}}`|||`{{Ingredient2}}`|||`{{Ingredient3}}`")
-   If you would like to use an image in one of the cells use =IMAGE("`{{ingredient}}`";1).

#### 🗣 Phone call tips:

-   The contents here will be read aloud when the phone call action runs. Keep that in mind when formatting the template.
-   A good starting place for this template is to reference the contents you wrote for the notification template.

#### 📅 Calendar event tips:

-   You need to have at least one timestamp ingredient included in the 'Quick add text' so that the calendar action knows when to create the event.
-   If your trigger produces the start time and end time of the event, be sure to use both ingredients in the template (ex. "Some event occurred from `{{StartTime}}` to `{{EndTime}}`")

### Actions

Each action requires a unique API endpoint.

###### Request

For each new trigger item, IFTTT will push data to your **action endpoint** with the following request structure:

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/actions/{{action_slug}}`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: {{random_uuid}}
    ```
    

###### Body

-   actionFields
    
    (object) Map of action field slugs to values.
    
    user
    
    (object) Information about the IFTTT user related to this request.
    
    ifttt\_source
    
    (optional object) Information about the personal Applet on IFTTT that triggered this request. If present, this will have an id uniquely identifying the Applet and a url pointing to a web page describing it. Note that only the user will be able to see this page, since personal Applets are private. In the future, these fields may point to an entity other than a personal Applet.
    

###### Example

-   ```
    
    POST /ifttt/v1/actions/new_status_update HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 1d21c3cd2ed8441ea269dd554d2c8e54
    
    {
      "actionFields": {
        "title": "New Banksy photo!",
        "body": "Check out a new Bansky photo: http://example.com/images/125"
      },
      "ifttt_source": {
        "id": "2",
        "url": "https://ifttt.com/myrecipes/personal/2"
      },
      "user": {
        "timezone": "America/Los_Angeles"
      }
    }
    ```
    

###### Response

Your action endpoint should generate the response below:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

A JSON object which contains an array, `data`, of a single item object:

###### Body

-   `data[0][id]`
    
    (string) A database ID, timestamp, URL, or other value which uniquely identifies the resource created or modified during action execution.
    
    `data[0][url]`
    
    (optional string) URL to the created or modified resource.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "id": "234325",
          "url": "http://example.com/posts/234325"
        }
      ]
    }
    ```
    

##### Skipping Actions

If an action fails and returns an error, IFTTT will retry several times. If the action continues to fail, the offending event will eventually be skipped. However, the action can specify that a event be skipped immediately by responding with status code 400 and a special error object. It should do this when a event will simply never be successfully processed because it is invalid or unacceptable. For example, a “Post Comment” action may want to skip over any events that have an empty comment. Note that this does not include syntactic errors in the requests or problems beyond just the individual event and its action fields, including authentication.

A “skip” error has a property `status` that must always be set to `"SKIP"`. It should also have a property `message`. This `message` should be a helpful user-facing error message as it may be displayed to users in their logs and elsewhere. 400 responses may have multiple error objects; any additional “SKIP” objects after the first will be ignored.

###### Example

-   ```
    
    HTTP/1.1 400 Bad request
    Content-Type: application/json; charset=utf-8
    
    {
      "errors": [
        {
          "status": "SKIP",
          "message": "Audio file size too big"
        }
      ]
    }
    ```
    

### Action fields

Action fields can be populated via a static text input or a drop-down. Unlike trigger fields, action fields do not currently support dynamic validation.

With a drop-down, we provide two different choices:

1.  A dynamic drop-down selector. We provide you with a unique API endpoint based on the action field's name you can use to dynamically grab the list of options from your server.
2.  A manual drop-down to manually add a list of options that the user can select from.

#### Action field dynamic options

##### Dynamic dropdowns

Options have a label, which the user sees, and a value, which is sent when the action is executed. If you're using the dynamic drop-down instead of the manual drop-down, options can be placed into categories one level deep. Users may select categorized options but may not select the category itself.

###### Request

For action fields using the **dynamic drop-down selector**, you can dynamically provide user-specific options. Each time the action field is displayed, IFTTT will fetch a list of options from your action field’s **dynamic options endpoint**:

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/actions/{{action_slug}}/fields/{{action_field_slug}}/options`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

An empty JSON object

###### Example

-   ```
    
    POST /ifttt/v1/actions/post_photo_to_album/fields/album_name/options HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: 9f99e73452cd40198cb6ce9c1cde83d6
    
    {}
    ```
    

###### Response

Your action field’s dynamic options endpoints should generate the following response:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

For the body you will get a JSON object which contains an array, data, of option objects:

###### Body

-   data\[label\]
    
    (string) A user-facing label.
    
    data\[value\]
    
    (string) The actual field value.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "label": "Street Art",
          "value": "12345"
        },
        {
          "label": "Technology",
          "value": "43245"
        },
        {
          "label": "Animals",
          "values": [
            {
              "label": "Cats",
              "value": "32143"
            },
            {
              "label": "Dogs",
              "value": "51231"
            }
          ]
        }
      ]
    }
    ```
    

##### Dynamic checkboxes

Options have a label, which the user sees, and a value, which is sent when the action is executed.

###### Request

For **checkbox** action fields, you can dynamically provide user-specific options. Each time the checkbox list is displayed, IFTTT will fetch a list of options from your action field’s **dynamic options endpoint**.

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/actions/{{action_slug}}/fields/{{action_field_slug}}/options`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

An empty JSON object

###### Example

-   ```
    
    POST /ifttt/v1/actions/post_photo_to_album/fields/album_name/options HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: 9f99e73452cd40198cb6ce9c1cde83d6
    
    {}
    ```
    

###### Response

Your action field’s dynamic options endpoints should generate the following response:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

For the body you will get a JSON object which contains an array, data, of option objects:

###### Body

-   data\[label\]
    
    (string) A user-facing label.
    
    data\[value\]
    
    (string) The actual field value.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "label": "Street Art",
          "value": "12345"
        },
        {
          "label": "Technology",
          "value": "43245"
        },
        {
          "label": "Animals",
          "values": [
            {
              "label": "Cats",
              "value": "32143"
            },
            {
              "label": "Dogs",
              "value": "51231"
            }
          ]
        }
      ]
    }
    ```
    

### Queries

Each query requires a unique API endpoint.

###### Request

To fetch new query data IFTTT will make the following request to your **query endpoint** with the following request structure:

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/queries/{{query_slug}}`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: {{random_uuid}}
    ```
    

###### Body

-   queryFields
    
    (object) Map of query field slugs to values.
    
    cursor
    
    (optional string) Reference to the next page of the result set.
    
    limit
    
    (optional number) Max number of rows to return in a response, default 50.
    
    include
    
    (optional string array) Ingredient slugs to resolve and include in the query response.
    
    user
    
    (object) Information about the IFTTT user related to this request.
    
    ifttt\_source
    
    (optional object) Information about the personal Applet on IFTTT that triggered this request. If present, this will have an id uniquely identifying the Applet and a url pointing to a web page describing it. Note that only the user will be able to see this page, since personal Applets are private. In the future, these fields may point to an entity other than a personal Applet.
    

###### Example

-   ```
    
    POST /ifttt/v1/queries/list_album_photos HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 1d21c3cd2ed8441ea269dd554d2c8e54
    
    {
      "queryFields": {
        "album_name": "Street Art"
      },
      "ifttt_source": {
        "id": "2",
        "url": "https://ifttt.com/myrecipes/personal/2"
      },
      "user": {
        "timezone": "America/Los_Angeles"
      }
    }
    ```
    

###### Response

Your query endpont should generate the response below:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type application/json; charset=utf-8`
    

###### BODY

-   ```
    
      "data": [
        {
          "slug 1": "value for row 1 ingredient 1",
          "slug 2": "value for row 1 ingredient 2",
          ...
          "slug n": "value for row 1 ingredient n"
        },
        ...
        {
          "slug 1": "value for row n ingredient 1",
          "slug 2": "value for row n ingredient 2",
          ...
          "slug n": "value for row n ingredient n"
        },
      ]
    ```
    

Responses should contain an array of rows. Each row should have one attribute for every ingredient in the query.

###### Response Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "image_url": "http://example.com/images/128",
          "tags": "banksy, brooklyn",
          "posted_at": "2013-11-04T09:23:00-07:00"
        },
        {
          "image_url": "http://example.com/images/125",
          "tags": "banksy, nyc",
          "posted_at": "2013-11-04T03:23:00-07:00"
        }
      ]
    }
    ```
    

Queries should support pagination. A query request can have `cursor` and/or `limit` attributes that control pagination.

###### Example

-   ```
    
    POST /ifttt/v1/queries/list_album_photos HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 1d21c3cd2ed8441ea269dd554d2c8e54
    
    {
      "queryFields": {
        "album_name": "Street Art"
      },
      "limit": 1,
      "ifttt_source": {
        "id": "2",
        "url": "https://ifttt.com/myrecipes/personal/2"
      },
      "user": {
        "timezone": "America/Los_Angeles"
      }
    }
    ```
    

The response should contain `limit` rows (default 50). If the result set is larger than the `limit`, a `cursor` should be present and reference the next page.

###### Paginated Response Example: page 1

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "image_url": "http://example.com/images/128",
          "tags": "banksy, brooklyn",
          "posted_at": "2013-11-04T09:23:00-07:00"
        }
      ],
      "cursor": "seijjh24ks"
    }
    ```
    

If used in a subsequent query request, `cursor` should reference the next page of the result set.

###### Example

-   ```
    
    POST /ifttt/v1/queries/list_album_photos HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 1d21c3cd2ed8441ea269dd554d2c8e54
    
    {
      "queryFields": {
        "album_name": "Street Art"
      },
      "limit": 1,
      "cursor": "seijjh24ks",
      "ifttt_source": {
        "id": "2",
        "url": "https://ifttt.com/myrecipes/personal/2"
      },
      "user": {
        "timezone": "America/Los_Angeles"
      }
    }
    ```
    

The response should contain the next `limit` rows of the result set. The last page should not have the `cursor` attribute.

###### Paginated Response Example: page 2

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "image_url": "http://example.com/images/125",
          "tags": "banksy, nyc",
          "posted_at": "2013-11-04T03:23:00-07:00"
        }
      ]
    }
    ```
    

##### Nested results

Most queries will have primitive ingredients (string, number...) and result in a tabular result set like in the examples above. However, a query can have complex ingredients that are queries themselves resulting in nested result sets. Such query ingredients can be represented in one of the two ways: unresolved or resolved. An unresolved query ingredient will have a subquery **request** as the ingredient value. A client can use that request later in a subsequent query request to drill-down into the result set. A resolved query ingredient will have a subquery **result** as the ingredient value. It's a result of executing the query associated with that ingredient. The request attribute `include` can be used to control which one of the two representations the query ingredient should have in the query response.

The following is an example that demonstrates both scenarios. Here we request a list of images. We also request `likes` to be included with each image.

###### Example

-   ```
    
    POST /ifttt/v1/queries/list_album_photos HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    Content-Type: application/json
    X-Request-ID: 1d21c3cd2ed8441ea269dd554d2c8e54
    
    {
      "queryFields": {
        "album_name": "Street Art"
      },
      "include": ["likes"],
      "ifttt_source": {
        "id": "2",
        "url": "https://ifttt.com/myrecipes/personal/2"
      },
      "user": {
        "timezone": "America/Los_Angeles"
      }
    }
    ```
    

The response should contain a resolved `likes` subquery and unresolved `dislikes` subquery. In both cases inclusion of the `queryFields` attribute is mandatory.

###### Response Example: resolved subquery

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "image_url": "http://example.com/images/128",
          "tags": "banksy, brooklyn",
          "posted_at": "2013-11-04T09:23:00-07:00",
          "likes": {
            "queryFields": {
              "image_url": "http://example.com/images/128"
            },
            "data": [
              { "date": "2013-11-04T09:23:00-07:00", "user": "jim" },
              { "date": "2013-11-04T09:03:00-07:00", "user": "bob" }
            ]
          },
          "dislikes": {
            "queryFields": {
              "image_url": "http://example.com/images/128"
            }
          }
        }
      ]
    }
    ```
    

##### Trigger-based queries

If your service was published before August 2020, trigger-based queries may have been added to your service. These queries use the response from your [trigger endpoint](https://ifttt.com/docs/api_reference#triggers) and translates it to a query that can be used in Applets and connections.

For example, if you had a trigger named **New event added**, the query based on this trigger would be **History of new events added**.

### Query fields

Query fields can have [**dynamic options via a drop-down**](https://ifttt.com/docs/api_reference#query-field-dynamic-options) or static text input. Each dynamic option requires a unique endpoint.

#### Query field dynamic options

Options have both a label, which the user sees, and a value, which is sent when the query is executed. Options can be placed into categories; users may select categorized options but may not select the category itself. See the example exchange below for more information on how to present the options to IFTTT.

###### Request

For **drop-down selector** query fields, you can dynamically provide user-specific options. Each time the query field is displayed, IFTTT will fetch a list of options from your query field’s **dynamic options endpoint**:

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/queries/{{query_slug}}/fields/{{query_field_slug}}/options`
    

###### Headers (authenticated services)

-   ```
    
    Authorization: Bearer {{user_access_token}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Headers (non-authenticated services)

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

An empty JSON object

###### Example

-   ```
    
    POST /ifttt/v1/queries/list_album_photos/fields/album_name/options HTTP/1.1
    Host: api.example-service.com
    Authorization: Bearer b29a71b4c58c22af116578a6be6402d2
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: 9f99e73452cd40198cb6ce9c1cde83d6
    
    {}
    ```
    

###### Response

Your query field’s dynamic options endpoints should generate the following response:

###### HTTP

-   Status
    
    200
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

For the body you will get a JSON object which contains an array, data, of option objects:

###### Body

-   data\[label\]
    
    (string) A user-facing label.
    
    data\[value\]
    
    (string) The actual field value.
    

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": [
        {
          "label": "Street Art",
          "value": "12345"
        },
        {
          "label": "Technology",
          "value": "43245"
        },
        {
          "label": "Animals",
          "values": [
            {
              "label": "Cats",
              "value": "32143"
            },
            {
              "label": "Dogs",
              "value": "51231"
            }
          ]
        }
      ]
    }
    ```
    

### Ingredients

An ingredient is a data point returned by a trigger or a query. Typically a response will have multiple sets of data points. You can think of a response as a tabular data set with items of the `data` attribute as rows, and ingredients as columns.

###### BODY

-   ```
    
      "data": [
        {
          "ingredient 1": "value for row 1 ingredient 1",
          "ingredient 2": "value for row 1 ingredient 2",
          ...
          "ingredient n": "value for row 1 ingredient n"
        },
        ...
        {
          "ingredient 1": "value for row n ingredient 1",
          "ingredient 2": "value for row n ingredient 2",
          ...
          "ingredient n": "value for row n ingredient n"
        },
      ]
    ```
    

The response above can be represented as a table

| ingredient 1 | ingredient 2 | ... | ingredient n |
| --- | --- | --- | --- |
| value for row 1 ingredient 1 | value for row 1 ingredient 2 | ... | value for row 1 ingredient n |
| value for row 2 ingredient 1 | value for row 2 ingredient 2 | ... | value for row 2 ingredient n |
| ... | ... | ... | ... |
| value for row n ingredient 1 | value for row n ingredient 2 | ... | value for row n ingredient n |

#### String ingredients

Ingredients that use the **String**, **Image URL**, **Web URL**, or **File URL** are simple strings.

#### Date and time ingredients

Ingredients that use the **Date** or **Date with time** are timestamps in the [W3 flavor](http://www.w3.org/TR/NOTE-datetime) of ISO8601 formats.

###### Example: Date only

-   `2013-12-31`  
    `2014-01-01`

###### Example: Date & Time

-   `2013-11-04T09:23:00Z`  
    `2013-11-04T09:23:00-07:00`

#### Nested ingredients

Ingredients that use the **Query** are queries themselves. They are available in queries only and described in more detail in [Nested results](https://ifttt.com/docs/api_reference#nested-results).

### Service status

Provide an API endpoint which IFTTT can periodically check for your service’s availability. This endpoint is not user-specific, and thus does not require an access token.

###### Request

IFTTT will make the following request to check your service’s API status:

###### HTTP

-   Method
    
    GET
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/status`
    

###### Headers

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: {{random_uuid}}
    ```
    

###### Example

-   ```
    
    GET /ifttt/v1/status HTTP/1.1
    Host api.example-service.com
    IFTTT-Service-Key: vFRqPGZBmZjB8JPp3mBFqOdt
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    X-Request-ID: 0715f98e65f749aba2fc243eac1e3c09
    ```
    

###### Response

The service status endpoint should generate the following response:

###### HTTP

-   Status
    
    200 or 503
    
    Body
    
    none
    

###### Example: service OK

-   ```
    
    HTTP/1.1 200 OK
    ```
    

###### Example: service unavailable

-   ```
    
    HTTP/1.1 503 Unavailable
    ```
    

___

### OpenAPI definition

We provide an OpenAPI definition file that describes the IFTTT Service API. You can use this file to generate some of your server code. This should save you time and effort implementing your service.

#### What is OpenAPI

[OpenAPI](https://swagger.io/docs/specification/about/) (formerly Swagger) is a standard used to describe an API.

#### How to use it

There are multiple tools that can generate server code from an OpenAPI definition file. The choice of tool will depend on your tech stack and requirements. [OpenAPI Generator](https://openapi-generator.tech/) and [Swagger Codegen](https://swagger.io/tools/swagger-codegen/) are the most popular ones.

For this example we'll use [OpenAPI Generator Gradle Plugin](https://github.com/OpenAPITools/openapi-generator/tree/master/modules/openapi-generator-gradle-plugin) to generate server stubs for a [Spring Boot](https://spring.io/projects/spring-boot) application.

Initialize a gradle project

-   ```
            
    $ mkdir service-api-example
    $ cd service-api-example
    $ gradle wrapper --gradle-version 6.7.1
    $ mkdir -p src/main/resources
    $ mkdir -p src/main/java/com/example/service/
              
            
    ```
    

Create `build.gradle`

-   ```
            
    plugins {
      id 'org.openapi.generator' version '4.3.1'
      id 'org.springframework.boot' version '2.3.4.RELEASE'
      id 'io.spring.dependency-management' version '1.0.10.RELEASE'
      id 'java'
    }
    
    group = 'com.example.service'
    version = '0.0.1-SNAPSHOT'
    
    repositories {
      mavenCentral()
    }
    
    // Configuration for the OpenAPI Generate Gradle Plugin
    openApiGenerate {
      // OpenAPI definition file location
      inputSpec = "${projectDir}/src/main/resources/service-api.yaml"
      // Which generator to use (see https://openapi-generator.tech/docs/generators#server-generators)
      generatorName = 'spring'
      // https://openapi-generator.tech/docs/generators/spring
      configOptions = [
        dateLibrary         : "java8",
        interfaceOnly       : "true",
        skipDefaultInterface: "false",
        openApiNullable     : "false",
        apiPackage          : "${group}.${name}",
        modelPackage        : "${group}.${name}.model",
      ]
    }
    
    sourceSets.main.java.srcDirs += 'build/generate-resources/main/src/main/java'
    
    dependencies {
      implementation 'org.springframework.boot:spring-boot-starter-web'
      annotationProcessor 'org.springframework.boot:spring-boot-configuration-processor'
      implementation 'org.springframework:spring-webmvc:5.2.9.RELEASE'
      implementation 'io.swagger:swagger-annotations:1.6.2'
      implementation 'javax.validation:validation-api:2.0.1.Final'
      implementation 'com.fasterxml.jackson.core:jackson-annotations:2.11.3'
      implementation 'org.openapitools:jackson-databind-nullable:0.2.1'
      implementation 'javax.annotation:javax.annotation-api:1.3.2'
      compileOnly 'javax.servlet:javax.servlet-api:4.0.1'
    }
              
            
    ```
    

Download [OpenAPI definition for IFTTT Service API](https://github.com/IFTTT/service-api/blob/master/service-api.yaml) into `src/main/resources/service-api.yaml`.

Generate server stubs `./gradlew openApiGenerate`.

You should be able to find generated code at `build/generate-resources/main/src/main/java/com/example/service/service_api_example/IftttApi.java`.

Now we can add our own implementation. For this example we'll implement just one endpoint: `/ifttt/v1/status`.

Create API implementation `src/main/java/com/example/service/IftttApiController.java`

-   ```
            
    package com.example.service;
    
    import com.example.service.service_api_example.IftttApi;
    import org.springframework.http.ResponseEntity;
    import org.springframework.web.bind.annotation.RestController;
    
    @RestController
    public class IftttApiController implements IftttApi {
        @Override
        public ResponseEntity getStatus() {
            return ResponseEntity.ok().build();
        }
    }
            
          
    ```
    

Create the main class `src/main/java/com/example/service/Application.java`

-   ```
            
    package com.example.service;
    
    import org.springframework.boot.SpringApplication;
    import org.springframework.boot.autoconfigure.SpringBootApplication;
    
    @SpringBootApplication
    public class Application {
      public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
      }
    }
            
          
    ```
    

Run the app `./gradlew bootRun`.

Check the app status `curl --verbose localhost:8080/ifttt/v1/status`. You should see a successful 200 response with no body.

#### Next steps:

-   Learn about [testing your service](https://ifttt.com/docs/testing).
-   Explore the [Connect API](https://ifttt.com/docs/connect_api).