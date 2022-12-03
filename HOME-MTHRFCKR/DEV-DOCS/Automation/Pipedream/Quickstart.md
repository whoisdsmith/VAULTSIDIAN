Sign up for a [free Pipedream account (no credit card required) (opens new window)](https://pipedream.com/auth/signup) and complete this quickstart guide to learn the basic patterns for workflow development:

-   [Create a new workflow](https://pipedream.com/docs/#create-a-new-workflow)
-   [Add an HTTP / Webhook trigger](https://pipedream.com/docs/#add-an-http-webhook-trigger)
-   [Send data to the workflow](https://pipedream.com/docs/#send-data-to-the-workflow)
-   [Enrich trigger data using Node.js and npm](https://pipedream.com/docs/#enrich-trigger-data-using-node-js-and-npm)
-   [Save data to Google Sheets](https://pipedream.com/docs/#save-data-to-google-sheets)

### [#](https://pipedream.com/docs/#create-a-new-workflow) Create a new workflow

First, create a new workflow by clicking **New** from [https://pipedream.com/workflows (opens new window)](https://pipedream.com/workflows):

![image-20210516114638660](https://pipedream.com/docs/assets/img/image-20210516114638660.739caab0.png)

### [#](https://pipedream.com/docs/#add-an-http-webhook-trigger) Add an HTTP / Webhook trigger

Pipedream will launch the workflow builder. For this example, select the **HTTP / Webhook Requests** trigger.

![./image-20220123213843066](https://pipedream.com/docs/assets/img/image-20220123213843066.968d755b.png)

Click **Continue** to accept the default settings.

![./image-20220123214244795](https://pipedream.com/docs/assets/img/image-20220123214244795.59ba841b.png)

Pipedream will generate a unique URL to trigger this workflow.

![./image-20220123214505923](https://pipedream.com/docs/assets/img/image-20220123214505923.1a0b7e3e.png)

### [#](https://pipedream.com/docs/#send-data-to-the-workflow) Send data to the workflow

Next, send data to the trigger URL to help you build the workflow. For this example, send an HTTP POST request with a JSON body containing a simple message.

You can edit and run the following `cURL` command (or use your favorite HTTP tool).

When Pipedream receives the request, it will display the contents of the HTTP request. Expand the `body` to validate that the message was received. ![./image-20220123215443936](https://pipedream.com/docs/assets/img/image-20220123215443936.1315ff21.png)

If you need to send a different event to your workflow you can select it from the event selector:

![./image-20220123215558412](https://pipedream.com/docs/assets/img/image-20220123215558412.17881139.png)

TIP

The selected event will be used to provide autocomplete suggestion as you build your workflow. The data will also be used when testing later steps.

### [#](https://pipedream.com/docs/#enrich-trigger-data-using-node-js-and-npm) Enrich trigger data using Node.js and npm

Before we send data to Google Sheets, let's use the npm [`sentiment` (opens new window)](https://www.npmjs.com/package/sentiment) package to generate a sentiment score for our message. To do that, click **Continue** or the **+** button.

![./image-20220123220018170](https://pipedream.com/docs/assets/img/image-20220123220018170.f67ab13e.png)

That will open the **Add a step** menu. Select **Run custom code**.

![./image-20220123220128877](https://pipedream.com/docs/assets/img/image-20220123220128877.df656921.png)

Pipedream will add a Node.js code step. Rename the step to **sentiment**.

![image-20220123221849231](https://pipedream.com/docs/assets/img/image-20220123221849231.21370cc3.png)

Next, add the following code to the code step:

This code imports the npm package, passes the message we sent to our trigger to the `analyze()` function by referencing `steps.trigger.event.body.message` and then returns the result.

TIP

To use any npm package on Pipedream, just `import` it. There's no `npm install` or `package.json` required.

TIP

Any data you `return` from a step is exported so it can be inspected and referenced it in future steps via the `steps` object. In this example, return values will be exported to `steps.sentiment.$return_value` because we renamed the step to **sentiment** .

Your code step should now look like the screenshot below. To run the step and test the code, click the **Test** button.

![image-20220123222340361](https://pipedream.com/docs/assets/img/image-20220123222340361.5f1447ee.png)

You should see the results of the sentiment analysis when the test is complete.

![image-20220123222643042](https://pipedream.com/docs/assets/img/image-20220123222643042.b9db2022.png)

TIP

When you **Test** a step, only the current step is executed. Use the caret to test different ranges of steps including the entire workflow.

### [#](https://pipedream.com/docs/#save-data-to-google-sheets) Save data to Google Sheets

Next, create a Google Sheet and add **Timestamp**, **Message** and **Sentiment Score** to the first row. These labels will act as our column headers amd will help us configure the Google Sheets step of the workflow.

![image-20220125184754078](https://pipedream.com/docs/assets/img/image-20220125184754078.76a52ce5.png)

Next, let's add a step to the workflow to send the data to Google Sheets. First, click **+** after the `sentiment` code step and select the **Google Sheets** app.

![image-20220125185156527](https://pipedream.com/docs/assets/img/image-20220125185156527.576a3669.png)

Then select the **Add Single Row** action.

![image-20220125185305043](https://pipedream.com/docs/assets/img/image-20220125185305043.c3e29efb.png)

Click to connect you Google Sheets account to Pipedream (or select it from the dropdown if you previously connected an account).

![image-20220125185354469](https://pipedream.com/docs/assets/img/image-20220125185354469.3971f459.png)

Pipedream will open Google's sign in flow in a new window. Sign in with the account you want to connect.

![image-20220125185544800](https://pipedream.com/docs/assets/img/image-20220125185544800.fc095965.png)

Important

If prompted, you must check the box for Pipedream to **See, edit, create and delete all of your Google Drive files**. These permissions are required for configure and use the pre-built actions for Google Sheets.

![image-20220125185952120](https://pipedream.com/docs/assets/img/image-20220125185952120.fc9a7f27.png)

Learn more about Pipedream's [privacy and security policy](https://pipedream.com/docs/privacy-and-security/).

When you complete connecting your Google account, the window should close and you should return to Pipedream. Your connected account should automatically be selected. Next, select your spreadsheet from the dropdown menu:

![image-20220125190643112](https://pipedream.com/docs/assets/img/image-20220125190643112.ff86e079.png)

Then select the sheet name (the default sheet name in Google Sheets is **Sheet1**):

![image-20220125190740937](https://pipedream.com/docs/assets/img/image-20220125190740937.a2d2cf50.png)

Next, select if the spreadsheet has headers in the first row. When a header row exists, Pipedream will automatically retrieve the header labels to make it easy to enter data (if not, you can manually construct an array of values). Since the sheet for this example contains headers, select **Yes**.

![image-20220125191025880](https://pipedream.com/docs/assets/img/image-20220125191025880.fa7028b1.png)

Pipedream will retrieve the headers and generate a form to enter data in your sheet:

![image-20220125191155907](https://pipedream.com/docs/assets/img/image-20220125191155907.ddf3f897.png)

First, let's use the object explorer to pass the timestamp for the workflow event as the value for the first column. This data can be found in the context object on the trigger. When you click into the **Timestamp** field, Pipedream will display an object explorer to make it easy to find data. Scroll or search to find the `ts` key under `steps.trigger.context` and click **select path**. That will insert the reference `{{steps.trigger.context.ts}}`:

![image-20220125191627775](https://pipedream.com/docs/assets/img/image-20220125191627775.e6e096a8.png)

Next, let's use autocomplete to enter a value for the **Message** column. First, add double braces `{{` — Pipedream will automatically add the closing braces `}}`. Then, type `steps.trigger.event.body.message` between the pairs of braces. Pipedream will provide autocomplete suggestions as you type. Press **Tab** to use a suggestion and then click `.` to get suggestions for the next key. The final value in the **Message** field should be `{{steps.trigger.event.body.message}}`.

![image-20220125191907876](https://pipedream.com/docs/assets/img/image-20220125191907876.344faf69.png)

Finally, let's copy a reference from a previous step. Scroll up to the `sentiment` step and click the **Copy Path** link next to the score.

![image-20220125192301634](https://pipedream.com/docs/assets/img/image-20220125192301634.dd474cb7.png)

Paste the value into the **Sentiment Score** field — Pipedream will automatically wrap the reference in double braces `{{ }}`.

![image-20220125192410390](https://pipedream.com/docs/assets/img/image-20220125192410390.2d94f403.png)

Now that the configuration is complete, click **Test** to validate the configuration for this step. When the test is complete, you will see a success message and a summary of the action performed:

![image-20220125192709058](https://pipedream.com/docs/assets/img/image-20220125192709058.539c0e80.png)

If you load your spreadsheet, you should see the data Pipedream inserted.

![image-20220125192818879](https://pipedream.com/docs/assets/img/image-20220125192818879.e1abecfd.png)

Next, return to your workflow. Before you deploy, customize the name of your workflow:

![image-20220125193340378](https://pipedream.com/docs/assets/img/image-20220125193340378.e408cb3d.png)

Then click **Deploy** to run your workflow on every trigger event.

![image-20220125200445675](https://pipedream.com/docs/assets/img/image-20220125200445675.b2a47368.png)

When your workflow deploys, you will be redirected to the **Inspector**. Your workflow is now live.

![image-20220125193507453](https://pipedream.com/docs/assets/img/image-20220125193507453.a57b4f69.png)

To validate your workflow is working as expected, send a new request to your workflow: You can edit and run the following `cURL` command:

The event will instantly appear in the event list. Select it to inspect the workflow execution.

![image-20220125194354113](https://pipedream.com/docs/assets/img/image-20220125194354113.fa944cc0.png)

Finally, you can return to Google Sheets to validate that the new data was automatically inserted.

![image-20220125194510308](https://pipedream.com/docs/assets/img/image-20220125194510308.0aa862b0.png)

Congratulations! You completed the quickstart and should now understand the basic patterns for workflow development. Next, try creating your own workflows and check out the docs to learn more!