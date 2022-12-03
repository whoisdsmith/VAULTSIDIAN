**Last updated:** February 09, 2021

You can add branching logic to Zaps by using [filters](https://zapier.com/help/create/customize/add-conditions-to-zaps-with-filters) in multiple Zaps. This allows your Zaps to take different paths of actions based on the data received from your app.

If you're on a [Professional plan or higher](https://zapier.com/pricing), you can add branching logic to Zaps with [paths](https://zapier.com/help/create/customize/add-branching-logic-to-zaps-with-paths). This article is intended for users on plans without access to paths.

This article uses lead distribution as an example, but this process can be applied to any situation where you want to take different actions depending on incoming data from your app.

___

## [1\. Create the first Zap and filter](https://zapier.com/help/create/customize/add-branching-logic-to-zaps-with-filters#create-the-first-zap-and-filter)

Set the [filter rule](https://zapier.com/help/create/customize/add-conditions-to-zaps-with-filters) so that the Zap only continues when the correct value is present. This will prevent the Zap from continuing when the specific field has different values.

For example, you can set the filter rule for the Zap to only continue if the field _Source_ contains the text _website_.

[![In this example, the Zap will only continue if the field "Source" contains the word "Website"](https://cdn.zappy.app/25f18899ec2b3bcb92de2519284f0136.png)](https://cdn.zappy.app/25f18899ec2b3bcb92de2519284f0136.png)

You can then set up an action that is customized to the specific value, such as sending the incoming lead to a specific salesperson.

[![Example of sending leads from a specific source to a specific salesperson](https://cdn.zappy.app/20dd8e86abae1b59961e3af06e521fc0.png)](https://cdn.zappy.app/20dd8e86abae1b59961e3af06e521fc0.png)

___

## [2\. Create the second Zap and filter](https://zapier.com/help/create/customize/add-branching-logic-to-zaps-with-filters#create-the-second-zap-and-filter)

Similar to the first Zap, set the [filter rule](https://zapier.com/help/create/customize/add-conditions-to-zaps-with-filters) so that the Zap only continues when the correct value is present.

For example, you can set the filter rule for the Zap to only continue if the field _Source_ contains the text _phone_.

[![In this example, the Zap will only continue if the field "Source" contains the text "phone"](https://cdn.zappy.app/d2d988ce80fb0230af77bd3ed0f0ba5e.png)](https://cdn.zappy.app/d2d988ce80fb0230af77bd3ed0f0ba5e.png)

You can then set up the same action as in the first Zap, this time customized to the second value. For example, the incoming lead can be sent to a different salesperson.

[![Example of sending leads from a specific source to a specific salesperson](https://cdn.zappy.app/684aaccb886dce03613cfd6748d2fa94.png)](https://cdn.zappy.app/684aaccb886dce03613cfd6748d2fa94.png)

To create more than two branches, you can repeat this process by creating more Zaps and filters for each possible field value.

___