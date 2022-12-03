**Anything you can do in Go, you can do in a Pipedream Workflow**. You can use any of [Go packages available (opens new window)](https://pkg.go.dev/) with a simple `import` no `go get` needed.

Pipedream supports [Go v1.17.1 (opens new window)](https://go.dev/) in workflows.

## [#](https://pipedream.com/docs/#adding-a-go-code-step) Adding a Go code step

1.  Click the + icon to add a new step
2.  Click "Custom Code"
3.  In the new step, select the `golang` language runtime in language dropdown

## [#](https://pipedream.com/docs/#logging-and-debugging) Logging and debugging

You can use `fmt.Println` at any time to log information as the script is running.

The output for the `fmt.Println` **Logs** will appear in the `Results` section just beneath the code editor.

TIP

Don't forget to import the `fmt` package in order to run `fmt.Println`.

## [#](https://pipedream.com/docs/#using-third-party-packages) Using third party packages

You can use any packages from [Go package registry (opens new window)](https://pkg.go.dev/). This includes popular choices such as:

-   [`net/http` for making HTTP requests (opens new window)](https://pkg.go.dev/net/http#pkg-overview/)
-   [`encoding/json` for encoding and decoding JSON (opens new window)](https://pkg.go.dev/encoding/json)
-   [`database/sql` for reading and writing to SQL databases (opens new window)](https://pkg.go.dev/database/sql@go1.17.6)

To use a Go package, just `import` it in your step's code:

And that's it.

## [#](https://pipedream.com/docs/#making-an-http-request) Making an HTTP request

We recommend using the `http` HTTP client package included in the Go Standard Library for making HTTP requests.

### [#](https://pipedream.com/docs/#making-a-get-request) Making a `GET` request

You'll typically use `GET` requests to retrieve data from an API:

### [#](https://pipedream.com/docs/#making-a-post-request) Making a `POST` request

### [#](https://pipedream.com/docs/#sending-files) Sending files

You can send files stored in the `/tmp` directory in an HTTP request:

## [#](https://pipedream.com/docs/#sharing-data-between-steps) Sharing data between steps

A step can accept data from other steps in the same workflow, or pass data downstream to others.

This makes your steps even more powerful, you can compose new workflows and reuse steps.

### [#](https://pipedream.com/docs/#using-data-from-another-step) Using data from another step

Data from the initial workflow trigger and other steps are available in the `pipedream-go` package.

In this example, we'll pretend this data is coming into our HTTP trigger via POST request.

You can access this data in the `Steps` variable from the `pd` package. Specifically, this data from the POST request into our workflow is available in the `trigger` map.

### [#](https://pipedream.com/docs/#sending-data-downstream-to-other-steps) Sending data downstream to other steps

To share data for future steps to use, call the Export function from pd package:

Now this `pokemon` data is accessible to downstream steps within `pd.Steps["code"]["pokemon"]`

## [#](https://pipedream.com/docs/#using-environment-variables) Using environment variables

You can leverage any [environment variables defined in your Pipedream account](https://pipedream.com/docs/environment-variables/#environment-variables) in a Go step. This is useful for keeping your secrets out of code as well as keeping them flexible to swap API keys without having to update each step individually.

To access them, use the `os` package.

### [#](https://pipedream.com/docs/#using-api-key-authentication) Using API key authentication

If a particular service requires you to use an API key, you can pass it via the HTTP request.

This proves your identity to the service so you can interact with it:

## [#](https://pipedream.com/docs/#handling-errors) Handling errors

You may need to exit a workflow early, use the `os.Exit` to exit the `main` function with a specific error code.

The step will quit at the time `os.Exit` is called. In this example, the exit code `1` will appear in the **Results** of the step.

## [#](https://pipedream.com/docs/#file-storage) File storage

You can also store and read files with Go steps. This means you can upload photos, retrieve datasets, accept files from an HTTP request and more.

The `/tmp` directory is accessible from your workflow steps for saving and retrieving files.

You have full access to read and write both files in `/tmp`.

### [#](https://pipedream.com/docs/#writing-a-file-to-tmp) Writing a file to `/tmp`

Now `/tmp/go-logo.svg` holds the official Go logo.

### [#](https://pipedream.com/docs/#reading-a-file-from-tmp) Reading a file from /tmp

You can also open files you have previously stored in the `/tmp` directory. Let's open the `go-logo.svg` file.

### [#](https://pipedream.com/docs/#tmp-limitations) `/tmp` limitations

The `/tmp` directory can store up to 512MB of storage. Also the storage may be wiped or may not exist between workflow executions.

To avoid errors, assume that the `/tmp` directory is empty between workflow runs.