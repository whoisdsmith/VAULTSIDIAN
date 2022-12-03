Prefer to write quick scripts in Bash? We've got you covered.

You can run any Bash in a Pipedream step within your workflows.

## [#](https://pipedream.com/docs/#adding-a-bash-code-step) Adding a Bash code step

1.  Click the + icon to add a new step
2.  Click **Custom Code**
3.  In the new step, select the `bash` runtime in language dropdown

## [#](https://pipedream.com/docs/#logging-and-debugging) Logging and debugging

When it comes to debugging Bash scripts, `echo` is your friend.

Your `echo` statements will print their output in the workflow step results:

## [#](https://pipedream.com/docs/#available-binaries) Available binaries

Bash steps come with many common and useful binaries preinstalled and available in `$PATH` for you to use out of the box. These binaries include but aren't limited to:

-   `curl` for making HTTP requests
-   `jq` for manipulating and viewing JSON data
-   `git` for interacting with remote repositories

Unfortunately it is not possible to install packages from a package manager like `apt` or `yum`.

If you need a package pre-installed in your Bash steps, [just ask us (opens new window)](https://pipedream.com/support).

Otherwise, you can use the `/tmp` directory to download and install software from source.

## [#](https://pipedream.com/docs/#making-an-http-request) Making an HTTP request

`curl` is already preinstalled in Bash steps, we recommend using it for making HTTP requests in your code for sending or requesting data from APIs or webpages.

### [#](https://pipedream.com/docs/#making-a-get-request) Making a `GET` request

You can use `curl` to perform `GET` requests from websites or APIs directly.

TIP

Use the `--silent` flag with `curl` to suppress extra extra diagnostic information that `curl` produces when making requests.

This enables you to only worry about the body of the response so you can visualize it with tools like `echo` or `jq`.

### [#](https://pipedream.com/docs/#making-a-post-request) Making a `POST` request

`curl` can also make `POST`s requests as well. The `-X` flag allow you to specify the HTTP method you'd like to use for an HTTP request.

The `-d` flag is for passing data in the `POST` request.

### [#](https://pipedream.com/docs/#using-api-key-authentication) Using API key authentication

Some APIs require you to authenticate with a secret API key.

`curl` has an `-h` flag where you can pass your API key as a token.

For example, here's how to retrieve mentions from the Twitter API:

## [#](https://pipedream.com/docs/#sharing-data-between-steps) Sharing data between steps

A step can accept data from other steps in the same workflow, or pass data downstream to others.

### [#](https://pipedream.com/docs/#using-data-from-another-step) Using data from another step

In Bash steps, data from the initial workflow trigger and other steps are available in the `$PIPEDREAM_STEPS` environment variable.

In this example, we'll pretend this data is coming into our HTTP trigger via a POST request.

In our Bash script, we can access this data via the `$PIPEDREAM_STEPS` file. Specifically, this data from the POST request into our workflow is available in the `trigger` object.

TIP

The period (`.`) in front the `trigger.event` in the example is not a typo. This is to define the starting point for `jq` to traverse down the JSON in the HTTP response.

### [#](https://pipedream.com/docs/#sending-data-downstream-to-other-steps) Sending data downstream to other steps

To share data for future steps to use downstream, append it to the `$PIPEDREAM_EXPORTS` file.

WARNING

Not all data types can be stored in the `$PIPEDREAM_EXPORTS` data shared between workflow steps.

For the best experience, we recommend only exporting strings from Bash steps that can be serialized to JSON.

[Read more details on step limitations here.](https://pipedream.com/docs/workflows/steps/#limitations-on-step-exports)

## [#](https://pipedream.com/docs/#using-environment-variables) Using environment variables

You can leverage any [environment variables defined in your Pipedream account](https://pipedream.com/docs/environment-variables/#environment-variables) in a bash step. This is useful for keeping your secrets out of code as well as keeping them flexible to swap API keys without having to update each step individually.

To access them, just append the `$` in front of the environment variable name.

Or an even more useful example, using the stored environment variable to make an authenticated API request.

## [#](https://pipedream.com/docs/#raising-exceptions) Raising exceptions

You may need to stop your step immediately. You can use the normal `exit` function available in Bash to quit the step prematurely.

WARNING

Using `exit` to quit a Bash step early _won't_ stop the execution of the rest of the workflow.

Exiting a Bash step will only apply that particular step in the workflow.

This will exit the step and output the error message to `stderr` which will appear in the results of the step in the workflow.

## [#](https://pipedream.com/docs/#file-storage) File storage

If you need to download and store files, you can place them in the `/tmp` directory.

### [#](https://pipedream.com/docs/#writing-a-file-to-tmp) Writing a file to /tmp

For example, to download a file to `/tmp` using `curl`

WARNING

The `/tmp` directory does not have unlimited storage. Please refer to the [disk limits](https://pipedream.com/docs/limits/#disk) for details.