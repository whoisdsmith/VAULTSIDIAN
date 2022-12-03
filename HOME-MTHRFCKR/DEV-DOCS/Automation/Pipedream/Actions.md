Actions are reusable code steps that integrate your apps, data and APIs. For example, you can send HTTP requests to an external service using our HTTP actions, or use our Google Sheets actions to add new data. You can use thousands of actions across 400+ apps today.

Typically, integrating with these services requires custom code to manage connection logic, error handling, and more. Actions handle that for you. You only need to specify the parameters required for the action. For example, the HTTP `GET` Request action requires you enter the URL whose data you want to retrieve.

**You can also create your own actions that can be shared across your own workflows, or published to all Pipedream users**.

-   [Using Existing Actions](https://pipedream.com/docs/#using-existing-actions)
-   [Updating actions to the latest version](https://pipedream.com/docs/#updating-actions-to-the-latest-version)
-   [Creating your own actions](https://pipedream.com/docs/#creating-your-own-actions)
-   [Reporting a bug / feature request](https://pipedream.com/docs/#reporting-a-bug-feature-request)

## [#](https://pipedream.com/docs/#using-existing-actions) Using Existing Actions

Adding existing actions to your workflow is easy:

1.  Click the **+** button below any step.
2.  Search for the app you're looking for and select it from the list.
3.  Search for the action and select it to add it to your workflow.

For example, here's how to add the HTTP `GET` Request action:

![Adding HTTP GET request action](https://pipedream.com/docs/assets/img/adding-http-get-request-action.c49f3773.gif)

## [#](https://pipedream.com/docs/#updating-actions-to-the-latest-version) Updating actions to the latest version

When you use existing actions or create your own, you'll often want to update an action you added to a workflow to the newest version. For example, the community might publish a new feature or bug fix that you want to use.

To update your action to the latest version, hover over the step in your workflow and click the icon with two arrows in a circle:

![Update action](https://pipedream.com/docs/assets/img/update-action.ce6763a1.png)

## [#](https://pipedream.com/docs/#creating-your-own-actions) Creating your own actions

You can author your own actions on Pipedream, too. Anytime you need to reuse the same code across steps, consider making that an action.

Start with our [action development quickstart](https://pipedream.com/docs/components/quickstart/nodejs/actions/). You can read more about all the capabilities of actions in [our API docs](https://pipedream.com/docs/components/api/), and review [example actions here](https://pipedream.com/docs/components/api/#example-components).

You can also publish actions to [the Pipedream registry](https://pipedream.com/docs/components/guidelines/#pipedream-registry), which makes them available for anyone on Pipedream to use.

## [#](https://pipedream.com/docs/#reporting-a-bug-feature-request) Reporting a bug / feature request

If you'd like to report a bug, request a new action, or submit a feature request for an existing action, [open an issue in our GitHub repo (opens new window)](https://github.com/pipedreamhq/pipedream).