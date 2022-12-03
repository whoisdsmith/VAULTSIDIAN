**Environment variables** enable you to separate secrets and other data from your code.

You should not include API keys or other sensitive data directly in your workflow's code. This is especially important if you [make your workflow public](https://pipedream.com/docs/public-workflows/), since anyone would be able to see your API key in plain sight. By referencing the value of an environment variable, instead, your workflow includes a reference to that variable — `process.env.API_KEY` — instead of the API key itself.

Environment variables are defined at the account-level, and can be referenced in [workflow code](https://pipedream.com/docs/workflows/steps/code/) or [step params](https://pipedream.com/docs/workflows/steps/params/).

-   [Creating, updating environment variables](https://pipedream.com/docs/#creating-updating-environment-variables)
-   [Referencing environment variables in code](https://pipedream.com/docs/#referencing-environment-variables-in-code)
-   [Referencing environment variables in actions](https://pipedream.com/docs/#referencing-environment-variables-in-actions)
-   [Copying workflows that use environment variables](https://pipedream.com/docs/#copying-workflows-that-use-environment-variables)
-   [Limits](https://pipedream.com/docs/#limits)

## [#](https://pipedream.com/docs/#creating-updating-environment-variables) Creating, updating environment variables

Environment variables are managed at the account-level. You can access your environment variables at [https://pipedream.com/settings/env-vars](https://pipedream.com/settings/env-vars).

To add an environment variable, click the **New Environment Variable** button.

To edit an environment variable, click the **Reveal / Edit** button next to a specific variable.

Updates to environment variables will be made available to your workflows as soon as the save operation is complete — typically a few seconds after you click **Save**. If you update the value of an environment variable in the UI, your workflow should automatically use that new value where it's referenced.

## [#](https://pipedream.com/docs/#referencing-environment-variables-in-code) Referencing environment variables in code

You can reference the value of any environment variable using the object [`process.env` (opens new window)](https://nodejs.org/dist/latest-v10.x/docs/api/process.html#process_process_env). This object contains environment variables as key-value pairs.

For example, let's say you have an environment variable named `API_KEY`. You can reference its value using `process.env.API_KEY`:

Variable names are case-sensitive. Use the name you defined in your Environment settings in the app when referencing your variable in `process.env`.

Referencing an environment variable that doesn't exist returns the value `undefined` in Node.js. For example, if you try to reference `process.env.API_KEY` without first defining the `API_KEY` variable in your environment settings, it will return the value `undefined`.

WARNING

Logging the value of any environment variables — for example, using `console.log` — will include that value in the logs associated with the cell. Please keep this in mind and take care not to print the values of sensitive secrets.

## [#](https://pipedream.com/docs/#referencing-environment-variables-in-actions) Referencing environment variables in actions

[Actions](https://pipedream.com/docs/components/actions/) are prebuilt code steps that provide a form for passing [params](https://pipedream.com/docs/workflows/steps/params/) as input.

You can reference the value of environment variables using `{{process.env.YOUR_ENV_VAR}}`. You'll see a list of your environment variables in the [object explorer](https://pipedream.com/docs/workflows/steps/params/#use-the-object-explorer):

![Environment variables in the object explorer](https://pipedream.com/docs/assets/img/env-vars-object-explorer.e7dec525.png)

## [#](https://pipedream.com/docs/#copying-workflows-that-use-environment-variables) Copying workflows that use environment variables

Your environment variables are made available to any running workflow. **If you copy a public workflow that uses an environment variable, make sure you review the code to see what environment variables it's using**.

Reviewing the code ensures you have the necessary variables defined for the workflow to run correctly, and makes sure the original workflow author isn't reading variables that you don't need for the workflow to function. You can always modify the code for the workflow after copying to remove these variables, or change their names.

## [#](https://pipedream.com/docs/#limits) Limits

Currently, **environment variables are only exposed in Pipedream workflows, [not event sources (opens new window)](https://github.com/PipedreamHQ/pipedream/issues/583)**.

The value of any environment variable may be no longer than `64KB`.

The names of environment variables must start with a letter or underscore. Pipedream also reserves environment variables that start with `PIPEDREAM_` for internal use. You cannot create an environment variable that begins with that prefix.