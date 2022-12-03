If you're on a [paid plan](https://zapier.com/pricing), you can trigger Zaps from polling webhooks. In contrast to the [Catch Hook trigger](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks), which requires you to send a POST request to trigger the Zap, the Retrieve Poll trigger “polls” an endpoint for data. In other words, it allows you to send a GET request to a REST API endpoint and parse the data that is returned.

This trigger only supports basic authentication with a username and password. If you need to query an API that requires more advanced forms of authentication, you should create your own private application on the [Zapier platform](https://zapier.com/platform).

## [1\. Make sure your endpoint returns JSON in the format Zapier requires](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-polling-webhooks#make-sure-your-endpoint-returns-json-format-zapier-requires)

In order to trigger properly, the Zap expects your URL to return JSON, specifically a list of dictionaries (an array of objects) in reverse chronological order (newest first, oldest last). For example, that might look like this:

```
[{“id”:1235, “name”:”event2”, “created_date”:”2019-04-01”},{“id”:1234, “name”:”event1”, “created_date”:”2019-01-01”}]
```

___

## [2\. Enter the deduplication key](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-polling-webhooks#enter-the-deduplication-key)

By default, Zapier looks for an “id” key, and uses that to determine whether a record is new or not, i.e. to deduplicate the records.

If the “id” key does not exist by default in your data, you have two options: \* You may specify an alternate unique key that the Zap can use for deduplication in the _Deduplication Key_ field. \* If you don’t specify an alternate key, the Zap will fall back to the shortest key containing “id”.

___

## [3\. Enter a child key](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-polling-webhooks#enter-a-child-key)

Often, the array containing the objects that you’d like to trigger your Zap is not top-level—instead, it may be contained within another object.

If this is the case, use the _Key_ field to enter the key corresponding to the array that does contain the records you’d like to trigger the Zap. Note that this field does support dot notation if the array is nested more than once.

___

## [4\. Customize your webhook trigger](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-polling-webhooks#customize-your-webhook-trigger)

The Retrieve Poll trigger also offers the ability to enter a username and password, Headers, and an Xpath. If your API requires authentication or custom headers to access and parse data properly, you’ll want to take advantage of these fields!

## [Webhook throttling](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-polling-webhooks#webhook-throttling)

Once you’ve set up your webhook trigger, you’re ready to continue setting up the rest of your Zap.