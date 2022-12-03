-   [Running Applets only during certain times](https://help.ifttt.com/hc/en-us/articles/360052451954-Building-with-filter-code#RunningAppletsonlyduringcertaintimes)
-   [Running actions every other week](https://help.ifttt.com/hc/en-us/articles/360052451954-Building-with-filter-code#Runningactionseveryotherweek)
-   [Running actions based on trigger data](https://help.ifttt.com/hc/en-us/articles/360052451954-Building-with-filter-code#Runningactionsbasedontriggerdata)
-   [Searching for a keyword and skipping an action](https://help.ifttt.com/hc/en-us/articles/360052451954-Building-with-filter-code#Searchingforakeywordandskippinganaction)
-   [Updating action fields](https://help.ifttt.com/hc/en-us/articles/360052451954-Building-with-filter-code#Updatingactionfields)

Regular Applets have a very straightforward logic to them - when a trigger fires for a new event, an action is always run. But what if you want to have more say in when or how exactly this happens?

Filter code gives you some control over this logic. Filter code is a bit of JavaScript code (the ES5 flavor, but let's not get _too_ technical just yet!) that runs right after a trigger fires.

With filter code you can do two things:

-   Skip an action or multiple actions.
-   Change the values of the fields the action will run with.

Combine that with the power of Javascript logic and you can build Applets that only run when certain conditions are met or Applets with multiple actions where specific actions depend on the data from the trigger.

Let's look at examples of filter code in action.

## Running Applets only during certain times

<iframe src="//www.youtube-nocookie.com/embed/P_wjDKNu5dk" width="560" height="315" frameborder="0" allowfullscreen=""></iframe>

If you have Applets that notify you about new events or updates from a service, but these notifications are not important enough to wake you up at night, you can use filter code to skip notifications outside your waking hours. This is one of the most common use-cases and fortunately, a simple one to set up

```
let currentHour = Meta.currentUserTime.hour();if (currentHour < 9 || currentHour >= 23) {  Email.sendMeEmail.skip(`It's ${currentHour}, only running between 9am and 11pm`);    // You can pass a message to skip() and it will be recorded in the Applet's    // activity feed when an action is skipped. This is useful for debugging.}
```

In the filter code, you have access to the time object Meta.currentUserTime, which is technically [a momentjs object](https://momentjs.com/docs/#/get-set/). It has a lot of built-in methods for getting and manipulating the different parts that make up the current time and date (taking into account the time zone the user set in their IFTTT account setting).  
  
For this example, you need to get the integer value, the number that represents the current hour (in 24h format). The hour() method provides that, so we assign the value to the currentHour variable on the first line.

We then build a simple IF statement that checks two conditions: either the value of currentHour is less than 9 OR it’s greater than or equals to 23 (11pm). The || symbols represent the OR logic we need in this example.

Lastly, in the { } we have just one command - skip the email action. If the current hour is outside the 9am - 11pm interval, this code will stop the Applet. Any Actions afterward will not run.

## Running actions every other week

Another interesting Applet idea that is now possible with the filter code is running an action on a bi-weekly schedule. If you want your Applet to run on certain days of the week, then the Date&Time service can help, but it’s powerless if you have a bi-weekly action(s). It’s also not useful when there is another trigger that needs to fire and the schedule is just another layer of logic on top of it.

```
// Filter code to check the week number and if the week number is odd, // the actions will be skipped.// This code makes use of the moment.js function moment().week() // which returns the current week number in the number format.let thisWeek = Meta.currentUserTime.week();//Change 0 to 1 to make it run on odd weeks insteadif (thisWeek % 2 != 0) {    IfNotifications.sendNotification.skip(`Only running on even weeks. Week number ${thisWeek}`);}
```

## Running actions based on trigger data

If you have a few Applets that take alerts (from a monitoring, security, or weather service, for example) and use different actions to notify you, you can combine them in one Applet and build the filter code logic to skip some notification methods if the alert is not important enough.

In this example, we have an Applet that takes the current temperature from the Weather Underground trigger and three actions - sendMeEmail, sendMeText and sendNotification. The logic is then built to skip the text message if the temperature does not rise above 90, skip both a text and a push notification if it’s still under 75. All three actions will fire if the temperature rises above 90

```
let currentTemp = Number(Weather.currentTemperatureRisesAbove.TempFahrenheit);if (currentTemp < 90 && currentTemp > 75) {   Sms.sendMeText.skip(`Temperature is ${currentTemp}`);} else if (currentTemp <= 75) {   IfNotifications.sendNotification.skip(`Temperature is ${currentTemp}`);   Sms.sendMeText.skip(`Temperature is ${currentTemp}`);}
```

## Searching for a keyword and skipping an action

This is a simple starter filter code that searches for a keyword in a Google Calendar event description and skips the notification action if the keyword is not found. 

```
let str = GoogleCalendar.anyEventStarts.Description;let searchTerm = 'IFTTT';let indexOfFirst = str.indexOf(searchTerm);if (indexOfFirst === -1) {  IfNotifications.sendNotification.skip("Not found!")}
```

The code works by taking the search term and trying to locate its exact match in the calendar event description. If there are no matches, the result is -1, and the IF statement skips the notification accordingly.

## Updating action fields

In this example, there is an array of colors and a way of picking a random color from the list. This color is then used with a Lifx.color action to change the color of your lights.

```
let colors = ["#FF8400", "#FF0000", "#15FF00", "#FF00D4","#00D4FF","#003CFF"]let index = Math.floor((Math.random() * colors.length))Lifx.color.setAdvancedOptions('color: ' + colors[index] + '; brightness: 1; duration: 12')
```

Instructions for adding filter code to your Applets can be found [here](https://help.ifttt.com/hc/en-us/articles/360052451954). And if you're not too confident writing code, check out our [filter code generators](https://help.ifttt.com/hc/en-us/articles/1260805596369) to get started!