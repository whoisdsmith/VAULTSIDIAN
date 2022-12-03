## What are connections?

Connections allow you to power entire integrations between your service and another with one single connection. A user connects once using the connect button, and you can power multiple queries, triggers, and actions.

## Connections vs Applets

Applets are 1:1. There's one trigger that happens on your service that maps to certain actions on another service. Also, Applets need to be configured on IFTTT and aren't compatible with queries.

Connections, on the other hand, are there to achieve multiple functions with a single integration. Connections allow you to set up queries, triggers, and actions for your users [via the Connect API](https://ifttt.com/docs/connect_api) without the user having to enable anything on IFTTT. Just connect, authenticate, and you're ready to go.

## Creating connections

### Connection creation tool

The [connection creation tool](https://platform.ifttt.com/mkt/connections%2Fnew) is designed for you to be able to build powerful integrations with any service on IFTTT. Connections created on the platform should be used in tandem with the [Connect API](https://ifttt.com/docs/connect_api), the [iOS SDK](https://github.com/IFTTT/ConnectSDK-iOS), and the [Android SDK](https://github.com/IFTTT/ConnectSDK-Android).

#### How to use the tool

1.  Start by searching for and selecting the service you are looking to connect with
2.  Then add a [feature](https://ifttt.com/docs/glossary#feature) and configure the triggers, queries, and actions you're going to use.
3.  Enter a title for the connection (e.g. "Control your Hue lights when you stream on Twitch") then click **Update**.
4.  A runtime script, if included, will run any time a new trigger event occurs for the connection.
5.  You'll now have access to Connect API endpoints for the selected queries, triggers, and actions.
6.  Leverage the [Connect API](https://ifttt.com/docs/connect_api) along with the [iOS SDK](https://github.com/IFTTT/ConnectSDK-iOS) and [Android SDK](https://github.com/IFTTT/ConnectSDK-Android) to programmatically execute queries, subscribe to triggers, and run actions for your users.

#### Tips on configuration

Connection query fields, trigger fields, and action fields can either be set by you as the developer or shown to the user to set themselves. How a connection is configured is dependent on the experience you're looking to create. See below for an example of how to use different configuration settings for different experiences.

#### Example: Control the color of your Hue lightbulbs

Service: Philips Hue Action: Change color

Use cases:

**Change a user's Hue lights to blue** An experience you're looking to create that only sets a user's Hue lights to blue.

| Field name | Visibility | Value |
| --- | --- | --- |
| Which lights? | Customizable by the user | Set by the user |
| Color value or name | Set by you | `blue` |

**Change a user's Hue lights to their favorite color** An experience you're looking to create that sets a user's Hue lights to their favorite single color.

| Field name | Visibility | Value |
| --- | --- | --- |
| Which lights? | Customizable by the user | Set by the user |
| Color value or name | Customizable by the user | `blue` (default) |

**Change a user's Hue lights dynamically from your mobile app** An experience you're powering where a user can change the color of their Hue lights directly from your mobile app.

| Field name | Visibility | Value |
| --- | --- | --- |
| Which lights? | Customizable by the user | Set by the user |
| Color value or name | Set by you | `blue` (default) |

To change the color of the lights dynamically, be sure to include the following in the body of your [action run request](https://ifttt.com/docs/connect_api#run-an-action). This will overide the default value (`blue`).

```
{
  "fields": {
    "color": "purple",
  }
}
```

### Runtime script

#### What is a runtime script

A runtime script is JavaScript code that runs when IFTTT detects a new trigger event. Normally a connection requires you to run a backend server that receives trigger [[Webhooks|[[Webhoo]]ks|[[webhoo]]ks]] from IFTTT and runs queries and actions by making Connect API requests to IFTTT. However, if your case is simple enough you can avoid running your own connection backend by implementing your connection logic in a runtime script. Your runtime script will be executed by IFTTT when a new trigger event occurs. In the script you can examine the trigger event and run connection queries and actions.

#### How to write a runtime script

A runtime script can be added on the connection edit page. Think of a runtime script as a trigger event handler. To understand how to write one let's go over an example.

Let's say you have created a connection between YouTube and SMS. The connection is set up to use the New liked video trigger, Search for videos query, and Send me an SMS action. Once the trigger fires you want the runtime script to search YouTube for similar videos and send you a text message with the search results.

First we need to get the title of the liked video. The `Trigger` object contains the event information. Click "Open reference" link in the top right hand corner of the script editor to see all available ingredients.

```
const likedVidTitle = Trigger.ingredients.title;
```

Then we need to search for similar videos. To achieve that we'll use the `get_videos_from_search` query and request the first 3 videos.

```
const promise = performQuery("youtube.get_videos_from_search", { fields: {search_query: likedVidTitle}, limit: 3});
```

And finally we need to send a text message for every video found.

```
promise.then((response) => {
  response.responseBody.data.forEach(video => {
    runAction("sms.send_me_text", { fields: { message: `${video.title} ${video.url}` }});
  });
});
```

Here is the script in its entirety:

```
const likedVidTitle = Trigger.ingredients.title;

const promise = performQuery("youtube.get_videos_from_search", { fields: {search_query: likedVidTitle}, limit: 3});

promise.then((response) => {
  response.responseBody.data.forEach(video => {
    runAction("sms.send_me_text", { fields: { message: `${video.title} ${video.url}` }});
  });
});
```

#### JavaScript API

##### Constants

The following constants are available to you in a runtime script:

| Constant | Type | Description | Example |
| --- | --- | --- | --- |
| `Meta.currentUserTime` | `moment.js` object | Current time in user's timezone |  |
| `Trigger.id` | string | Trigger id | `"youtube.new_liked_video"` |
| `Trigger.ingredients` | object | Event details | `{ title: "Hello World!", url: "https://..." }` |
| `Connection.serviceUserId` | string | User id as given to IFTTT by your service | `"UCr9jxQ3llSDks"` |
| `Connection.currentFeatureName` | string | The name of the current feature | `"yp6zrl2tpd"` |
| `Connection.userFeatureId` | string | The id of the current user feature | `"f98de900-fe18-4fd2-b42b-422761d030a9"` |
| `Connection.configuration` | object | The connection fields defined in the connection composer | `{foo: "bar"}` |

##### Functions

The following functions are available to you in a runtime script:

```
runAction(actionId, requestBody)
```

This will run an action using [Connect API](https://ifttt.com/docs/connect_api).

| Argument | Type | Description | Example |
| --- | --- | --- | --- |
| `actionId` | string | The id of the action you want to execute | `"sms.send_me_text"` |
| `requestBody` | object | (Optional) The body of the action request, same as a body of a [Connect API action request](https://ifttt.com/docs/connect_api#run-an-action) |  |

```
performQuery(queryId, requestBody)
```

This will run a query using [Connect API](https://ifttt.com/docs/connect_api).

| Argument | Type | Description | Example |
| --- | --- | --- | --- |
| `queryId` | string | The id of the query you want to execute | `"youtube.get_videos_from_search"` |
| `requestBody` | object | (Optional) The body of the query request, same as a body of a [Connect API query request](https://ifttt.com/docs/connect_api#perform-a-query) |  |

Both of these functions return a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that provides the following response object to your handler function:

```
{
  statusCode: (number) the http status code returned by [Connect API](/docs/connect_api),
  responseBody: (object) the response body returned by [Connect API](/docs/connect_api)
}
```

#### Examples

##### Run an action

```
runAction("sms.send_me_text")
  .then((response) => { /* handle action response here */ });
```

This will execute the action with default fields (set by the user when they enable the connection).

##### Run a query

```
performQuery("youtube.get_videos_from_search")
  .then((response) => { /* handle query response here */ });
```

This will execute the query with default fields (set by the user when they enable the connection).

##### Limit query results

```
performQuery("youtube.get_videos_from_search", { limit: 3 });
```

This query will return 3 items.

##### Override default fields

```
runAction("sms.send_me_text", { fields: { message: "overriden" } });
```

In this example we are overriding the `message` field. The same approach can be used when running queries.

##### Access connection options

```
Connection.configuration.foo;
```

This is how you access a field `foo` defined on the connection level.

##### Using feature context

```
Connection.currentFeatureName;
```

This will give you the name of the current feature. This is useful when a connection has the same trigger in multiple features.

```
runAction("sms.send_me_text", { user_feature_id: Connection.userFeatureId } });
```

This will run the action in the context of the current feature. This is useful when a connection has the same action in multiple features.

#### Execution environment

Runtime: Node.js 12.

Time limit: 10 seconds (your runtime script will be terminated if it exceeds this limit).

### Testing and publishing your connections

-   To see the Connect API logs for a given connection, click the "API logs" tab and reference set of [status codes](https://ifttt.com/docs/connect_api#http-status-codes).
    
-   Connections can be tested fully with the [iOS and Android SDKs](https://ifttt.com/docs/connect_api#ios-and-android-sdks).
    
-   Publishing connections is only available for approved paid organizations. To learn more, [contact sales](mailto:sales@ifttt.com).
    

___

#### Next steps:

-   Explore the [Connect API](https://ifttt.com/docs/connect_api).
-   Create your first connection with our [Connect Quick Start Guide](https://ifttt.com/docs/getting_started_connect).
-   Explore the [Service API](https://ifttt.com/docs/api_reference) to build [triggers](https://ifttt.com/docs/glossary#trigger), [queries](https://ifttt.com/docs/glossary#query), and [actions](https://ifttt.com/docs/glossary#action) that other services can interact with.


---
#ifttt 