**Last updated:** November 02, 2021

Filters are a way to ensure actions get performed only on the items you want. With filters, you set a specific condition to get to the granularity you need.

For instance, you can set up a filter to only capture emails that contain a specific subject line or only customers who purchase a specific product. So when the data from your Zap meets the conditions of a filter, it proceeds to the next action in your Zap. If a filter stops an item, then no further actions are performed.

If a filter does not pass, it does not count as a task, and no other action will run that would count as a task either.

Learn how to [set up filters for your Zap](https://zapier.com/help/create/customize/add-conditions-to-zaps-with-filters).

___

## [Filter rule types](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#step-1)

Filters can use different rules for logic. Conditions can only work for the type of data that is specified in parentheses. There are five types of filter rules: text, number, date/time, boolean, and generic.

**Examples**

In this table, you can see which fields would pass a given rule. In each example, the _Rule_ is the filter rule we’ve set, the Value is what we’re checking against, and the examples are those coming through the Zap that the filter is checking.

| Rule | Value | Examples that would pass | Examples that wouldn’t pass |
| --- | --- | --- | --- |
| (Text) Contains | Apples and bananas | Apples Apple Apples and bananas | Strawberries |
| (Text) Does not contain | Apples and bananas | Strawberries | Apple |
| (Text) Exactly matches | Apples | Apples | Apple (not plural) apple (not uppercase) |
| (Text) Does not exactly match | Apples | Apple Banana And more | Apples |
| (Text) Is in | Apples, bananas | Apples Bananas | Apple Banana Strawberries |
| (Text) Is not in | Apples, bananas | Strawberries Apple | Apples Bananas |
| (Text) Starts with | App | Apples Applesauce | Apricots Bananas |
| (Text) Does not start with | App | Apricots Bananas | Apples Applesauce |
| (Text) Ends with | s | Bananas Apple and bananas | Apple |
| (Text) Does not end with | s | Apple Banana | Apples Bananas |
| (Number) Greater than | 10 | 11100 | 9-1 |
| (Number) Less than | 10 | 9-1 | 100 |
| (Date/time) After | 12/31/2018 1:00 | 01/01/2019 12/31/2018 01:01 | 12/31/2017 |
| (Date/time) Before | 12/31/2018 1:00 | 12/31/2017 | 01/01/2019 |
| (Date/time) Equals | 12/31/2018 1:00 | 12/31/2018 1:00 | 12/31/2019 12/31/2018 00:00 |
| Exists | n/a | Apple 10 01/01/2019 |  |
| Does not exist | n/a |  | Apple 10 01/01/2019 |

When filtering [line items](https://zapier.com/help/create/basics/use-line-items-in-zaps), whether your Zap continues past the filter depends on whether you use [positive or negative filter conditions](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#step-6).

___

## [Text filters](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#step-2)

Text filters only work with text data, so they won’t work with numbers or dates.

You should only use _Exactly matches_ as a filter rule when you want your Zap to continue only if the field has certain exact words, down to the letter (it's even case-sensitive). Be careful with this rule as it can sometimes filter out more records than you expect. If you want a similar but less strict rule, try using _Contains_.

___

## [Number filters](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#step-3)

Number filters only work with numeric values, like 1 or 100. They do not work with written forms of numbers (one, two, one hundred) or dates.

___

## [Boolean filters](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#step-4)

___

## [Generic filters](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#step-5)

___

## [Filters and line items](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#step-6)

If you have a set of [line items](https://zapier.com/help/create/basics/use-line-items-in-zaps) like this:

[![Example of line items](https://cdn.zappy.app/0644b5ff109474052dc61e732c66cfd1.png)](https://cdn.zappy.app/0644b5ff109474052dc61e732c66cfd1.png)

Whether your Zap continues past the filter depends on whether you use positive or negative filter conditions.

### [If your filter conditions are all positive](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#if-your-filter-conditions-are-all-positive)

If all conditions are positive, at least one line item must pass all filter conditions for the Zap to continue.

In the example below, the Zap continues because a single line item passed both positive conditions, even if others didn't.

[![Example of line items passing when using all positive filter conditions](https://cdn.zappy.app/0a3e269ddd5234d894850afb35d4f413.png)](https://cdn.zappy.app/0a3e269ddd5234d894850afb35d4f413.png)

### [If your filter conditions are both positive and negative or all negative](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps#if-your-filter-conditions-are-both-positive-and-negative-or-all-negative)

Whenever there is a negative condition included, all line items must pass all filter conditions for the Zap to continue.

In the example below, the Zap doesn't continue because at least one line item didn't pass the filter conditions.

[![Example of line items not passing when using all negative filter conditions](https://cdn.zappy.app/5e0b487ae0116dc5811af4cea723d5d0.png)](https://cdn.zappy.app/5e0b487ae0116dc5811af4cea723d5d0.png)

The Filter action doesn't remove any line items. If you map line items to later actions, this will include any line items that didn't pass the filter conditions.

___