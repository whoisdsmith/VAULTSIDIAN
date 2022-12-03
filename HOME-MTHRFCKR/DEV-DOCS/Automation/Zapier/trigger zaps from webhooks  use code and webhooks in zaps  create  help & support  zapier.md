Webhooks are automated messages sent between apps—a type of notification that includes detailed information about new items in apps. If you're on a [paid plan](https://zapier.com/pricing), you can trigger Zaps from webhooks. You can also [send a webhook](https://zapier.com/help/create/code-webhooks/send-webhooks-in-zaps) when an event occurs in an app.

## [Limitations](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#limitations)

## [1\. Add a webhook trigger](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#add-a-webhook-trigger)

For most webhooks, the _Catch Hook_ trigger will be the best option. Catch hooks work by giving you a unique URL that you can make POST requests to. If you want Zapier to make a GET request of an external URL to check for new entries, use a [Retrieve Poll webhook trigger](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-polling-webhooks).

If you want access to the raw body of the response, use the **Catch Raw Hook** trigger.

___

## [2\. Set up the webhook trigger](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#set-up-the-webhook-trigger)

Next, you’ll be given the URL for your webhook and can set it up:

___

## [3\. Add the webhook URL to your app](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#add-the-webhook-url-to-your-app)

Open the app you want to connect to Zapier, and find its webhooks settings page. You'll often find it in your app's core settings or options page. If you’re unable to find it, check your app's help and support documentation.

In your app's webhook settings, you'll typically choose to add a new webhook connection. Paste the webhook URL you copied from Zapier, select any options that app offers—including which data you want to receive via the webhook—and save your changes.

[![In this example, we’re adding the URL to a Mailchimp account and specifying what types of updates we want Mailchimp to send to it.](https://cdn.zapier.com/storage/photos/54b167b4fdf04268609fb43a904c8265.png)](https://cdn.zapier.com/storage/photos/54b167b4fdf04268609fb43a904c8265.png)

___

## [4\. Send data to your webhook](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#send-data-to-your-webhook)

The app that's connected to your Zapier webhook URL will send data to it whenever something new is added. To test a webhook trigger, you must first add something new to your app. For example, if you're connecting to an email marketing app such as MailChimp, you could add a new subscriber to Mailchimp.

### [Sending more than one event per webhook request](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#sending-more-than-one-event-per-webhook-request)

Webhook triggers can receive more than one event in a single webhook request. You can send an array of properly formed JSON objects, and Zapier will trigger the Zap once for each object in the array.

For example, if you POST this payload to a Webhook endpoint:

```
[
{
    "first_name": "Bryan",
    "last_name": "Helmig",
    "age": 27
},
{
    "first_name": "Mike",
    "last_name": "Knoop",
    "age": 28
},
{
    "first_name": "Wade",
    "last_name": "Foster",
    "age": 29
}
]
```

Zapier will trigger the actions three times, once for every object in the array.

___

## [5\. Test your webhook](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#test-your-webhook)

Zapier will separate each field from your webhook data, which lets you use them (e.g. email addresses, names, project info) in later steps in your Zap.

If you don't get any data in the test, try to add a new item to your trigger app again and see if the Zap receives it. If the data still doesn’t come in, double-check the webhook settings in your trigger app to ensure that Zapier's webhooks URL was added correctly.

___

## [6\. Optional: Trigger multiple Zaps with webhooks](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#optional-trigger-multiple-zaps-with-webhooks)

If you have multiple webhooks you want to trigger from the same event in your app, you can combine their URLs into a single URL. For example, if you have three Zaps, the URLs would look like this:

`https://hooks.zapier.com/hooks/catch/123456/zbB61`

`https://hooks.zapier.com/hooks/catch/123456/kzXC4`

`https://hooks.zapier.com/hooks/catch/123456/2Ajjn`

You can take the last part of each URLs and combine them into a single URL like this:  
`https://zapier.com/hooks/catch/123456/zbB61,kzXC4,2Ajjn`

Requests sent to this URL will trigger all three webhook URLs at once.

## [Webhook throttling](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks#webhook-throttling)

When a large number of triggers or actions occur within a short time span, they may be throttled (limited) to reduce their frequency. Here are some cases where webhooks may be throttled:

Once you’ve set up your webhook trigger, you’re ready to continue setting up the rest of your Zap.