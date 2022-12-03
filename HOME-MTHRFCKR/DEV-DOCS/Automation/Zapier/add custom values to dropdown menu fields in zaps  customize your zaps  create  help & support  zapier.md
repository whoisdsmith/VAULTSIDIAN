When creating a Zap, you may want to pull in a value from a prior step—for example, to assign a task to a different person depending on variables from the trigger step. Some fields let you insert this information, but depending on the field you fill out, you may run into a static dropdown menu that doesn’t allow it. That’s where custom values come in.

You may want to create new cards in Trello on different boards depending on the data that comes through either the trigger or a previous action step.

## [Types of custom values](https://zapier.com/help/create/customize/add-custom-values-to-dropdown-menu-fields-in-zaps#types-of-custom-values)

The two types of fields you can pass to a custom value are Name fields and ID fields. When there is just a name field, you only need to pass over the name of the field. When there is an ID, the app will only accept the ID of that field. You can tell which kind of values the field accepts by reading the help text below the label. It will tell you if you need to send an ID or a name.

You can only use custom values in action steps and they are only a way to link to an option that already exists in your app. They are not a way to use a value that doesn’t exist in your app.

![Video Thumbnail](https://embedwistia-a.akamaihd.net/deliveries/096dd7eec3498d83113a84fa0900fcb2ea04b902.webp?image_crop_resized=960x540)

## [1\. Set up the custom value (Name field)](https://zapier.com/help/create/customize/add-custom-values-to-dropdown-menu-fields-in-zaps#set-up-the-custom-value-name-field)

[![Continuing with our Trello card position example. In the Card Position dropdown, scroll to the bottom and select Custom Value.  A new field will appear labeled Custom Value for Card Position.  ](https://cdn.zappy.app/7bee99783082e24ddac6e28ed55a0d70.gif)](https://cdn.zappy.app/7bee99783082e24ddac6e28ed55a0d70.gif)

If you want to use a different custom value but the exact name isn’t included in the data from a previous step, then you can [use a lookup table](https://zapier.com/help/create/format/create-lookup-tables-in-zaps). For example, if you want to pass in a different user name to your custom value field depending on the email address from the trigger, you could create a lookup table where you would associate specific names with specific email addresses.

___

## [2\. Set up the custom value (ID field)](https://zapier.com/help/create/customize/add-custom-values-to-dropdown-menu-fields-in-zaps#set-up-the-custom-value-id-field)

[![Using our Trello card board example, in the Board dropdown, scroll to the bottom and select Custom Value. A new field will appear labeled Custom Value for Board where you can insert data from a previous step.](https://cdn.zappy.app/a7801077bef299a72a06676216c95a3a.gif)](https://cdn.zappy.app/a7801077bef299a72a06676216c95a3a.gif)

If you want to use a different custom value but the exact ID isn’t included in the data from a previous step, then you can [use a lookup table](https://zapier.com/help/create/format/create-lookup-tables-in-zaps). For example, if you want to pass in a different user ID to your custom value field depending on the email address from the trigger, you could create a lookup table where you would associate specific IDs with specific email addresses.

Now complete the rest of your Zap, and this field will be dynamically updated whenever your Zap

If you're mapping in a custom value from an object you've created in a previous step, it may not exist yet. You can resolve this by adding a [delay step](https://zapier.com/help/create/customize/helpdocs/create/customize/add-delays-to-zaps) in between in order to give your connected app time to create the new record.