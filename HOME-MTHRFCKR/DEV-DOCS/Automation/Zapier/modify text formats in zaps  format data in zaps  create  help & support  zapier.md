**Last updated:** February 17, 2021

You can use [Formatter’s](https://zapier.com/help/create/format/get-started-with-formatter) Text transform to change text in your Zap. There are several different [text transforms](https://zapier.com/help/create/format/get-started-with-formatter#all-text-transformations) that you can use.

If an app has a _Full name_ field but another app has separate _First name_ and _Last name_ fields, you can use the **Split Text** transform to split the full name data into separate fields.

___

## [1\. Add a Formatter step](https://zapier.com/help/create/format/modify-text-formats-in-zaps#add-a-formatter-step)

[![Mapping a field from a previous step to the Input field](https://cdn.zappy.app/c098b22051adf99a9f4a10f1e5db1147.png)](https://cdn.zappy.app/c098b22051adf99a9f4a10f1e5db1147.png)

Some text transforms will have additional required or optional fields.

___

## [2\. (Optional) Find, replace, or split special characters](https://zapier.com/help/create/format/modify-text-formats-in-zaps#find-replace-or-split-special-characters)

In order to find, replace, or split special characters in text, you must use a special character syntax:

```
- `[:space:]` - matches space (\s) characters
- `[:tab:]` - matches tab (\t) characters
- `[:newline:]` - matches newline (\n) characters
- `[:return:]` - matches carriage-return (\r) characters
```

In the previous example, you can split “Jane Doe” into separate fields using the `[:space:]` special character.  
![Using the space special character](https://cdn.zappy.app/15f71bf6a953025bf8e98313083f749e.png)

___

## [3\. Test your text transform](https://zapier.com/help/create/format/modify-text-formats-in-zaps#test-your-text-transform)

Once you've set up the Formatter Text transform, you can use the results in further actions in your Zap.

___