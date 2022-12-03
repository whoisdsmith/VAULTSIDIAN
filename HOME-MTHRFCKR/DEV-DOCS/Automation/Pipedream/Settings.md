You can control workflow-specific settings in the **Settings** header, just above your workflow's code.

![Workflow settings](https://pipedream.com/docs/assets/img/workflow-settings.f3a1c0b6.png)

-   [Errors](https://pipedream.com/docs/#errors)
-   [Execution Controls](https://pipedream.com/docs/#execution-controls)
    -   [Execution Timeout Limit](https://pipedream.com/docs/#execution-timeout-limit)
    -   [Memory](https://pipedream.com/docs/#memory)
    -   [Concurrency and Throttling](https://pipedream.com/docs/#concurrency-and-throttling)
-   [Attachments](https://pipedream.com/docs/#attachments)
    -   [Limits](https://pipedream.com/docs/#limits)

## [#](https://pipedream.com/docs/#errors) Errors

By default, any errors raised in a workflow are sent to the **Global Error Workflow**. This workflow sends you an email with the details of this error, once per error, per workflow, per 24-hour period.

But the Global Error Workflow is just another workflow, and lives in your account. So you can modify it however you'd like. For example, you can send errors to Slack, or send critical issues to Pagerduty, or log all errors to a table in the [SQL service](https://pipedream.com/docs/destinations/sql/) for later analysis.

## [#](https://pipedream.com/docs/#execution-controls) Execution Controls

### [#](https://pipedream.com/docs/#execution-timeout-limit) Execution Timeout Limit

Workflows have a default [execution limit](https://pipedream.com/docs/limits/#time-per-execution), which defines the time workflows can run for a single invocation until they're timed out.

If your workflow times out, and needs to run for longer than the [default limit](https://pipedream.com/docs/limits/#time-per-execution), you can change that limit here.

### [#](https://pipedream.com/docs/#memory) Memory

By default, workflows run with `256MB` of memory. If you're processing a lot of data in memory, you might need to raise that limit. Here, you can increase the memory of your workflow up to `10GB`.

**Pipedream charges invocations proportional to your memory configuration**. When you modify your memory settings, Pipedream will show you the number of invocations you'll be charged per execution. [Read more here](https://pipedream.com/docs/pricing/#how-does-workflow-memory-affect-billable-invocations).

### [#](https://pipedream.com/docs/#concurrency-and-throttling) Concurrency and Throttling

[Manage the concurrency and rate](https://pipedream.com/docs/workflows/events/concurrency-and-throttling/) at which events from a source trigger your workflow code.

## [#](https://pipedream.com/docs/#attachments) Attachments

Sometimes, you'll need to reference static files in your workflow, like a CSV. Files uploaded in the **Attachments** section can be referenced in your workflow using the `$attachments` object.

For example, if you upload a file named `test.csv`, Pipedream will expose the _file path_ of the uploaded file at `$attachments["test.csv"]`. You can read the contents of the file using `fs.readFileSync`:

![File attachment data](https://pipedream.com/docs/assets/img/attachment-file-data.0b64dfcb.png)

### [#](https://pipedream.com/docs/#limits) Limits

Each attachment is limited to `10MB` in size. The total size of all attachments within a single workflow cannot exceed `200MB`.