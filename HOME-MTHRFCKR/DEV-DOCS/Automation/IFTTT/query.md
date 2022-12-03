-   [How can I use a query?](https://help.ifttt.com/hc/en-us/articles/360053502173-What-is-a-query-#HowcanIuseaquery?)
-   [Do I need to use filter code to use a query?](https://help.ifttt.com/hc/en-us/articles/360053502173-What-is-a-query-#DoIneedtousefiltercodetouseaquery?)

A query is a way to request additional data that your Applet's [trigger](https://help.ifttt.com/hc/en-us/articles/4411016949403#Trigger) doesn’t provide. Queries run immediately after triggers, but before [filter code](https://help.ifttt.com/hc/en-us/articles/4411016949403#Filtercode).

Some examples of queries are [Google Calendar - List Events For a Date](https://ifttt.com/google_calendar/queries/list_events_for_date) and [Facebook - List Album Photos](https://ifttt.com/facebook/queries/list_album_photos).

## How can I use a query?

Queries can be used alongside triggers to build more powerful Applets. The data from the two can be used in your actions, or can combine with filter code to create all kinds of automations.

To add a query to your Applet, you'll first need to add a trigger, after which you can click on the plus button ( + ) and select **Add query**:

![How_to_add_a_query_to_an_Applet.gif](https://help.ifttt.com/hc/article_attachments/4412837810075/How_to_add_a_query_to_an_Applet.gif)

Queries, along with filter code, unlock Applets to go beyond **if this** to **if this _and_ this**.

For example, [the below Applet](https://ifttt.com/applets/VDdNBmiE-get-a-notification-when-the-iss-passes-over-your-house-but-only-if-it-is-clear-skies-and-after-dark) uses a query and some filter code to notify you when the ISS passes overhead, but only if it's nighttime: 

-   Trigger: [Space - ISS passes over a specific location](https://ifttt.com/space/triggers/space_station_overhead_soon_nasa)
-   Query: [Weather Underground - Current weather](https://ifttt.com/weather/queries/current_weather)
-   Filter code: [Skip the action if the current time is after sunrise and before sunset (when the sun is up)](https://help.ifttt.com/hc/en-us/articles/1260805234570-How-can-I-run-an-Applet-only-after-sunset-)
-   Action: [Notifications - Send a notification from the IFTTT app](https://ifttt.com/if_notifications/actions/send_notification)

<iframe src="//www.youtube-nocookie.com/embed/wSWCouDyMhY" width="560" height="315" frameborder="0" allowfullscreen=""></iframe>

## Do I need to use filter code to use a query?

Filter code is not required to use queries.

For example, the following Applet uses a Google Calendar query to send an email every day containing all calendar events for the upcoming day:

-   Trigger: [Date & Time - Every day at](https://ifttt.com/date_and_time/triggers/every_day_at)
-   Query: [Google Calendar - List Events For a Date](https://ifttt.com/google_calendar/queries/list_events_for_date)
-   Action: [Email - Send me an email](https://ifttt.com/email/actions/send_me_email) 
