Events trigger workflow executions. The event that triggers your workflow depends on the trigger you select for your workflow:

-   [HTTP triggers](https://pipedream.com/docs/workflows/steps/triggers/#http) invoke your workflow on HTTP requests.
-   [Cron triggers](https://pipedream.com/docs/workflows/steps/triggers/#schedule) invoke your workflow on a time schedule (e.g., on an interval).
-   [Email triggers](https://pipedream.com/docs/workflows/steps/triggers/#email) invoke your workflow on inbound emails.
-   [Event sources](https://pipedream.com/docs/workflows/steps/triggers/#app-based-triggers) invoke your workflow on events from apps like Twitter, Google Calendar, and more.

___

-   [Selecting a test event](https://pipedream.com/docs/#selecting-a-test-event)
-   [Examining event data](https://pipedream.com/docs/#examining-event-data)
-   [Copying references to event data](https://pipedream.com/docs/#copying-references-to-event-data)
-   [Copying the values of event data](https://pipedream.com/docs/#copying-the-values-of-event-data)
-   [Event format](https://pipedream.com/docs/#event-format)
    -   [HTTP](https://pipedream.com/docs/#http)
    -   [Cron Scheduler](https://pipedream.com/docs/#cron-scheduler)
    -   [Email](https://pipedream.com/docs/#email)
-   [steps.trigger.context](https://pipedream.com/docs/#steps-trigger-context)
-   [Limits on event history](https://pipedream.com/docs/#limits-on-event-history)

## [#](https://pipedream.com/docs/#selecting-a-test-event) Selecting a test event

When you test any step in your workflow, Pipedream passes the test event you select in the trigger step:

![Test event](https://pipedream.com/docs/assets/img/test-event.6b08af22.png)

You can select any event you've previously sent to your trigger as your test event, or send a new one.

## [#](https://pipedream.com/docs/#examining-event-data) Examining event data

When you select an event, you'll see [the incoming event data](https://pipedream.com/docs/#event-format) and the [event context](https://pipedream.com/docs/#steps-trigger-context) for that event:

![Event and context](https://pipedream.com/docs/assets/img/event-and-context.d151079c.png)

Pipedream parses your incoming data and exposes it in the variable [`steps.trigger.event`](https://pipedream.com/docs/#event-format), which you can access in any [workflow step](https://pipedream.com/docs/workflows/steps/).

## [#](https://pipedream.com/docs/#copying-references-to-event-data) Copying references to event data

When you're [examining event data](https://pipedream.com/docs/#examining-event-data), you'll commonly want to copy the name of the variable that points to the data you need to reference in another step.

Hover over the property whose data you want to reference, and click the **Copy Path** button to its right:

![Copy path GIF](https://pipedream.com/docs/assets/img/copy-path.ea06b4eb.gif)

## [#](https://pipedream.com/docs/#copying-the-values-of-event-data) Copying the values of event data

You can also copy the value of specific properties of your event data. Hover over the property whose data you want to copy, and click the **Copy Value** button to its right:

![Copy value GIF](https://pipedream.com/docs/assets/img/copy-value.24900812.gif)

## [#](https://pipedream.com/docs/#event-format) Event format

When you send an event to your workflow, Pipedream takes the trigger data — for example, the HTTP payload, headers, etc. — and adds our own Pipedream metadata to it.

**This data is exposed in the `steps.trigger.event` variable. You can reference this variable in any step of your workflow**.

You can reference your event data in any [code](https://pipedream.com/docs/code/) or [action](https://pipedream.com/docs/components/actions/) step. See those docs or the general [docs on passing data between steps](https://pipedream.com/docs/workflows/steps/) for more information.

The specific shape of `steps.trigger.event` depends on the trigger type:

### [#](https://pipedream.com/docs/#http) HTTP

| Property | Description |
| --- | --- |
| `body` | A string or object representation of the HTTP payload |
| `client_ip` | IP address of the client that made the request |
| `headers` | HTTP headers, represented as an object |
| `method` | HTTP method |
| `path` | HTTP request path |
| `query` | Query string |
| `url` | Request host + path |

### [#](https://pipedream.com/docs/#cron-scheduler) Cron Scheduler

| Property | Description |
| --- | --- |
| `interval_seconds` | The number of seconds between scheduled invocations |
| `cron` | When you've configured a custom cron schedule, the cron string |
| `timestamp` | The epoch timestamp when the workflow ran |
| `timezone_configured` | An object with formatted datetime data for the given invocation, tied to the schedule's timezone |
| `timezone_utc` | An object with formatted datetime data for the given invocation, tied to the UTC timezone |

### [#](https://pipedream.com/docs/#email) Email

We use Amazon SES to receive emails for the email trigger. You can find the shape of the event in the [SES docs (opens new window)](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-notifications-contents.html).

## [#](https://pipedream.com/docs/#steps-trigger-context) `steps.trigger.context`

`steps.trigger.event` contain your event's **data**. `steps.trigger.context` contains _metadata_ about the workflow and the invocation tied to this event.

You can use the data in `steps.trigger.context` to uniquely identify the Pipedream event ID, the timestamp at which the event invoked the workflow, and more:

| Property | Description |
| --- | --- |
| `deployment_id` | A globally-unique string representing the current version of the workflow |
| `id` | A unique, Pipedream-provided identifier for the event that triggered this workflow |
| `owner_id` | The Pipedream-assigned user ID for the owner of the workflow |
| `platform_version` | The version of the Pipedream execution environment this event ran on |
| `ts` | The ISO 8601 timestamp at which the event invoked the workflow |
| `workflow_id` | The workflow ID |
| `workflow_name` | The workflow name |

You may notice other properties in `context`. These are used internally by Pipedream, and are subject to change.

## [#](https://pipedream.com/docs/#limits-on-event-history) Limits on event history

Only the last 100 events are retained for each workflow. After 100 events have been processed, Pipedream will delete the oldest event data as new events arrive, keeping only the last 100 events.