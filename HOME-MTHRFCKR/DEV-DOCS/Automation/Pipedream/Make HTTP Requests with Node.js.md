HTTP requests are fundamental to working with APIs or other web services. You can make HTTP requests to retrieve data from APIs, fetch HTML from websites, or do pretty much anything your web browser can do.

**Below, we'll review how to make HTTP requests using Node.js code on Pipedream.**

We'll use the [`axios` (opens new window)](https://github.com/axios/axios) and [`got` (opens new window)](https://github.com/sindresorhus/got) HTTP clients in the examples below, but [you can use any npm package you'd like](https://pipedream.com/docs/workflows/steps/code/#using-npm-packages) on Pipedream, so feel free to experiment with other clients, too.

If you're developing Pipedream components, you may find the [`@pipedream/platform` version of `axios`](https://pipedream.com/docs/pipedream-axios/) helpful for displaying error data clearly in the Pipedream UI.

If you're new to HTTP, see our [glossary of HTTP terms (opens new window)](https://requestbin.com/blog/working-with-webhooks/#webhooks-glossary-common-terms) for a helpful introduction.

-   [Basic axios usage notes](https://pipedream.com/docs/#basic-axios-usage-notes)
-   [Send a GET request to fetch data](https://pipedream.com/docs/#send-a-get-request-to-fetch-data)
-   [Send a POST request to submit data](https://pipedream.com/docs/#send-a-post-request-to-submit-data)
-   [Pass query string parameters to a GET request](https://pipedream.com/docs/#pass-query-string-parameters-to-a-get-request)
-   [Send a request with HTTP headers](https://pipedream.com/docs/#send-a-request-with-http-headers)
-   [Send a request with a secret or API key](https://pipedream.com/docs/#send-a-request-with-a-secret-or-api-key)
-   [Send multiple HTTP requests in sequence](https://pipedream.com/docs/#send-multiple-http-requests-in-sequence)
-   [Send multiple HTTP requests in parallel](https://pipedream.com/docs/#send-multiple-http-requests-in-parallel)
-   [Send a multipart/form-data request](https://pipedream.com/docs/#send-a-multipart-form-data-request)
-   [Download a file to the /tmp directory](https://pipedream.com/docs/#download-a-file-to-the-tmp-directory)
-   [Upload a file from the /tmp directory](https://pipedream.com/docs/#upload-a-file-from-the-tmp-directory)
-   [Use an HTTP proxy to proxy requests through another host](https://pipedream.com/docs/#use-an-http-proxy-to-proxy-requests-through-another-host)
-   [IP addresses for HTTP requests made from Pipedream workflows](https://pipedream.com/docs/#ip-addresses-for-http-requests-made-from-pipedream-workflows)
-   [Stream a downloaded file directly to another URL](https://pipedream.com/docs/#stream-a-downloaded-file-directly-to-another-url)
-   [Catch and process HTTP errors](https://pipedream.com/docs/#catch-and-process-http-errors)
-   [Paginating API requests](https://pipedream.com/docs/#paginating-api-requests)

## [#](https://pipedream.com/docs/#basic-axios-usage-notes) Basic `axios` usage notes

To use `axios` on Pipedream, you'll just need to import the `axios` npm package:

You make HTTP requests by passing a [JavaScript object (opens new window)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects) to `axios` that defines the parameters of the request. For example, you'll typically want to define the HTTP method and the URL you're sending data to:

`axios` returns a [Promise (opens new window)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises), which is just a fancy way of saying that it makes the HTTP request in the background (asynchronously) while the rest of your code runs. On Pipedream, [all asynchronous code must be run synchronously](https://pipedream.com/docs/workflows/steps/code/async/), which means you'll need to wait for the HTTP request to finish before moving on to the next step. You do this by adding an `await` in front of the call to `axios`.

**Putting all of this together, here's how to make a basic HTTP request on Pipedream:**

The response object `resp` contains a lot of information about the response: its data, headers, and more. Typically, you just care about the data, which you can access in the `data` property of the response:

Alternatively, you can access the data using [object destructuring (opens new window)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Object_destructuring), which is equivalent to the above and preferred in modern JavaScript:

## [#](https://pipedream.com/docs/#send-a-get-request-to-fetch-data) Send a `GET` request to fetch data

Make a request to retrieve Star Wars films from the Star Wars API:

[Copy this workflow to run this example on Pipedream (opens new window)](https://pipedream.com/@dylburger/make-an-http-get-request-to-the-star-wars-api-p_OKC2KA/edit).

## [#](https://pipedream.com/docs/#send-a-post-request-to-submit-data) Send a `POST` request to submit data

POST sample JSON to [JSONPlaceholder (opens new window)](https://jsonplaceholder.typicode.com/), a free mock API service:

When you make a `POST` request, you pass `POST` as the `method`, and include the data you'd like to send in the `data` object.

[Copy this workflow to run this example on Pipedream (opens new window)](https://pipedream.com/@dylburger/make-an-http-post-request-using-axios-p_o7CbpY/edit).

## [#](https://pipedream.com/docs/#pass-query-string-parameters-to-a-get-request) Pass query string parameters to a `GET` request

Retrieve fake comment data on a specific post using [JSONPlaceholder (opens new window)](https://jsonplaceholder.typicode.com/), a free mock API service. Here, you fetch data from the `/comments` resource, retrieving data for a specific post by query string parameter: `/comments?postId=1`.

You should pass query string parameters using the `params` object, like above. When you do, `axios` automatically [URL-encodes (opens new window)](https://www.w3schools.com/tags/ref_urlencode.ASP) the parameters for you, which you'd otherwise have to do manually.

[Copy this workflow to run this code on Pipedream (opens new window)](https://pipedream.com/@dylburger/pass-query-string-parameters-to-an-http-get-request-p_xMCOvj/edit).

You pass HTTP headers in the `headers` object of the `axios` request:

## [#](https://pipedream.com/docs/#send-a-request-with-a-secret-or-api-key) Send a request with a secret or API key

Most APIs require you authenticate HTTP requests with an API key or other token. **Please review the docs for your service to understand how they accept this data.**

Here's an example showing an API key passed in an HTTP header:

[Copy this workflow to run this code on Pipedream (opens new window)](https://pipedream.com/@dylburger/send-an-http-request-with-headers-p_q6ClzO/edit).

## [#](https://pipedream.com/docs/#send-multiple-http-requests-in-sequence) Send multiple HTTP requests in sequence

There are many ways to make multiple HTTP requests. This code shows you a simple example that sends the numbers `1`, `2`, and `3` in the body of an HTTP POST request:

This sends each HTTP request _in sequence_, one after another, and returns an array of response data returned from the URL to which you send the POST request. If you need to make requests _in parallel_, [see these docs](https://pipedream.com/docs/#send-multiple-http-requests-in-parallel).

[Copy this workflow (opens new window)](https://pipedream.com/@dylburger/iterate-over-a-pipedream-step-export-sending-multiple-http-requests-p_ljCAPN/edit) and fill in your destination URL to see how this works. **This workflow iterates over the value of a Pipedream [step export](https://pipedream.com/docs/workflows/steps/#step-exports)** - data returned from a previous step. Since you often want to iterate over data returned from a Pipedream action or other code step, this is a common use case.

## [#](https://pipedream.com/docs/#send-multiple-http-requests-in-parallel) Send multiple HTTP requests in parallel

Sometimes you'll want to make multiple HTTP requests in parallel. If one request doesn't depend on the results of another, this is a nice way to save processing time in a workflow. It can significantly cut down on the time you spend waiting for one request to finish, and for the next to begin.

To make requests in parallel, you can use two techniques. By default, we recommend using [`promise.allSettled` (opens new window)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/allSettled), which makes all HTTP requests and returns data on their success / failure. If an HTTP request fails, all other requests will proceed.

First, we generate an array of `axios.get` requests (which are all [Promises (opens new window)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)), and then call `Promise.allSettled` to run them in parallel.

When you want to stop future requests when _one_ of the requests fails, you can use [`Promise.all` (opens new window)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all), instead:

The Mozilla docs expand on the difference between these methods, and when you may want to use one or the other:

> The `Promise.allSettled()` method returns a promise that resolves after all of the given promises have either fulfilled or rejected, with an array of objects that each describes the outcome of each promise.
> 
> It is typically used when you have multiple asynchronous tasks that are not dependent on one another to complete successfully, or you'd always like to know the result of each promise.
> 
> In comparison, the Promise returned by `Promise.all()` may be more appropriate if the tasks are dependent on each other / if you'd like to immediately reject upon any of them rejecting.

## [#](https://pipedream.com/docs/#send-a-multipart-form-data-request) Send a `multipart/form-data` request

[Copy this workflow (opens new window)](https://pipedream.com/@dylburger/send-a-multipart-form-data-request-p_WxCQRyr/edit) to run this example.

## [#](https://pipedream.com/docs/#download-a-file-to-the-tmp-directory) Download a file to the `/tmp` directory

This example shows you how to download a file to a file in [the `/tmp` directory](https://pipedream.com/docs/workflows/steps/code/nodejs/working-with-files/). This can be especially helpful for downloading large files: it streams the file to disk, minimizing the memory the workflow uses when downloading the file.

[Copy this workflow (opens new window)](https://pipedream.com/@dylburger/download-a-file-from-a-url-to-tmp-p_pWCYA8y/edit) to run this example.

## [#](https://pipedream.com/docs/#upload-a-file-from-the-tmp-directory) Upload a file from the `/tmp` directory

This example shows you how to make a `multipart/form-data` request with a file as a form part. You can store and read any files from [the `/tmp` directory](https://pipedream.com/docs/workflows/steps/code/nodejs/working-with-files/).

This can be especially helpful for uploading large files: it streams the file from disk, minimizing the memory the workflow uses when uploading the file.

[Copy this workflow (opens new window)](https://pipedream.com/@dylburger/stream-a-file-upload-p_6lC1d2Z/edit) to run this example.

## [#](https://pipedream.com/docs/#use-an-http-proxy-to-proxy-requests-through-another-host) Use an HTTP proxy to proxy requests through another host

When you make HTTP requests to certain services, they might require you whitelist a set of IP addresses those requests come from. Often, this is to improve the security of the target service.

By default, HTTP requests made from Pipedream can come from a range of IP addresses. **If you need to make requests from a single IP address, you can route traffic through an HTTP proxy**:

**If you don't have access to an HTTP proxy, and you are a paying Pipedream customer, [reach out to our team (opens new window)](https://pipedream.com/support)**. We operate a proxy that you can use for HTTP requests made through Pipedream.

[Copy this workflow to run this code on Pipedream (opens new window)](https://pipedream.com/@dylburger/make-an-http-request-through-a-proxy-p_ezC6RD/edit).

## [#](https://pipedream.com/docs/#ip-addresses-for-http-requests-made-from-pipedream-workflows) IP addresses for HTTP requests made from Pipedream workflows

By default, [HTTP requests made from Pipedream can come from a large range of IP addresses](https://pipedream.com/docs/workflows/networking/). **If you need to restrict the IP addresses HTTP requests come from, you have two options**:

-   [Use an HTTP proxy to proxy requests](https://pipedream.com/docs/#use-an-http-proxy-to-proxy-requests-through-another-host)
-   If you don't need to access the HTTP response data, you can [use `$send.http()`](https://pipedream.com/docs/destinations/http/) to send requests from a [limited set of IP addresses](https://pipedream.com/docs/destinations/http/#ip-addresses-for-pipedream-http-requests).

## [#](https://pipedream.com/docs/#stream-a-downloaded-file-directly-to-another-url) Stream a downloaded file directly to another URL

Sometimes you need to upload a downloaded file directly to another service, without processing the downloaded file. You could [download the file](https://pipedream.com/docs/#download-a-file-to-the-tmp-directory) and then [upload it](https://pipedream.com/docs/#upload-a-file-from-the-tmp-directory) to the other URL, but these intermediate steps are unnecessary: you can just stream the download to the other service directly, without saving the file to disk.

This method is especially effective for large files that exceed the [limits of the `/tmp` directory](https://pipedream.com/docs/limits/#disk).

[Copy this workflow (opens new window)](https://pipedream.com/@dylburger/stream-download-to-upload-p_5VCLoa1/edit) or paste this code into a [new Node.js code step](https://pipedream.com/docs/workflows/steps/code/#adding-a-code-step):

You'll want to replace `https://example.com` with the URL you'd like to stream data from, and replace `https://example2.com` with the URL you'd like to send the data _to_. `got` streams the content directly, downloading the file using a `GET` request and uploading it as a `POST` request.

If you need to modify this behavior, [see the `got` Stream API (opens new window)](https://github.com/sindresorhus/got#gotstreamurl-options).

## [#](https://pipedream.com/docs/#catch-and-process-http-errors) Catch and process HTTP errors

By default, `axios` throws an error when the HTTP response code is in the 400-500 range (a client or server error). If you'd like to process the error data instead of throwing an error, you can pass a custom function to the `validateStatus` property:

See [the `axios` docs (opens new window)](https://github.com/axios/axios#request-config) for more details.

## [#](https://pipedream.com/docs/#paginating-api-requests) Paginating API requests

When you fetch data from an API, the API may return records in "pages". For example, if you're trying to fetch a list of 1,000 records, the API might return those in groups of 100 items.

Different APIs paginate data in different ways. You'll need to consult the docs of your API provider to see how they suggest you paginate through records.