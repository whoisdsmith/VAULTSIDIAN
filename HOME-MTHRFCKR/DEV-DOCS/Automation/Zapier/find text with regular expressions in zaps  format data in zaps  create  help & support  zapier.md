If you need to separate part of the content from a field, you can do it by using the [Formatter's](https://zapier.com/help/create/format/get-started-with-formatter)  
_Extract Pattern_ transform. This allows you to use regular expressions (regex) to extract partial data from a field.

## [1\. Add a Formatter step to your Zap](https://zapier.com/help/create/format/find-text-with-regular-expressions-in-zaps#add-a-formatter-step-to-your-zap)

___

## [2\. Set up the “Extract pattern” transform](https://zapier.com/help/create/format/find-text-with-regular-expressions-in-zaps#set-up-the-extract-pattern-transform)

The _Input_ field can work with [line items](https://zapier.com/help/create/basics/use-line-items-in-zaps). It will look for the pattern in each item individually. However, this Formatter step won’t work with line items if the option _Match All_ dropdown is set as **Yes**.

___

## [3\. Optional: Set up option (flag)](https://zapier.com/help/create/format/find-text-with-regular-expressions-in-zaps#optional-set-up-option-flag)

To refine your pattern match, select yes from the following dropdown [options](https://developers.google.com/edu/python/regular-expressions#options):  
\- **Match All** - Matches all occurrences of pattern. Returns results as line items. Note: If this option is set to **Yes**, the _Input_ field won't work with line items.  
\- **IGNORECASE** - Ignore upper/lowercase differences for matching.  
\- **DOTALL** - Allow dot (.) to match newline normally it matches anything but newline.  
\- **MULTILINE** - Within a string made of many lines, allow ^ and $ to match the start and end of each line.

___

## [4\. Optional: Create a group label (Match All only)](https://zapier.com/help/create/format/find-text-with-regular-expressions-in-zaps#optional-create-a-group-label-match-all)

When setting the option **Match All** to **Yes**, we recommend creating group label in your [pattern](https://zapier.com/help/create/format/find-text-with-regular-expressions-in-zaps#set-up-the-extract-pattern-transform). This creates named properties in a line item, making it identifiable for use in your Zap later.

In this example, we want to create a group label called _all\_foo\_bars_, by using the pattern `(?P<all_foo_bars>f[o]+ bar)`.  
![Example regex of creating a group label](https://cdn.zappy.app/f9bd71549cf2855e6aba1291bac76501.png)  
![Example of group labels appearing in the test step](https://cdn.zappy.app/23818a0e55b2ed3a791139bc30f86037.png)

___

## [5\. Test your step](https://zapier.com/help/create/format/find-text-with-regular-expressions-in-zaps#test-your-step)

The step will show the results of the regular expression. If the regular expression finds a match, it will return it in the field _output_. As you can have multiple matches in your pattern, your output can vary. Each match will always return at least these fields:

`0` - text of match  
`_end` - last position of match in text  
`_start` - first position of match in the text  
`_matched` - true or false based on the match

If you have multiple matches in your pattern, the first match will appear as `0`, second match as `1` etc.

If you're using the option **Match All**, your results will be returned as line items.

Once you've set up this step, you can add another action where the result of the Formatter step will be used.