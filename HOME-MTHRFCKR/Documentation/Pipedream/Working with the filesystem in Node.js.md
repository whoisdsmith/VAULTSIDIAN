You'll commonly need to work with files in a workflow, for example: downloading content from some service to upload to another. This doc explains how to work with files in Pipedream workflows and provides some sample code for common operations.

-   [The /tmp directory](https://pipedream.com/docs/#the-tmp-directory)
-   [Managing /tmp across workflow runs](https://pipedream.com/docs/#managing-tmp-across-workflow-runs)
-   [Writing a file to /tmp](https://pipedream.com/docs/#writing-a-file-to-tmp)
-   [Listing files in /tmp](https://pipedream.com/docs/#listing-files-in-tmp)
-   [Reading a file from /tmp](https://pipedream.com/docs/#reading-a-file-from-tmp)
-   [Delete a file](https://pipedream.com/docs/#delete-a-file)
-   [Download a file to /tmp](https://pipedream.com/docs/#download-a-file-to-tmp)
-   [Upload a file from /tmp](https://pipedream.com/docs/#upload-a-file-from-tmp)
-   [Download a file, uploading it in another multipart/form-data request](https://pipedream.com/docs/#download-a-file-uploading-it-in-another-multipart-form-data-request)
-   [Download email attachments to /tmp, upload to Amazon S3](https://pipedream.com/docs/#download-email-attachments-to-tmp-upload-to-amazon-s3)

## [#](https://pipedream.com/docs/#the-tmp-directory) The `/tmp` directory

Within a workflow, you have full read-write access to the `/tmp` directory. You have `512 MB` of available space in `/tmp` to save any file.

## [#](https://pipedream.com/docs/#managing-tmp-across-workflow-runs) Managing `/tmp` across workflow runs

The `/tmp` directory is stored on the virtual machine that runs your workflow. We call this the execution environment ("EE"). More than one EE may be created to handle high-volume workflows. And EEs can be destroyed at any time (for example, after about 10 minutes of receiving no events). This means that you should not expect to have access to files across invocations. At the same time, files _may_ remain, so you should clean them up to make sure that doesn't affect your workflow. **Use [the `tmp-promise` package (opens new window)](https://github.com/benjamingr/tmp-promise) to cleanup files after use, or [delete the files manually](https://pipedream.com/docs/#delete-a-file).**

## [#](https://pipedream.com/docs/#writing-a-file-to-tmp) Writing a file to `/tmp`

Use the [`fs` module (opens new window)](https://nodejs.org/api/fs.html) to write data to `/tmp`:

## [#](https://pipedream.com/docs/#listing-files-in-tmp) Listing files in `/tmp`

Return a list of the files saved in `/tmp`:

## [#](https://pipedream.com/docs/#reading-a-file-from-tmp) Reading a file from `/tmp`

This example uses [step exports](https://pipedream.com/docs/workflows/steps/#step-exports) to return the contents of a test file saved in `/tmp`, returned as a string ([`fs.readFileSync` returns a `Buffer` (opens new window)](https://nodejs.org/api/fs.html#fs_fs_readfilesync_path_options)):

## [#](https://pipedream.com/docs/#delete-a-file) Delete a file

## [#](https://pipedream.com/docs/#download-a-file-to-tmp) Download a file to `/tmp`

[See this example](https://pipedream.com/docs/workflows/steps/code/nodejs/http-requests/#download-a-file-to-the-tmp-directory) to learn how to download a file to `/tmp`.

## [#](https://pipedream.com/docs/#upload-a-file-from-tmp) Upload a file from `/tmp`

[See this example](https://pipedream.com/docs/workflows/steps/code/nodejs/http-requests/#upload-a-file-from-the-tmp-directory) to learn how to upload a file from `/tmp` in an HTTP request.

## [#](https://pipedream.com/docs/#download-a-file-uploading-it-in-another-multipart-form-data-request) Download a file, uploading it in another `multipart/form-data` request

[This workflow (opens new window)](https://pipedream.com/@dylburger/download-file-then-upload-file-via-multipart-form-data-request-p_QPCx7p/edit) provides an example of how to download a file at a specified **Download URL**, uploading that file to an **Upload URL** as form data.

## [#](https://pipedream.com/docs/#download-email-attachments-to-tmp-upload-to-amazon-s3) Download email attachments to `/tmp`, upload to Amazon S3

[This workflow (opens new window)](https://pipedream.com/@dylan/upload-email-attachments-to-s3-p_V9CGAQ/edit) is triggered by incoming emails. When copied, you'll get a workflow-specific email address you can send any email to. This workflow takes any attachments included with inbound emails, saves them to `/tmp`, and uploads them to Amazon S3.

You should also be aware of the [inbound payload limits](https://pipedream.com/docs/limits/#email-triggers) associated with the email trigger.