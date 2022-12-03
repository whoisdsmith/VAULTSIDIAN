## [I need to send a nested JSON array in the request data](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#i-need-to-send-a-nested-json-array-in-the-request-data)

To send a nested JSON array, use the Custom Request action. That will allow more flexibility for the payload.

## [How do I fix Error -2. ?](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#how-do-i-fix-error-2-)

This error means the domain lookup for your URL failed. If the URL seems okay, check for extra spaces before or after the URL in your webhook settings. Remove the space and you should be good to go!

## [Why Is It Always 200 or Success Status? Can I customize the response?](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#why-is-it-always-200-or-success-status-can-i-customize-the-response)

For High Availability and High Throughput reasons, Zapier always returns a success message with a payload of debugging information when collecting a webhook—regardless of whether there is a Zap behind the webhook or if it is paused or not. The only way to know if a URL is live is to visit the editor and look at the URL (which never changes for a Zap). There is no way to customize the response to the request you send to the Catch Hook URL, as the response is sent before the Zap triggers and runs on the webhook request.

## [Can I set up redirects?](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#can-i-set-up-redirects)

Zapier cannot set up 301 or 302 redirects to a different URL and deliver/retrieve payloads from the new address. Doing so will result in a failure.

## [How do I fix the error: "413 Request Entity Too Large"?](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#how-do-i-fix-the-error-413-request-entity-too-large)

The maximum webhook size we currently support is 10 MB for triggers and 5MB for actions. Any payloads that exceed this limit with receive a `413` status code.

## [Why do I get a "Connection Failure"?](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#why-do-i-get-a-connection-failure)

This is very common if you have a firewall in place to limit access to your local intranet or company network. Open up your instance to the wider internet to give Zapier and similar services access to your server. Be sure to use good passwords if you can!

## [Webhook not returning results for next steps](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#webhook-not-returning-results-for-next-steps)

Unfortunately, not all apps can send back data in a way that Zapier can interpret in subsequent steps.

If you're familiar with Python or Javascript, a potential workaround is to do this with a [Code step](https://zapier.com/apps/code/integrations). Keep in mind that the Code app is an advanced feature, and the Zapier support team can't help to troubleshoot the code if there are errors.

## [Posting JSON from Web Browser + Access-Control-Allow-Headers in Preflight Response Error](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#posting-json-from-web-browser-access-control-allow-headers-in-preflight-response-error)

Specifically, the error:

> Request header field Content-Type is not allowed by Access-Control-Allow-Headers in preflight response.

This happens when trying to send data to the Zapier webhooks from inside a web browser and altering the Content-Type header during the process. Because of Cross Browser Security restrictions, your browser will reject these requests. To combat this, do not set a custom `Content-Type` header in the request.

## [Nothing found on trigger test step](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#nothing-found-on-trigger-test-step)

Zapier needs to have received a payload of data to that webhook URL before testing to be able to find that data.

The request cannot be completely blank, so be sure to add something in the payload (or the URL parameters if it's a GET request) so the Zap can trigger.

## [Error: "We hit an error creating a post. Error: -11"](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#error-we-hit-an-error-creating-a-post-error-11)

This means that Zapier can't get a reliable IP for the domain. Even though you may be able to access the URL via the browser or an API client, it may still fail Zapier's requirements. When it does, this often means there are issues with the DNS configuration for the domain. You can run it through [http://dnscheck.pingdom.com/](http://dnscheck.pingdom.com/) to find them.

## [My Zap triggered multiple times and I see many entries in Zap History with the same time-stamp](https://zapier.com/help/create/code-webhooks/troubleshoot-webhooks-in-zapier#my-zap-triggered-multiple-times-and-i-see-many-entries-in-zap-history-with-the-same-time-stamp)

If the webhook response data is an array of objects, that will run the subsequent steps in your Zap multiple times — _once for each object in the array_. If this isn't what you're looking to do, you'll need to check the documentation for the API you're connecting to and see if there's a way to limit the number of objects returned in the response to just one (e.g. a `limit` parameter). If that isn't possible, take a look at building a custom integration using Zapier's [Developer Platform](https://zapier.com/platform) which will give you full control over the data received from webhook requests and how it is handled in your Zaps.

If you need further assistance with your webhooks, [contact Zapier support](https://zapier.com/app/get-help).