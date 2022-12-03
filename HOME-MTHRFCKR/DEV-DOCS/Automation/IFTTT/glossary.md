### Action

An action is the work that IFTTT initiates as a result of an updated trigger.

Actions are organized under services. Some example actions are “Create post” or “Post a new tweet”.

### Action field

When a user enables a connection or sets up an Applet, they populate the action’s “action fields” with data, usually including ingredients provided by the trigger. Think of action fields as a form field. For example, when using the “Create post” action, the two action fields are for the “Title” and “Post Body”. When using the “Post a new tweet” action, the only action field is the text of the message.

Almost every action has at least one action field.

### Applet

We bring services together into Applets. An Applet connects two or more apps or devices together. It enables you to do something that those apps or devices couldn’t do on their own.

Some example Applets include [Sync Amazon Alexa to-dos with your Google Calendar](https://ifttt.com/applets/w34JWa5M-create-an-event-on-your-ios-calendar-using-amazon-alexa?utm_medium=Help&utm_source=Basics&utm_campaign=Using_IFTTT) or [Create events in your iPhone Calendar, via Google Assistant](https://ifttt.com/applets/eX6zn2mD-create-an-event-on-your-iphone-s-calendar-with-google-home?utm_medium=Help&utm_source=Basics&utm_campaign=Using_IFTTT). IFTTT users can turn on Applets that have been created by services or other users, or they can create their own. Here’s [a short video tutorial](https://www.youtube.com/watch?v=-M4kRmnZUBM) that shows you how to connect your apps and devices, and turn on Applets.

Applets are composed of [triggers](https://ifttt.com/docs/glossary#triggers), [queries](https://ifttt.com/docs/glossary#queries), and [actions](https://ifttt.com/docs/glossary#actions). Triggers tell an Applet to start, queries provide data, and actions are the end result of an Applet run.

### Applet ID

The _Applet ID_ is an ID that specifies an Applet on IFTTT. For example, [this Applet](https://ifttt.com/applets/YfkYtQB2-get-a-notification-when-the-international-space-station-passes-over-your-house)'s ID is `YfkYtQB2`.

### Applet version ID

An Applet version ID specifies a user's _version_ of an Applet. It will look like `78911786` and is available on an Applet page when the user views it.

### Applet defaults

See [Applet templates](https://ifttt.com/docs/api_reference#Applet-templates) in the API reference documentation.

### Applet run

When a user sets up an Applet, IFTTT starts monitoring the endpoint specified by the trigger service. Every time IFTTT finds that the data has been updated, IFTTT will execute the Applet, pushing the data from the trigger over to the action(s). This is an “Applet Run”.

To get an Applet to run as close to the triggering event as possible, triggers should [use the Realtime API](https://ifttt.com/docs/api_reference#realtime-api).

### Connection

Connections provide a way to power and embed integrations between your service and another brand's service. Connections contain one or more [features](https://ifttt.com/docs/glossary#feature) which are groups of [triggers](https://ifttt.com/docs/glossary#triggers), [queries](https://ifttt.com/docs/glossary#queries), and [actions](https://ifttt.com/docs/glossary#actions).

### Connect button

A connect button embeds a connection in your [iOS app](https://ifttt.com/docs/connect_api#ios-and-android-sdks), [Android app](https://ifttt.com/docs/connect_api#ios-and-android-sdks), website, or emails and yields the recommended user experience to better set user expectations and increase conversion rates.

### Endpoint

The URI at the service's domain where IFTTT will request updates (for triggers) or POST data (for actions).

### Feature

A feature is a group of triggers, queries, and actions which let you define what a connection will do for your users. Features can be optional to give your users more fine-grained control and visibility.

### IFTTT-Service-Key

A [key](https://platform.ifttt.com/mkt/api) that identifies your service. Interchangeable with `IFTTT-Channel-Key`.

### Ingredient

Triggers and queries contain ingredients – individual pieces of data.

Some example ingredients from the “New tweet by you” trigger from the Twitter service:

-   Text – The tweet itself.
-   UserName – User name of tweeter.
-   LinkToTweet – The URL to the tweet itself.
-   CreatedAt – Date and time tweet was created.
-   TweetEmbedCode – The HTML embed code for the Tweet.

A user will take the individual ingredients provided by a trigger or a query and will use them to fill in an action’s [action fields](https://ifttt.com/docs/glossary#action-field).

### Query

A query is a way to request additional data if the trigger doesn't provide it. IFTTT initiates a Query execution as a result of an updated trigger.

Queries are organized under services. Some example queries are “List busy windows” or “Search events”.

Every service is required to have at least one query.

### Query field

When a user enables a connection or sets up an Applet, they populate the query’s “query fields” with data, usually including ingredients provided by the trigger. Think of query fields as a form field. For example, when using the “Search events” query, the two query fields are for the “Calendar id” and “Query”. When using the “List busy windows” query, the only query field is the id of the calendar.

Almost every query has at least one query field.

### Realtime API

IFTTT’s [Realtime API](https://ifttt.com/docs/api_reference#realtime-api) lets Applets using your triggers to run near-instantly. Utilizing the Realtime API is required for services with triggers.

### Service

Services are the basic building blocks of IFTTT. Some example services are Facebook, Twitter, Nest, Fitbit, Amazon Alexa and Gmail. Your product will be represented on IFTTT as a service.

### Slug

In the context of the IFTTT platform, a slug is the immutable ID of a service, trigger, trigger field, ingredient, action, or action field.

### Trigger

A trigger is the data that, when changed, notifies a connnection's [webhook](https://ifttt.com/docs/connect_api#webhook-endpoint) or prompts an Applet to run on IFTTT. Some example triggers include _Breaking news for sport_ or _New results from search_.

Triggers are organized under services. Each service provides an endpoint for each trigger, which is checked after the service POSTs to the [Realtime API](https://ifttt.com/docs/api_reference#realtime-api) (recommended) alerting IFTTT that there is fresh trigger data. If the Realtime API is not used, the trigger is checked periodically for new data.

Learn more about how triggers work [in our FAQ](https://ifttt.com/docs/faq#triggers).

### Trigger field

When a user enables a connection or sets up an Applet, they can specify certain parameters that IFTTT will pass to the service's endpoint when it makes the request for new data.

Think of trigger fields as a “filter” for the data requested from a trigger. For example, on the Google Drive service, the “New file in your folder” has the trigger field “Drive folder path”. When the user sets up an Applet with that trigger, she can select which folder she’s interested in. Or for the Spotify “New track added to a playlist” trigger, the user can specify the playlist they want to subscribe to.