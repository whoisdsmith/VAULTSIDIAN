**Destinations**, like [actions](https://pipedream.com/docs/components/actions/), abstract the delivery and connection logic required to send events to services like Amazon S3, or targets like HTTP and email.

However, Destinations are different than actions in two ways:

-   **Events are delivered to the Destinations asynchronously**, after your workflow completes. This means you don't wait for network I/O (e.g. for HTTP requests or connection overhead for data warehouses) within your workflow code, so you can process more events faster.
-   In the case of data stores like S3, you typically don't want to send every event on its own. This can be costly and carries little benefit. **Instead, you typically want to batch a collection of events together, sending the batch at some frequency. Destinations handle that batching for relevant services**.

The docs below discuss features common to all Destinations. See the [docs for a given destination](https://pipedream.com/docs/#available-destinations) for information specific to those destinations.

-   [Available Destinations](https://pipedream.com/docs/#available-destinations)
-   [Using destinations](https://pipedream.com/docs/#using-destinations)
    -   [Using destinations in workflows](https://pipedream.com/docs/#using-destinations-in-workflows)
    -   [Using destinations in actions](https://pipedream.com/docs/#using-destinations-in-actions)
-   [Asynchronous Delivery](https://pipedream.com/docs/#asynchronous-delivery)

## [#](https://pipedream.com/docs/#available-destinations) Available Destinations

-   [HTTP](https://pipedream.com/docs/destinations/http/)
-   [Email](https://pipedream.com/docs/destinations/email/)
-   [S3](https://pipedream.com/docs/destinations/s3/)
-   [Pipedream Data Warehouse](https://pipedream.com/docs/destinations/sql/)
-   [SSE](https://pipedream.com/docs/destinations/sse/)

## [#](https://pipedream.com/docs/#using-destinations) Using destinations

### [#](https://pipedream.com/docs/#using-destinations-in-workflows) Using destinations in workflows

You can send data to Destinations in [Node.js code steps](https://pipedream.com/docs/workflows/steps/code/), too, using `$.send` functions.

`$.send` is an object provided by Pipedream that exposes destination-specific functions like `$.send.http()`, `$.send.s3()`, and more. **This allows you to send data to destinations programmatically, if you need more control than the default actions provide**.

Let's use `$.send.http()` to send an HTTP POST request like we did in the Action example above. [Add a new Action](https://pipedream.com/docs/components/actions/#adding-a-new-action), then search for "**Run Node.js code**":

[Create an endpoint URL (opens new window)](https://requestbin.com/), adding the code below to your code step, with the URL you created:

See the docs for the [HTTP destination](https://pipedream.com/docs/destinations/http/) to learn more about all the options you can pass to the `$.send.http()` function.

Again, it's important to remember that **Destination delivery is asynchronous**. If you iterate over an array of values and send an HTTP request for each:

you won't have to `await` the execution of the HTTP requests in your workflow. We'll collect every `$.send.http()` call and defer those HTTP requests, sending them after your workflow finishes.

### [#](https://pipedream.com/docs/#using-destinations-in-actions) Using destinations in actions

If you're authoring a [component action](https://pipedream.com/docs/components/actions/), you can deliver data to destinations, too. `$.send` isn't directly available to actions like it is for workflow code steps. **Instead, you use `$.send` to access the destination-specific functions**:

[See the component action API docs](https://pipedream.com/docs/components/api/#actions) for more details.

## [#](https://pipedream.com/docs/#asynchronous-delivery) Asynchronous Delivery

Events are delivered to destinations _asynchronously_ — that is, separate from the execution of your workflow. **This means you're not waiting for network or connection I/O in the middle of your function, which can be costly**.

Some destination payloads, like HTTP, are delivered within seconds. For other destinations, like S3 and SQL, we collect individual events into a batch and send the batch to the destination. See the [docs for a specific destination](https://pipedream.com/docs/#available-destinations) for the relevant batch delivery frequency.