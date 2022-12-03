Pipedream includes an event source which exposes an HTTP API for scheduling one-time tasks. You can schedule tasks at any timestamp, with second-level precision, up to one year in the future.

[Click here to create this source (opens new window)](https://pipedream.com/sources?action=create&key=pipedream-new-scheduled-tasks), or visit [https://pipedream.com/sources/new (opens new window)](https://pipedream.com/sources/new), select the **Pipedream** app, and the **New Scheduled Tasks** source.

To [schedule a new task](https://pipedream.com/docs/#scheduling-a-task), just send an HTTP `POST` request to your source's endpoint, at the `/schedule` path, with the following format:

When the timestamp arrives and the task is invoked, the source will emit the payload passed in your original, scheduled request. This allows you to trigger [a Pipedream workflow](https://pipedream.com/docs/workflows/) at the scheduled time, passing the `message` and `timestamp` to the workflow as an [incoming event](https://pipedream.com/docs/workflows/events/).

You can also listen for these events in your own app / infra, by [subscribing to your source's SSE stream](https://pipedream.com/docs/api/sse/). Each time a scheduled task is emitted from your Pipedream source, it also emits a message to that SSE stream. Any application (a Docker container, a Rails app, etc.) listening to that SSE stream can react to that message to run whatever code you'd like.

-   [HTTP API](https://pipedream.com/docs/#http-api)
    -   [Scheduling a task](https://pipedream.com/docs/#scheduling-a-task)
    -   [Cancelling a scheduled task](https://pipedream.com/docs/#cancelling-a-scheduled-task)
-   [Processing scheduled tasks](https://pipedream.com/docs/#processing-scheduled-tasks)

## [#](https://pipedream.com/docs/#http-api) HTTP API

This source exposes an HTTP endpoint where you can send `POST` requests to schedule new tasks. Your endpoint URL should appear as the **Endpoint** in your source's details, in the **Events** tab.

### [#](https://pipedream.com/docs/#scheduling-a-task) Scheduling a task

#### [#](https://pipedream.com/docs/#pipedream-built-in-action) Pipedream built-in action

Use the **Pipedream Task Scheduler - Schedule Task** Helper Functions action to schedule a new task.

#### [#](https://pipedream.com/docs/#node-js) Node.js

Use the following code in a Node.js code step:

#### [#](https://pipedream.com/docs/#curl) `cURL`

To schedule a new task, `POST` a JSON object with an [ISO 8601 (opens new window)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toISOString) `timestamp` and a `message` to the **`/schedule` path** of your source's HTTP endpoint:

Optionally, if you configured a secret in your source, you'll need to pass that in the `x-pd-secret` header. For example:

Successful task schedule requests yield a `200 OK` response, noting the task was successfully scheduled.

### [#](https://pipedream.com/docs/#cancelling-a-scheduled-task) Cancelling a scheduled task

When you schedule a task, you'll receive a unique ID assigned to that task in the `id` field of the HTTP response body. That `id` can be passed to the `/cancel` endpoint to cancel that task before its scheduled time arrives.

#### [#](https://pipedream.com/docs/#node-js-2) Node.js

Cancel tasks using the following code in a Node.js code step:

#### [#](https://pipedream.com/docs/#curl-2) `cURL`

## [#](https://pipedream.com/docs/#processing-scheduled-tasks) Processing scheduled tasks

Scheduled tasks are emitted by the event source as events, which you can consume with

-   [Pipedream workflows](https://pipedream.com/docs/workflows/)
-   [A source-specific SSE stream](https://pipedream.com/docs/api/sse/)
-   [The Pipedream REST API](https://pipedream.com/docs/api/rest/)
-   [The Pipedream CLI](https://pipedream.com/docs/cli/reference/#installing-the-cli)

[See the docs on consuming events from sources](https://pipedream.com/docs/sources/#consuming-events-from-sources) for more information.