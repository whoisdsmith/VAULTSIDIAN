**Anything you can do in Python can be done in a Pipedream Workflow**. This includes using any of the [350,000+ PyPi packages available (opens new window)](https://pypi.org/) in your Python powered workflows.

Pipedream supports [Python v3.8 (opens new window)](https://www.python.org/) in workflows.

## [#](https://pipedream.com/docs/#adding-a-python-code-step) Adding a Python code step

1.  Click the + icon to add a new step
2.  Click **Custom Code**
3.  In the new step, select the `python` language runtime in language dropdown

## [#](https://pipedream.com/docs/#logging-and-debugging) Logging and debugging

You can use `print` at any time in a Python code step to log information as the script is running.

The output for the `print` **logs** will appear in the `Results` section just beneath the code editor.

![Python print log output in the results](https://pipedream.com/docs/assets/img/print-logs.ac4a876a.png)

## [#](https://pipedream.com/docs/#using-third-party-packages) Using third party packages

You can use any packages from [PyPi (opens new window)](https://pypi.org/) in your Pipedream workflows. This includes popular choices such as:

-   [`requests` for making HTTP requests (opens new window)](https://pypi.org/project/requests/)
-   [`sqlalchemy`for retrieving or inserting data in a SQL database (opens new window)](https://pypi.org/project/sqlalchemy/)
-   [`pandas` for working with complex datasets (opens new window)](https://pypi.org/project/pandas/)

To use a PyPi package, just include it in your step's code:

And that's it.

No need to update a `requirements.txt` or specify elsewhere in your workflow of which packages you need. Pipedream will automatically install the dependency for you.

## [#](https://pipedream.com/docs/#making-an-http-request) Making an HTTP request

We recommend using the popular `requests` HTTP client package available in Python to send HTTP requests.

No need to run `pip install`, just `import requests` at the top of your step's code and it's available for your code to use.

### [#](https://pipedream.com/docs/#making-a-get-request) Making a `GET` request

GET requests typically are for retrieving data from an API. Below is an example.

### [#](https://pipedream.com/docs/#making-a-post-request) Making a POST request

### [#](https://pipedream.com/docs/#sending-files) Sending files

You can also send files within a step.

An example of sending a previously stored file in the workflow's `/tmp` directory:

## [#](https://pipedream.com/docs/#sharing-data-between-steps) Sharing data between steps

A step can accept data from other steps in the same workflow, or pass data downstream to others.

### [#](https://pipedream.com/docs/#using-data-from-another-step) Using data from another step

In Python steps, data from the initial workflow trigger and other steps are available in the `pipedream.script_helpers.export` module.

In this example, we'll pretend this data is coming into our HTTP trigger via POST request.

In our Python step, we can access this data in the `exports` variable from the `pipedream.script_helpers` module. Specifically, this data from the POST request into our workflow is available in the `trigger` dictionary item.

### [#](https://pipedream.com/docs/#sending-data-downstream-to-other-steps) Sending data downstream to other steps

To share data created, retrieved, transformed or manipulated by a step to others downstream call the `export` module from `pipedream.script_helpers`.

Now this `pokemon` data is accessible to downstream steps within `steps["code"]["pokemon"]`

WARNING

Not all data types can be stored in the `steps` data shared between workflow steps.

For the best experience, we recommend only exporting these types of data from Python steps:

-   lists
-   dictionaries

[Read more details on step limitations here.](https://pipedream.com/docs/workflows/steps/#limitations-on-step-exports)

## [#](https://pipedream.com/docs/#using-environment-variables) Using environment variables

You can leverage any [environment variables defined in your Pipedream account](https://pipedream.com/docs/environment-variables/#environment-variables) in a Python step. This is useful for keeping your secrets out of code as well as keeping them flexible to swap API keys without having to update each step individually.

To access them, use the `os` module.

Or an even more useful example, using the stored environment variable to make an authenticated API request.

### [#](https://pipedream.com/docs/#using-api-key-authentication) Using API key authentication

If an particular service requires you to use an API key, you can pass it via the headers of the request.

This proves your identity to the service so you can interact with it:

TIP

There are 2 different ways of using the `os` module to access your environment variables.

`os.environ['ENV_NAME_HERE']` will raise an error that stops your workflow if that key doesn't exist in your Pipedream account.

Whereas `os.environ.get('ENV_NAME_HERE')` will _not_ throw an error and instead returns an empty string.

If your code relies on the presence of a environment variable, consider using `os.environ['ENV_NAME_HERE']` instead.

## [#](https://pipedream.com/docs/#handling-errors) Handling errors

You may need to exit a workflow early. In a Python step, just a `raise` an error to halt a step's execution.

All exceptions from your Python code will appear in the **logs** area of the results.

## [#](https://pipedream.com/docs/#file-storage) File storage

You can also store and read files with Python steps. This means you can upload photos, retrieve datasets, accept files from an HTTP request and more.

The `/tmp` directory is accessible from your workflow steps for saving and retrieving files.

You have full access to read and write both files in `/tmp`.

### [#](https://pipedream.com/docs/#writing-a-file-to-tmp) Writing a file to /tmp

Now `/tmp/python-logo.png` holds the official Python logo.

### [#](https://pipedream.com/docs/#reading-a-file-from-tmp) Reading a file from /tmp

You can also open files you have previously stored in the `/tmp` directory. Let's open the `python-logo.png` file.

### [#](https://pipedream.com/docs/#listing-files-in-tmp) Listing files in /tmp

If you need to check what files are currently in `/tmp` you can list them and print the results to the **Logs** section of **Results**:

WARNING

The `/tmp` directory does not have unlimited storage. Please refer to the [disk limits](https://pipedream.com/docs/limits/#disk) for details.