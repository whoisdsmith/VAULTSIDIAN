With a delay step, you can put your Zap on hold for a specified amount of time before your actions run. You can use delays to set up scheduled emails, get notified of incomplete tasks, send automatic follow-ups, and automate other tasks on your timeline.

There are three types of Zap delays:

1.  Delay for
2.  Delay until
3.  Delay after queue

![Video Thumbnail](https://embedwistia-a.akamaihd.net/deliveries/97a22ccfd51a78ce5d744b5edc380f02.webp?image_crop_resized=960x540)

## [1\. Delay for](https://zapier.com/help/create/customize/add-delays-to-zaps#delay-for)

___

## [2\. Delay until](https://zapier.com/help/create/customize/add-delays-to-zaps#delay-until)

___

## [3\. Delay after queue](https://zapier.com/help/create/customize/add-delays-to-zaps#delay-after-queue)

The Delay After Queue option allows you to create a queue of actions to run. When a Zap is triggered, it adds actions to the queue. The queue then plays the actions one at a time in the order that they were added to the queue. There is a delay between each set of actions for a Zap.

This can be useful if you are running into limits with too many requests to an app, or if you have multiple Zaps that may try to update a record at the same time.

To use Delay After Queue:

The maximum time a task can be held for is for one month (31 days). Since tasks will be queued, the maximum number of tasks in the queue depends on the _Time Delayed For (value)_ value. For example, if you set the delay to one day, the maximum number of tasks in the queue will be 31. If a 32nd task is created within that period, it will error on the delay step because the scheduled time it will be released is too far away.

___

## [4\. Additional limitations](https://zapier.com/help/create/customize/add-delays-to-zaps#additional-limitations)

After setting up your delay, click **Test & Review** and check if the date matches the delay conditions you’ve set up.

If you want your action(s) to run based on a recurring event that doesn't occur at fixed intervals, you can create a recurring event in Google Calendar and add a Google Calendar action to schedule your action(s).