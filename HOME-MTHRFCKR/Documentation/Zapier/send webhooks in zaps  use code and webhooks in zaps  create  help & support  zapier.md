Webhooks are automated messages sent between apps—a type of notification that includes detailed information about new items in apps. If you're on a [paid plan](https://zapier.com/pricing), you can send webhooks in Zaps. You can also [trigger Zaps from webhooks](https://zapier.com/help/create/code-webhooks/trigger-zaps-from-webhooks).

![Video Thumbnail](https://embed-fastly.wistia.com/deliveries/ee55ecdd24d3c109b028b77c393e0396.webp?image_crop_resized=960x540)

## [1\. Add a webhook action](https://zapier.com/help/create/code-webhooks/send-webhooks-in-zaps#add-a-webhook-action)

Webhooks by Zapier offers **GET**, **POST**, **PUT** methods, which include automatic data parsing, and you can also select **Custom Request** for other use cases.

Use _GET_ if you want the step to retrieve information from a server. Use the _POST_ or _PUT_ methods if you’re sending files (file objects cannot be sent via _Custom Request_), or if you're not comfortable writing JSON or XML and would prefer the Zap to parse the information for you.

The app also offers a _Custom Request_ option. This option offers more flexibility and allows you to type out JSON or XML, but is also much less forgiving. Unlike the POST, PUT, and GET methods, it does not automatically parse information for you.

Use _Custom Request_ if your use case involves the following:

After you've selected the webhook option, click **Continue**.

___

## [2\. Select the payload type](https://zapier.com/help/create/code-webhooks/send-webhooks-in-zaps#select-the-payload-type)

To make sure the request is sent in the way your app expects, select the correct format from the _Payload Type_ dropdown menu.

There are three common serialization formats that you will see listed here: **Form** (also called URL-encoded), **JSON**, and **XML**. The following are examples of each format:

**Form**

```
first_name=Bryan&last_name=Helmig&age=27
```

**JSON**

```
{
  "first_name": "Bryan",
   "last_name": "Helmig",
   "age": 27
}
```

**XML**

```
<first_name>Bryan</first_name>
<last_name>Helmig</last_name>
<age>27</age>
```

You can also select **Raw** to send the request as-is. With this option, no data fields will be parsed.

___

## [3\. Enter the URL to send the request to](https://zapier.com/help/create/code-webhooks/send-webhooks-in-zaps#enter-the-url-to-send-the-request-to)

In the **URL** field, enter the URL where your app’s API is able to receive requests.

It's recommended not to add URL parameters in this field. Instead, enter URL parameters in the **Data** fields.

___

## [4\. Fill out the data fields](https://zapier.com/help/create/code-webhooks/send-webhooks-in-zaps#fill-out-the-data-fields)

Fill out the _Data_ section. If you’re using a templated action like **PUT**, **POST\*, or** GET **(i.e. not a Custom Request), enter the _key_ for the field on the left side, and the field value on the right. Data from previous steps can be used in the value field, and you can click the** plus icon +\*\* to add more parameters if needed.

If you need to add nested values, you can define child objects by adding the parent object and a double underscore before the object. Below is an example of what this looks like when entered into the Data section. The `|` (pipe) symbol is used only to separate what goes in the left-side and the right-side fields, and doesn't need to be added to the Zap.

```
order | value
item__price | value
item__sku | value
```

That will turn into JSON that looks like this:

```
{"product": "value", "item": {"price": "value", "sku": "value"}}
```

For more detailed nesting, use the _Custom Request_ action.

### [Using the Custom Request action](https://zapier.com/help/create/code-webhooks/send-webhooks-in-zaps#using-the-custom-request-action)

If you’re using _Custom Request_, type raw JSON (or other formats) directly into the **Data** field. Zapier will not parse or format this data for you and it will be sent exactly as entered, so it's recommended to use a JSON (or other) validator to verify that the syntax is correct.

If you leave the **Data** section blank, **all** fields from the previous step will be sent as the Request Payload. If you see unexpected fields coming in from the Zap, check that the **Data** section for your webhook action has been filled.

___

## [5\. Add headers and authentication](https://zapier.com/help/create/code-webhooks/send-webhooks-in-zaps#add-headers-and-authentication)

You can send specific headers by filling the fields in the **Headers** section.

You can also set up basic authentication (involving just a username and password, or username and API key) using the **Basic Auth** field.

If your app requires more advanced authentication options, you can build a private app integration on Zapier’s [Developer platform](https://zapier.com/platform).

## [Webhook throttling](https://zapier.com/help/create/code-webhooks/send-webhooks-in-zaps#webhook-throttling)

When a large number of triggers or actions occur within a short time span, they may be throttled (limited) to reduce their frequency.

Learn how to [troubleshoot Zaps not sending webhooks](https://zapier.com/help/troubleshoot/behavior/zap-isnt-sending-webhooks).