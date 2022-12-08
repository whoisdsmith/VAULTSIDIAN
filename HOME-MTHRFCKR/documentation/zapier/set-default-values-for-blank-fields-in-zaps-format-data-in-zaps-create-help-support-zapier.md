**Last updated:** September 27, 2021

With the default value text transformation in [Formatter](https://zapier.com/help/create/format/get-started-with-formatter), you can set a fallback value for fields that may not always have a value provided by a previous step.

You have a web form that collects leads and the _Name_ field is optional but your CRM requires it. You can set a default value of “Unknown” so that anyone that doesn't fill out their name still gets passed to your CRM.

Before you can add Formatter to a Zap, you’ll first need to [set up your Zap trigger](https://zapier.com/help/create/basics/set-up-your-zap-trigger).

A field may also be blank because the trigger test does not contain that field, or the name of the field changed. Before implementing the solution below, make sure to get [new trigger test data](https://zapier.com/help/create/basics/change-the-test-data-in-your-zap-trigger) so you have all current field names.

___

## [1\. Add Formatter to your Zap](https://zapier.com/help/create/format/set-default-values-for-blank-fields-in-zaps#add-formatter-to-your-zap)

___

## [2\. Set up the Default Value text transform](https://zapier.com/help/create/format/set-default-values-for-blank-fields-in-zaps#set-up-the-default-value-text-transform)

[![In this example, the “First And Last Name” field from our form is being checked, and the value "Unknown” is sent to upcoming steps if our respondents don’t include their own name.](https://cdn.zappy.app/1c955e37ca087708fac58de071b77414.png)](https://cdn.zappy.app/1c955e37ca087708fac58de071b77414.png)

___

## [3\. Test your transformation](https://zapier.com/help/create/format/set-default-values-for-blank-fields-in-zaps#test-your-transformation)

Click **Test & Review** to test your transformation. If the transformation was successful, you’ll see either the value provided by your trigger or the default value if the input field is blank.

After you set the default value, you will need to map the output of the Formatter step to the action step, instead of the original field. Learn more about [how to set up an action step](https://zapier.com/help/create/basics/set-up-your-zap-action#set-up-your-action).

___