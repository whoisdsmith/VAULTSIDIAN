**Last updated:** May 20, 2021

If your trigger data has a block of text that you need to split up, you can use named variables to separate the data. When you use named variable syntax, your trigger data will be formatted as separate fields that you can use in later steps in your Zap.

If you send a customer’s contact information in an email **body** field, you can use named variables to separate each piece of contact information into its own field.

You must be able to format the trigger data before it’s sent to your Zap. If this data is automatically generated, you’ll need to use a [Formatter step](https://zapier.com/help/create/format/modify-text-formats-in-zaps) to modify that data instead.

___

## [1\. Edit data sent by the trigger app](https://zapier.com/help/create/customize/split-up-trigger-data-in-zaps#edit-data-sent-by-the-trigger-app)

To use named variables in Zaps, you need to apply some specific formatting, so that the Zap can recognize the different fields (also called variables).

If your original data is:

```
First Name Philip
Last Name Fry
Email Address philip.j.fry@planetexpress.net
Phone Number 123-456-7890
```

Reformat it in your app as:

```
FirstName(Philip)
LastName(Fry)
EmailAddress(philip.j.fry@planetexpress.net)
PhoneNumber(123-456-7890)
```

Named variables can only contain letters, numbers, or underscores.

___

## [2\. Check your named variables](https://zapier.com/help/create/customize/split-up-trigger-data-in-zaps#check-your-named-variables)

[![Example email with named variables as separate fields](https://cdn.zappy.app/9c586801a67442c4a195909e41e29ab3.png)](https://cdn.zappy.app/9c586801a67442c4a195909e41e29ab3.png)

When you add another [action](https://zapier.com/help/create/basics/set-up-your-zap-action) to your Zap, you’ll be able to use the data from the individual fields that were created with the named variables.

___