You can test the implementation of your service API using IFTTT’s fully-automated endpoint testing tool. The tool will make requests against your API using sample data you provide and perform validation on the responses.

Your service must pass all of the endpoint testing tool’s tests before it can be reviewed for publication.

### The test/setup endpoint

Before starting an automated test, the endpoint testing tool will send a `POST` request to your service API’s `test/setup` endpoint. This serves as a signal to your API that a test is about to begin.

When the `test/setup` endpoint is called, it should perform the following:

-   If needed, prepare **mock users** and other **test fixtures**, so that your API’s endpoints can respond with meaningful data.
-   Provide **sample input** that can be used in subsequent calls to your service API. This includes:
    -   A valid OAuth access token, corresponding to a real user account.
    -   Sample input parameters for each of your API’s endpoints.

For security, the endpoint testing tool will send your **Service Key** in the request to `test/setup` in the `IFTTT-Service-Key` header. Before performing any of the above operations, you should verify that the value of the header matches the value for your Service Key, as displayed in the Developer UI.

### Request

###### HTTP

-   Method
    
    POST
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/test/setup`
    

###### HEADERS

-   ```
    
    IFTTT-Service-Key: {{ifttt_service_key}}
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    ```
    

###### Example

-   ```
    
    POST /ifttt/v1/test/setup HTTP/1.1
    Host: api.example-service.com
    IFTTT-Service-Key: vFRqPGZBmZjB8JPp3mBFqOdt
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    ```
    

### Response

###### HTTP

-   Status
    
    200
    
    URL
    
    `{{api_url_prefix}}/ifttt/v1/test/setup`
    
    Headers
    
    `Content-Type: application/json; charset=utf-8`
    

For the body you will get a JSON object with one top-level field, `data`, containing the following properties:

###### Body

-   data\[accessToken\]
    
    Only returned by OAuth Services. This should be a valid access token that corresponds to a user on your service.
    
    data\[samples\]
    
    an object containing sample input for your endpoints. See example below for specific details for each type of sample.
    

###### Example

-   ```
    
    POST /ifttt/v1/test/setup HTTP/1.1
    Host: api.example-service.com
    IFTTT-Service-Key: vFRqPGZBmZjB8JPp3mBFqOdt
    Accept: application/json
    Accept-Charset: utf-8
    Accept-Encoding: gzip, deflate
    ```
    

### Example

Consider a Service with the following properties:

-   **trigger:** `any_new_photo_in_category`
-   -   **category** (drop-down)

-   **trigger:** `any_new_photo_in_album`
-   -   **album** (text field)

-   **trigger:** `any_new_photo_by_you`
-   -   _No Trigger Fields_

-   **action:** `post_a_photo`
-   -   **album** (text field)
    -   **url** (text field)
    -   **description** (text body)

The Service’s response could be as follows:

###### Example

-   ```
    
    HTTP/1.1 200 OK
    Content-Type: application/json; charset=utf-8
    
    {
      "data": {
        "accessToken": "taSvYgeXfM1HjVISJbUXVBIw1YUkKABm",
        "samples": {
          "triggers": {
            "any_new_photo_in_category": {
              "category": "Nature"
            },
            "any_new_photo_in_album": {
              "album": "Italy"
            }
          },
          "triggerFieldValidations": {
            "any_new_photo_in_album": {
              "album": {
                "valid": "Italy",
                "invalid": "AlbumDoesNotExist"
              }
            }
          },
          "actions": {
            "post_a_photo": {
              "album": "Sports",
              "url": "http://example.com/foo/jpg",
              "description": "AT&T Park"
            }
          },
          "actionRecordSkipping": {
            "post_a_photo": {
              "album": "Sports",
              "url": "http://example.com/foo/jpg",
              "description": ""
            }
          }
        }
      }
    }
    ```
    

### Explanation of samples fields

###### `triggers`

```

    "triggers": {
      "any_new_photo_in_category": {
        "category": "Nature"
      },
      "any_new_photo_in_album": {
        "album": "Italy"
      }
    },
```

For all triggers that have trigger fields, provide a set of valid values for those trigger fields. These will be used in requests to verify that trigger endpoints respond appropriately.

For the example above, when testing the `triggers/any_new_photo_in_category` endpoint IFTTT will make requests with:

```
{ triggerFields: { "category": "Nature" } }
```

When testing triggers, IFTTT will expect a response containing at least three events for each trigger.

It should be noted that because `any-new-photo-by-you` does not have any trigger fields, it need not be included in the sample response.

###### `triggerFieldValidations`

```
...
"triggerFieldValidations": {
  "any_new_photo_in_album": {
    "album": {
      "valid": "Italy",
      "invalid": "AlbumDoesNotExist"
    }
  }
},
...
```

For all triggers with dynamic validators, provide a valid example and an invalid example.

For the example above, “Italy” corresponds to an album that exists on the service for this user and, unsurprisingly, “AlbumDoesNotExist” does not.

###### `actions`

```
...
"actions": {
  "post_a_photo": {
    "album": "Sports",
    "url": "http://example.com/foo/jpg",
    "description": "AT&T Park"
  }
},
...
```

For all actions, provide a set of valid values for each action field.

For the example above, when testing the `actions/post_a_photo` endpoint IFTTT will make requests with:

```
{ actionFields: { "album": "Sports", "url": "http://example.com/foo/jpg", "description": "AT&T Park" } }
```

###### `actionRecordSkipping`

```
...
"actionRecordSkipping": {
  "post_a_photo": {
    "album": "Sports",
    "url": "http://example.com/foo/jpg",
    "description": ""
  }
}
...
```

If you want to [skip actions](https://ifttt.com/docs/api_reference#skipping-actions), you can optionally provide test inputs that cause your action endpoint to return a `SKIP` response.

For the example above, the service does not allow photos to be created with blank descriptions. Therefore, when IFTTT makes a request with a blank `description` a record-skip response is expected.

IFTTT may decide at any point in the future to include additional data sent to your API in order to provide extra information, optional features, or to aid in debugging. We do not consider this a breaking change, and ask that you do not either.

As such, we ask that you do not validate the JSON strictly enough to the point where additional (validly formatted) key/values will result in an error. You may certainly validate and return an error if the JSON data is malformed or values that you normally expect are missing— IFTTT would normally publish a new API version in breaking cases like this.

To put it simply: **you should always expect that IFTTT may add additional JSON data at any time and your API should function correctly if it does**.

To ensure that your API adheres to this requirement, you’ll notice an endpoint test labeled **“with extra data”**. This test API request includes an additional randomly generated key/value pair in the JSON and expects that your API should ignore it and process the request normally.

### OAuth

Since the standard OAuth 2 flow involves an interactive step, we provide an authentication test for testing your OAuth flow. [Enable authentication first](https://ifttt.com/services/hello_world_086b07cf29/api/authentication) to use the authentication test.

___

#### Next steps:

-   Create your first connection with our [Connect Quick Start Guide](https://ifttt.com/docs/getting_started_connect).
-   Learn about [building Applets](https://ifttt.com/docs/applets).