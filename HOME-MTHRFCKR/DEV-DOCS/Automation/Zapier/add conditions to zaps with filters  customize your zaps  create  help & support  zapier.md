**Last updated:** December 21, 2021

Filters allow Zaps to only perform actions on the items you want. With filters, you set a specific condition and the Zap will only continue if the data from your app meets that condition.

You can set up a filter to only add customers to a list in your marketing app if they purchase a specific product. If the customer buys a different product, the filter stops the Zap and no further actions are performed.

To use a filter step, your [Zap trigger must be set up](https://zapier.com/help/create/basics/set-up-your-zap-trigger).

![Video Thumbnail](https://embedwistia-a.akamaihd.net/deliveries/f6a3b960c6330cc99951993408ab056e.webp?image_crop_resized=960x540)

___

## [1\. Add a Filter step](https://zapier.com/help/create/customize/add-conditions-to-zaps-with-filters#add-a-filter-step)

You can add a filter at any point after the trigger and can use multiple filters in the same Zap.

___

## [2\. Customize your filter rules](https://zapier.com/help/create/customize/add-conditions-to-zaps-with-filters#customize-your-filter-rules)

[![Let’s take the example of a Zap that triggers from new submissions to a form, and we only want it to run if the user who submitted has an email address that ends in `@zapier.com`. We can set up a filter that looks at the Email field from our trigger, choose the rule to be (Text) Contains, and set the value to be `@zapier.com`. ](https://cdn.zappy.app/254e568d7a382fa61e2326bcee9c31f2.png)](https://cdn.zappy.app/254e568d7a382fa61e2326bcee9c31f2.png)

Rules only work for the type of data specified in parentheses. For example, rules that begin with “(Text)” only work with text fields, and rules that begin with “(Number)” only work with number fields. Learn about the [different types of filter rules](https://zapier.com/help/create/customize/filter-and-path-rules-in-zaps).

___

## [3\. Test your filter](https://zapier.com/help/create/customize/add-conditions-to-zaps-with-filters#test-your-filter)

If the [test data](https://zapier.com/help/create/basics/change-the-test-data-in-your-zap-trigger) would have passed the filter, you’ll see a confirmation that the Zap would have continued.

[![If the data would have passed the filter, a green message will be presented.](https://cdn.zappy.app/348f987567daa40f08e462db6c160c00.png)](https://cdn.zappy.app/348f987567daa40f08e462db6c160c00.png)

If the test data would not have passed the filter, you’ll see a confirmation that the Zap would not have continued.

[![If the data doesn’t pass the filter, you will see a gray message saying that the Zap would not have continued.](https://cdn.zappy.app/a2cfecd286a78567988f5a20ed57e1cd.png)](https://cdn.zappy.app/a2cfecd286a78567988f5a20ed57e1cd.png)

If a Filter step uses data from a [search step](https://zapier.com/help/create/basics/search-for-existing-data-in-zaps#add-your-search-criteria) that didn't find anything, the Filter step and any other steps afterward won’t run.

After the filter is created, you can continue setting up the rest of your Zap. The actions added to the Zap after this filter step will only be performed if the incoming data passes the filter.

___