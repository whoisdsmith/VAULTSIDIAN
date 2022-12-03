# Activity Feed - How-To 

---

-   [About the Activity feed](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#AbouttheActivityfeed)
-   [Applet errors](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appleterrors)

-   [Applet ran](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletran)
-   [Applet updated](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletupdated)
-   [Applet created](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletcreated)
-   [Applet turned on](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletturnedon)
-   [Applet turned off](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletturnedoff)
-   [Applet skipped](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletskipped)

-   [Applets could also skip if:](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletscouldalsoskipif:)

-   [Applet failed](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletfailed)
-   [Applet published](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Appletpublished)

-   [Service errors](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Serviceerrors)

-   [Service connected](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Serviceconnected)
-   [Service disconnected](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Servicedisconnected)
-   [Service edited](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Serviceedited)
-   [Service is offline](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Serviceisoffline)
-   [Service is online](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Serviceisonline)
-   [Usage limit exceeded](https://help.ifttt.com/hc/en-us/articles/115004914234-How-to-use-the-IFTTT-Activity-feed#Usagelimitexceeded)

___

## About the Activity feed

The Activity feed gives you a log of your Applet runs. If you're wondering why an Applet isn't working properly, this may be the first place you look. It can be viewed [on web](https://ifttt.com/activity) or in the [[IFTTT]] apps.

You can visit your Activity feed to find useful information about your Applets and services:

-   Applet actions (ran, failed, skipped, deleted)
-   Error messages
-   Service connections and disconnections
-   Applet run notifications (mobile only)

Your Activity feed will only display the most recent 100 items, and they cannot be removed from the timeline. To troubleshoot your Applet, [there are some useful tips in this article as well](https://help.ifttt.com/hc/en-us/articles/115010194547-Common-Applet-errors-and-troubleshooting-tips).

Here's a rundown to help you understand what you’re seeing, and why.

![Get_a_morning_reminder_about_your_first_meeting_daily_-_IFTTT_-_15_December_2021__1_.gif](https://help.ifttt.com/hc/article_attachments/4412965476763/Get_a_morning_reminder_about_your_first_meeting_daily_-_IFTTT_-_15_December_2021__1_.gif)

## Applet errors

### Applet ran

Your Applet ran as expected! If you expand this item, you’ll see more details about what exactly IFTTT was up to on your behalf. **Note**: If your Applet has multiple actions, you’ll see this item even if only one of those actions successfully ran.

### Applet updated

You successfully changed the configuration on one of your Applets, such as the hashtag to track for a Twitter Applet or the day of the week for an Email Digest Applet.

### Applet created

You made an Applet via [ifttt.com/create](https://ifttt.com/create) or the mobile app. Note: this only shows up when you build your own Applet, not when you turn just on an Applet.

### Applet turned on

When you turn on an Applet, we’ll put this confirmation in your activity feed.

### Applet turned off

If you turned off one of your Applets, you’ll see this item. If you see it but don’t recall turning off the Applet, expand the item to get a link to some troubleshooting tips.

### Applet skipped

This means the trigger ran, but the actions were skipped. It’s not necessarily bad news — if your Applet has filter code, it may skip because the conditionals in the code outlined weren’t met, e.g. [This Applet](https://ifttt.com/applets/xrdyz95v-get-a-notification-if-there-s-breaking-news-about-the-bay-area) will show up in your feed as “Applet skipped” when the trigger fires on breaking news but the code determines that the news isn’t related to the Bay Area.

#### Applets could also skip if:

-   We tried to run the action five times and weren’t able to make it happen
-   The time between the trigger and the action attempt times out
-   The action service is paused — this also only happens with Applets that use the Button, Note, or Camera widget services (you can see which services are paused by visiting [status.ifttt.com](https://status.ifttt.com/))

### Applet failed

This can happen for a few reasons. Let’s break it down:

-   If your Applet uses filter code, something might be wrong with the javascript
-   If you’re using a service for your action that has usage limits, the Applet will fail if you’ve hit those limits (e.g. the SMS service has a limit of 100 messages a month in North America)
-   If one of the services involved is paused — visit the [status page](https://status.ifttt.com/) to check out which services are currently paused and subscribe for updates
-   Our call to the trigger or action service took too long or failed, usually indicating some (temporary!) API issues on that app or device’s end
-   An unexpected error could sometimes pop up (we can’t prevent 100% of these, but know that we see them and do our best to investigate them)

### Applet published

Users and services can publish Applets for others to use from within the [IFTTT Platform](https://platform.ifttt.com/?utm_medium=Help&utm_source=Applets&utm_campaign=Troubleshooting_Applets&utm_term=&utm_content=). When you do, you’ll see this item in your feed.

## Service errors

### Service connected

This item confirms that you’ve linked a new app or device to your [[IFTTT]] account.

### Service disconnected

When you disconnect from a service, we’ll put this confirmation in your activity feed.

### Service edited

Sometimes you may want to link a different service account, or update a password and reconnect. In that case, you’ll see this item letting you know those updates went through.

### Service is offline

Uh oh! This usually means one of your apps or devices is no longer properly linked with [[IFTTT]]. Expand this item and we’ll help you reconnect via the service’s settings page, so you can get up and running again. If you don’t reconnect, we may give you a reminder a few days later — eventually, if you don’t reconnect, we’ll automatically disable the service and associated Applets, so we’ll try and give you enough time to fix it before we do that.

### Service is online

If we’ve seen your service was recently offline but has made a triumphant return to online status, we’ll give you the good news in your activity feed via this item.

### Usage limit exceeded

Some of the apps and devices we work with have [usage limits](https://help.ifttt.com/hc/en-us/articles/360001448453) on how much they can handle via [[IFTTT]]. We try and make these as transparent as possible, and let you know when you’re approaching a limit and when you’ve hit it. When you hit it and we can’t run an Applet, you’ll see this item in your feed.


---

#[[ifttt]] 