Zapier relies on a few methods to make sure that your Zap does not trigger multiple times for a single "new" item.

The way Zapier does this is generally by polling, looking for new items every few minutes (your plan's [polling interval](https://zapier.com/help/create/basics/learn-key-concepts-in-zapier#step-6)). Zapier stores an identifier for each item seen so that the Zap never triggers off of that item again.

If you have two Zaps using the same trigger (e.g. two Zaps which trigger off the same form) both Zaps will be triggered by new items. Deduplication happens on a per-Zap basis.

Deduplication has several important effects:

The following apps and triggers have a special "steady-state" post-deduplication process applied. Normally, a new item will trigger a Zap as soon as Zapier first encounters it. However, this is not ideal for certain items that are created before you finish setting them up.

For example, you might still be typing into your new Evernote note when it triggers your Zap. The steady-state postprocessor will wait to trigger a Zap until the item has stopped changing across one polling interval.