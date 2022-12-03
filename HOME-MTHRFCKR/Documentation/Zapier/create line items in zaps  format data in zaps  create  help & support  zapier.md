**Last updated:** July 13, 2021

Line items are subsets of individual items. For example, “apples, oranges, bananas” are line items of “fruit”.

Line items are a specific kind of JSON data structure. A line item is an object containing an array of objects. In JSON, an array is a comma-separated list inside of square brackets which \[ “looks”, “like”, “this” \]; a JSON “object” is a set of {key:value} pairs that are surrounded by curly braces.

To use [line items](https://zapier.com/help/create/basics/use-line-items-in-zaps) in your Zap, line items must be supported in both your trigger and action. If your trigger doesn’t support line items, you can use Formatter to create line items after [setting up your trigger](https://zapier.com/help/create/basics/set-up-your-zap-trigger).

___

## [1\. Add a Formatter step to your Zap](https://zapier.com/help/create/format/create-line-items-in-zaps#add-a-formatter-step-to-your-zap)

___

## [2\. Set up the line item transformation](https://zapier.com/help/create/format/create-line-items-in-zaps#set-up-the-line-item-transformation)

There are two ways to create line items with Formatter.

### [Text to Line-item](https://zapier.com/help/create/format/create-line-items-in-zaps#text-to-line-item)

If you have a single set of line items you want to create, use the _Text to Line-item_ transform:

[![Text to line item input field](https://cdn.zappy.app/1188fd60689fab2537a5301a6f4d6b81.png)](https://cdn.zappy.app/1188fd60689fab2537a5301a6f4d6b81.png)

### [Line Itemizer](https://zapier.com/help/create/format/create-line-items-in-zaps#line-itemizer)

If you need to create more than one set of line items, use the _Line Itemizer_ transform:

[![Line itemizer properties](https://cdn.zappy.app/bdd5ec8746bb9c556470141559248d9e.png)](https://cdn.zappy.app/bdd5ec8746bb9c556470141559248d9e.png)

___

## [3\. Test your line item transformation](https://zapier.com/help/create/format/create-line-items-in-zaps#test-your-line-item-transformation)

[![Formatter by Zapier test](https://cdn.zappy.app/4357440d5671f88ce08c8c61260e74e5.png)](https://cdn.zappy.app/4357440d5671f88ce08c8c61260e74e5.png)

After creating your line items with Formatter, you can [use these line items](https://zapier.com/help/create/basics/use-line-items-in-zaps) in further actions in your Zap.

___