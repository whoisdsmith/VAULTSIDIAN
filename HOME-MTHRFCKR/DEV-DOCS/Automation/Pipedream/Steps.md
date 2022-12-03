Steps are the building blocks you use to create workflows. You can easily combine multiple steps into a workflow to integrate your apps, data and APIs:

-   Steps include triggers, code and prebuilt actions.
    
-   Steps are executed linearly, in the order they appear in your workflow.
    
-   You can pass data between steps using `steps` objects.
    
-   You can observe the execution results for each step including export values, logs and errors.
    

-   [Types of Steps](https://pipedream.com/docs/#types-of-steps)
    -   [Trigger](https://pipedream.com/docs/#trigger)
    -   [Code, Actions](https://pipedream.com/docs/#code-actions)
-   [Step Names](https://pipedream.com/docs/#step-names)
-   [Passing data to steps from the workflow builder](https://pipedream.com/docs/#passing-data-to-steps-from-the-workflow-builder)
-   [Step Exports](https://pipedream.com/docs/#step-exports)

## [#](https://pipedream.com/docs/#types-of-steps) Types of Steps

### [#](https://pipedream.com/docs/#trigger) Trigger

Every workflow begins with a single [**trigger**](https://pipedream.com/docs/workflows/steps/triggers/) step. Trigger steps initiate the execution of a workflow; i.e., workflows execute on each trigger event. For example, you can create an [HTTP trigger](https://pipedream.com/docs/workflows/steps/triggers/#http) to accept HTTP requests. We give you a unique URL where you can send HTTP requests, and your workflow is executed on each request.

### [#](https://pipedream.com/docs/#code-actions) Code, Actions

[**Actions**](https://pipedream.com/docs/components/actions/) and [**code**](https://pipedream.com/docs/workflows/steps/code/) steps drive the logic of your workflow. Anytime your workflow runs, Pipedream will execute each step of your workflow in order. Actions are prebuilt code steps that let you connect to hundreds of APIs without writing code. When you need more control than the default actions provide, code steps let you write any custom Node.js code.

Code and action steps cannot precede triggers, since they'll have no data to operate on.

Once you save a workflow, we deploy it to our servers. Each event triggers the workflow code, whether you have the workflow open in your browser, or not.

## [#](https://pipedream.com/docs/#step-names) Step Names

Steps have names, which appear at the top of the step:

![Default step names](https://pipedream.com/docs/assets/img/step-name.7ec687c1.png)

When you [share data between steps](https://pipedream.com/docs/#step-exports), you'll use this name to reference that shared data. For example, `steps.trigger.event` contains the event that triggered your workflow. If you exported a property called `myData` from this code step, you'd reference that in other steps using `steps.nodejs.myData`. See the docs on [step exports](https://pipedream.com/docs/#step-exports) to learn more.

You can rename a step by clicking on its name and typing a new one in its place:

![New step name](https://pipedream.com/docs/assets/img/new-step-name.ad52b376.png)

After changing a step name, you'll need to update any references to the old step. In this example, you'd now reference this step as `steps.my_awesome_code_step`.

## [#](https://pipedream.com/docs/#passing-data-to-steps-from-the-workflow-builder) Passing data to steps from the workflow builder

You can generate form based inputs for steps using `props`. This allows the step reuse in across many workflows with different provided arguments - all without changing code.

Learn more about using `props` in our [Node.js code step documentation.](https://pipedream.com/docs/code/nodejs/#passing-props-to-code-steps)

WARNING

Passing props from the workflow builder to workflow steps are only available in Node.js code steps.

We do not currently offer this feature for Python, Bash or Go powered code steps.

## [#](https://pipedream.com/docs/#step-exports) Step Exports

Step exports allow you to pass data between steps. Any data exported from a step must be JSON serializable; the data must be able to stored as JSON so it can be read by downstream steps.

For examples of supported data types in your steps language, see the examples below.

-   [Node.js (Javascript)](https://pipedream.com/docs/code/nodejs/#sharing-data-between-steps)
-   [Python](https://pipedream.com/docs/code/python/#sharing-data-between-steps)
-   [Bash](https://pipedream.com/docs/code/bash/#sharing-data-between-steps)
-   [Go](https://pipedream.com/docs/code/go/#sharing-data-between-steps)