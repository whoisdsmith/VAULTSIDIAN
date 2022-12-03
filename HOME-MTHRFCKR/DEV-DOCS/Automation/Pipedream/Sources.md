Event sources operate primarily as workflow triggers. When you add a new app-based [trigger](https://pipedream.com/docs/workflows/steps/triggers/) to your workflow, you're creating an event source.

![New-app-based trigger](https://pipedream.com/docs/assets/img/app-based-trigger.15b0a5a9.png)

Event sources run as their own resources, separate from workflows, for two reasons:

-   A single event sources can trigger more than one workflow. If you have a data source that you want to run _multiple_ workflows, you can create an event source once and use it as the trigger for each workflow.
-   If you need to consume events emitted by event sources in your own application, you don't need to run a workflow: you can use Pipedream's [REST API](https://pipedream.com/docs/api/rest/) or a [private, real-time SSE stream](https://pipedream.com/docs/api/sse/) to access the event data directly.

You can view your event sources at [https://pipedream.com/sources (opens new window)](https://pipedream.com/sources). Here, you'll see the events a specific source has emitted, as well as the logs and configuration for that source.

-   [Overview](https://pipedream.com/docs/#overview)
-   [Creating event sources](https://pipedream.com/docs/#creating-event-sources)
    -   [Creating a source from the UI](https://pipedream.com/docs/#creating-a-source-from-the-ui)
    -   [Creating a source from the CLI](https://pipedream.com/docs/#creating-a-source-from-the-cli)
-   [Consuming events from sources](https://pipedream.com/docs/#consuming-events-from-sources)
-   [Example: HTTP source](https://pipedream.com/docs/#example-http-source)
-   [Example: Cron jobs](https://pipedream.com/docs/#example-cron-jobs)
-   [Example: RSS](https://pipedream.com/docs/#example-rss)
-   [Publishing a new event source, or modifying an existing source](https://pipedream.com/docs/#publishing-a-new-event-source-or-modifying-an-existing-source)
-   [Limits](https://pipedream.com/docs/#limits)

## [#](https://pipedream.com/docs/#overview) Overview

Event sources collect data from apps or service like Github, Twitter, and Google Calendar, then **emit** this data as individual events. These events trigger linked workflows, and [can be retrieved using the API or SSE interfaces](https://pipedream.com/docs/#consuming-events-from-sources).

If the service supports webhooks or another mechanism for real-time data delivery, the event source uses it. For example, Google Sheets supports webhooks, which allows Google Sheets event sources to emit updates instantly.

If a service doesn't support real-time event delivery, Pipedream polls the API for updates every few minutes, emitting events as the API produces them. For example, Airtable doesn't support webhooks, so we poll their API for new records added to a table.

## [#](https://pipedream.com/docs/#creating-event-sources) Creating event sources

You can create event sources from the Pipedream UI or CLI.

### [#](https://pipedream.com/docs/#creating-a-source-from-the-ui) Creating a source from the UI

Visit [https://pipedream.com/sources (opens new window)](https://pipedream.com/sources) and click the **New +** button at the top right to create a new event source. You'll see a list of sources tied to apps (like Twitter and Github) and generic interfaces (like HTTP). Select your source, and you'll be asked to connect any necessary accounts (for example, the Twitter source requires you authorize Pipedream access to your Twitter account), and enter the values for any configuration settings tied to the source.

Once you've created a source, you can use it to trigger [Pipedream workflows](https://pipedream.com/docs/workflows/) or [consume its events](https://pipedream.com/docs/#consuming-events-from-sources) using Pipedream's APIs.

### [#](https://pipedream.com/docs/#creating-a-source-from-the-cli) Creating a source from the CLI

[Download the CLI](https://pipedream.com/docs/cli/install/) and run:

This will bring up an interactive menu prompting you to select a source. Once selected, you'll be asked to connect any necessary accounts (for example, the Twitter source requires you authorize Pipedream access to your Twitter account), and enter the values for any configuration settings tied to the source.

Once you've created a source, you can use it to trigger [Pipedream workflows](https://pipedream.com/docs/workflows/) or [consume its events](https://pipedream.com/docs/#consuming-events-from-sources) using Pipedream's APIs.

## [#](https://pipedream.com/docs/#consuming-events-from-sources) Consuming events from sources

You can view the events for a source in the sources UI, under the **Events** section of that source.

You can also trigger a [Pipedream workflow](https://pipedream.com/docs/workflows/) every time your source emits a new event. This lets you run workflows for every new tweet, every new item in an RSS feed, and more.

Finally, you can consume events programmatically, outside the Pipedream platform, in a few different ways:

-   In real-time, using the [SSE stream](https://pipedream.com/docs/api/sse/) linked to your source
-   In real-time, via the CLI's [`pd events` command](https://pipedream.com/docs/api/sse/#subscribe-to-new-events-using-the-pipedream-cli)
-   In batch, using the [REST API](https://pipedream.com/docs/#rest-api)

## [#](https://pipedream.com/docs/#example-http-source) Example: HTTP source

The simplest event source is an **HTTP source**.

When you create an HTTP source:

-   You get a unique HTTP endpoint that you can send any HTTP request to.
-   You can view the details of any HTTP request sent to your endpoint: its payload, headers, and more.
-   You can delete the source and its associated events once you're done.

HTTP sources are essentially [request bins (opens new window)](https://requestbin.com/) that can be managed via API.

HTTP sources are a good example of how you can turn an event stream into an API: the HTTP requests are the **event stream**, generated from your application, client browsers, webhooks, etc. Then, you can retrieve HTTP requests via Pipedream's [**REST API**](https://pipedream.com/docs/api/rest/), or stream them directly to other apps using the [SSE interface](https://pipedream.com/docs/api/sse/).

[**See the Github quickstart for more information on HTTP event sources** (opens new window)](https://github.com/PipedreamHQ/pipedream/tree/master/components/http#quickstart).

## [#](https://pipedream.com/docs/#example-cron-jobs) Example: Cron jobs

You can also use event sources to run any Node code on a schedule, allowing you to poll a service or API for data and emit that data as an event. The emitted events can trigger Pipedream workflows, and can be retrieved using Pipedream's [**REST API**](https://pipedream.com/docs/api/rest/) or [SSE interface](https://pipedream.com/docs/api/sse/).

You can run an event source that polls an RSS for new items and emits them in real time as formatted JSON.

[**Create an RSS event source here** (opens new window)](https://pipedream.com/sources/new?app=rss&key=rss-new-item-in-feed).

## [#](https://pipedream.com/docs/#publishing-a-new-event-source-or-modifying-an-existing-source) Publishing a new event source, or modifying an existing source

Anyone can create an event source or edit an existing one. The code for all event sources is public, and kept in the [`PipedreamHQ/pipedream` repo (opens new window)](https://github.com/PipedreamHQ/pipedream). [Read this quickstart](https://pipedream.com/docs/components/quickstart/nodejs/sources/) and see the [event source API docs](https://pipedream.com/docs/components/api/) to learn more about the source development process.

You can chat about source development with the Pipedream team in the `#contribute` channel of our [public Slack (opens new window)](https://join.slack.com/t/pipedream-users/shared_invite/zt-ernlymsn-UHfPg~Dfp08uGkAd8dpkww), and in the `#dev` topic in the [Pipedream community (opens new window)](https://pipedream.com/community/c/dev/11).

## [#](https://pipedream.com/docs/#limits) Limits

Event sources are subject to the [same limits as Pipedream workflows](https://pipedream.com/docs/limits/).