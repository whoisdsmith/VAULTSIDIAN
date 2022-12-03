Paths let you build advanced workflows to perform different actions based on different conditions. Paths use conditional, if/then logic: if A happens in your trigger app, then do X. If B happens, then do Y, and so on.

With each path, you set up rules and decide which actions should occur when those rules are met. You can add up to three paths and three nested paths (paths within a path) in your Zap. You can only set up paths after [adding a trigger](https://zapier.com/help/create/basics/set-up-your-zap-trigger) to your Zap, and paths must be the final step of your Zap.

Paths are only available on [Professional plans and higher](https://zapier.com/pricing). If you’re on a Free or Starter plan, you can get a free 7-day trial of paths by adding a paths step to a Zap in the editor.

## [1\. Add a path to your Zap](https://zapier.com/help/create/customize/add-branching-logic-to-zaps-with-paths#add-a-path-to-your-zap)

[![Path A and B will be added after adding a paths step](https://zappy.zapier.com/EA4799BD-7190-400C-985C-F7056EC89518.png)](https://zappy.zapier.com/EA4799BD-7190-400C-985C-F7056EC89518.png)

[![Renaming a path](https://zappy.zapier.com/E1150D59-5A7E-48C4-9FEC-8A4446B4413F.png)](https://zappy.zapier.com/E1150D59-5A7E-48C4-9FEC-8A4446B4413F.png)

Zaps are limited to 100 steps, including all steps within paths.

___

## [2\. Set your path rule(s)](https://zapier.com/help/create/customize/add-branching-logic-to-zaps-with-paths#set-your-path-rules)

In the _Rules_ section, set the rule(s) for your path using the three dropdown menus. Each path rule requires three pieces of information:

1.  **Field:** in the first dropdown menu, select a _trigger field_ to base the rule on.
2.  **Rule:** in the second dropdown menu, select the _rule_ for the trigger field. Learn more about [different rule types](https://zapier.com/help/create/customize/understand-different-filter-and-path-rules).
3.  **Value:** in the third dropdown menu, enter the specific _value_ the rule must meet.

[![Path rule](https://zappy.zapier.com/39981A29-DE87-4B0C-9A26-12F627D7328F.png)](https://zappy.zapier.com/39981A29-DE87-4B0C-9A26-12F627D7328F.png)

There are two types of logic for multiple path rules:

[Learn more about the difference between AND and OR](https://zapier.com/help/create/customize/whats-the-difference-between-and-and-or-logic-in-filters-and-paths). When you’re done setting up your rules, click **Test & Continue**.

If the data checked by the Zap matches more than one path, all matching paths will be used.

___

## [3\. Test your path rule(s)](https://zapier.com/help/create/customize/add-branching-logic-to-zaps-with-paths#test-your-path-rules)

In the _Filter Setup & Testing_ section, Zapier will test your path rules based on your sample data. A message will inform you if your Zap would or would not have continued down this path based on the sample data.

[![Path rule test](https://zappy.zapier.com/040E563E-38C1-4645-A358-F9C360F5C0E7.png)](https://zappy.zapier.com/040E563E-38C1-4645-A358-F9C360F5C0E7.png)

___

## [4\. Add actions to your path](https://zapier.com/help/create/customize/add-branching-logic-to-zaps-with-paths#add-actions-to-your-path)

Next, add actions to your path the same way you would [add actions to a regular Zap](https://zapier.com/help/create/basics/set-up-your-zap-action). You must add _at least one action_ to a path before you can build another path.

When you’re done setting up your action(s), click **Set Up Next Path**.

___

## [5\. Add more paths to your Zap](https://zapier.com/help/create/customize/add-branching-logic-to-zaps-with-paths#add-more-paths-to-your-zap)

You can add up to five paths in your Zap, and up to three nested paths (paths within a path). To set up your paths, repeat the steps above.

Paths must be the last step in a Zap. If you want the same actions to occur for each path at the end of your Zap, add the actions to each path.

To implement if/else logic, you can set the rules for two paths with opposite conditions. For example, in Path A: if the email address exists, and in Path B: if the email address does not exist.

When you’re done setting up all your paths, turn on your Zap.