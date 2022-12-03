**Last updated:** July 14, 2021

With a lookup table, you can automatically match data from one app with the corresponding data needed by another app. This is useful if two apps treat the same object differently. Lookup tables can only be used in a Zap action, not in a trigger.

If your trigger app sends the customer's name but your action app needs a customer ID, you can create a lookup table to match the name to the correct ID, and use the result in an action step.

If the [mapped field](https://zapier.com/help/create/basics/set-up-your-zap-action#set-up-your-action) for the lookup key has no value, nothing will be sent by the lookup table. The fallback value is only used for existing values that do not match any table row.

___

## [1\. Add a formatter step](https://zapier.com/help/create/format/create-lookup-tables-in-zaps#add-a-formatter-step)

___

## [2\. Select the lookup key](https://zapier.com/help/create/format/create-lookup-tables-in-zaps#select-the-lookup-key)

In the _Lookup Key_ field, select data from the trigger or a previous action step. The Zap will use this value to search the lookup table for the correct row.

___

## [3\. Fill out the table](https://zapier.com/help/create/format/create-lookup-tables-in-zaps#fill-out-the-table)

In the _Lookup Table_ fields, enter the original values (sent by the trigger or another action step) in the left column (the keys), and the matching values in the right column (the values).

The key column is case sensitive and expects an exact match with the information in the _Lookup Key_ field.

[![In the example, the lookup key is the field "Product". When the Zap runs, the lookup table will search for the value of that field in the left-hand column and output what is in the right-hand column. In this case, the product "Workshop" will output "842"](https://cdn.zappy.app/090776a88e5ecb5ee6a7b5e9a31bf907.png)](https://cdn.zappy.app/090776a88e5ecb5ee6a7b5e9a31bf907.png)

To find the values you need for the right column, look at the options in the field that will receive these values in the other app's Zap step. The value will be written in gray underneath the name of the option.

[![Example of when an app shows you the expected value](https://cdn.zappy.app/2e98356996f2f0f01be69bf7e4e6e66b.png)](https://cdn.zappy.app/2e98356996f2f0f01be69bf7e4e6e66b.png)

Lookup tables can only have one field as the lookup key, but can find multiple values if they're [line items](https://zapier.com/help/create/basics/use-line-items-in-zaps) within the same field.

___

## [4\. Map the output to another step](https://zapier.com/help/create/format/create-lookup-tables-in-zaps#map-the-output-to-another-step)

Next, [map the output](https://zapier.com/help/create/basics/set-up-your-zap-action#set-up-your-action) of the lookup table to the field in your action step that requires that value:

[![Map the output of the lookup table to the action field](https://cdn.zappy.app/45b8d2929e7f1bdebcdc4b21832fff71.png)](https://cdn.zappy.app/45b8d2929e7f1bdebcdc4b21832fff71.png)

Once you’ve set up your lookup table and mapped the output to another action, you’re ready to continue setting up the rest of your Zap.

___