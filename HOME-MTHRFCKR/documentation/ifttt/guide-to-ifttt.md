# Guide to tricking IFTTT into supporting multiple conditions and storing variables: IF this AND/OR that happened in the past, and now this happens, then do X. (Using spreadsheets and Filter code) : r/ifttt

![r/ifttt - Guide to tricking IFTTT into supporting multiple conditions and storing variables: IF this AND/OR that happened in the past, and now this happens, then do X. \(Using spreadsheets and Filter code\)](https://external-preview.redd.it/4JU3UogVXRczrXg9LrKTWkZfwKE5FKYqrpibUzCFv-8.jpg?width=640&crop=smart&auto=webp&s=edef87a7fdbb5f01ffd0f79257df69bf355f2b94)

TLDR: Instead of directly triggering your actions when a event happens, you can SET a cell in google sheets to save that the event happened. Then, set another applet to trigger when a computed cell based on the original cell updates. The computed cell could have any formula based on multiple events that are saved. Combine with filter code, and voila! 

I use this to turn on the lights automatically when I come home AFTER sunset, or when i'm already home and sunset happens. Also turn off the lights when I leave home, and mine also changes the color temp depending on the time of day. The color temp even works when i come home after sunset. 

**Step 1: Creating the conditions**

  1. Create a Google Sheet in a folder named "IFTTT" in your google Drive. 

  2. Create a Sheets file in the folder, I named mine "Lamps" 

  3. Create your conditions(Home, SunsetPassed) in the file like below. You can add as many as you want, and make it as complex as you want. 

[ ![r/ifttt - Guide to tricking IFTTT into supporting multiple conditions and storing variables: IF this AND/OR that happened in the past, and now this happens, then do X. \(Using spreadsheets and Filter code\)](https://preview.redd.it/ogde4bjgwt841.png?width=266&format=png&auto=webp&s=f023d9c028ce6be307d8fcf2877e2fc7b02bbed1) ](https://preview.redd.it/ogde4bjgwt841.png?width=266&format=png&auto=webp&s=f023d9c028ce6be307d8fcf2877e2fc7b02bbed1)

**Step 2: creating the logic**

Create a result spot that will change when you want to trigger your action: toggling the light in this case. 

Use the formula that gives the desired result. I want both home and SunsetPassed to be true, so i use AND. 

Give it a test to see if the result cell changes to TRUE when you want the lights to be on 

[ ![r/ifttt - Guide to tricking IFTTT into supporting multiple conditions and storing variables: IF this AND/OR that happened in the past, and now this happens, then do X. \(Using spreadsheets and Filter code\)](https://preview.redd.it/xdky49etwt841.png?width=303&format=png&auto=webp&s=8032633572966f9014db953fe9845de14cdc031a) ](https://preview.redd.it/xdky49etwt841.png?width=303&format=png&auto=webp&s=8032633572966f9014db953fe9845de14cdc031a)

**Step 3: Create the IFTTT applets**

You will need to create 4 applets for this: 

  1. Set B1 to TRUE when you come home using the location trigger 

  2. Set B1 to FALSE when you leave home area. 

  3. Set B2 to TRUE at sunset using Weather underground. (I use a location a bit east from me, because i like my lights to turn on a bit before sunset and sunset happens earlier there) 

  4. Set B2 to FALSE when you are asleep to reset it for the next day. I use 4am. 

[ ![r/ifttt - Guide to tricking IFTTT into supporting multiple conditions and storing variables: IF this AND/OR that happened in the past, and now this happens, then do X. \(Using spreadsheets and Filter code\)](https://preview.redd.it/pxkdp1i6wt841.png?width=862&format=png&auto=webp&s=948679006f7d424a16022d4e250946d5f1b9b18e) ](https://preview.redd.it/pxkdp1i6wt841.png?width=862&format=png&auto=webp&s=948679006f7d424a16022d4e250946d5f1b9b18e)

**Step 4: Set up the trigger(s)**

Now set up a trigger for when the result cell (B6 in my case) changes. You could set your lights to toggle, that might be enough. But the problem is that this will be triggered when RESULT changes from true to false and when it changes from false to true. To distinguish between the two, you need 2 applets with filter code, a feature meant for devs but available for anyone with the IFTTT platform. Here's how you do it: 

  1. Sign up at [platform.ifttt.com](https://platform.ifttt.com) if you haven't already. 

  2. Create an applet that turns ON your lights when the b6 field changes like normal 

  3. Add filter code that makes it cancel when the value changes to FALSE. Here's the code. Change the XXX to the service that you want to do, see the action text on the right of the text editor. Look for a line with "skip()" at the end. This will tell it skip this trigger if the value is "FALSE" 

if(GoogleSheets.cellUpdatedInSpreadsheet.Value == "FALSE"){ 

xxxxx.xxxxxx.skip() 

} 

Here's what it looks like for me: 

[ ![r/ifttt - Guide to tricking IFTTT into supporting multiple conditions and storing variables: IF this AND/OR that happened in the past, and now this happens, then do X. \(Using spreadsheets and Filter code\)](https://preview.redd.it/kip6mvmt1u841.png?width=1144&format=png&auto=webp&s=8469fe1b0409426e78ad0a1779fa5bd02447cd11) ](https://preview.redd.it/kip6mvmt1u841.png?width=1144&format=png&auto=webp&s=8469fe1b0409426e78ad0a1779fa5bd02447cd11)

**Step 4b: the other way around**

If you want your lights to turn off too when you leave, (when the value changes to false), you will need to create another applet in the IFTTT platform like you just did. The only difference is that you need if(GoogleSheets.cellUpdatedInSpreadsheet.Value == "TRUE"){ 

instead of 

if(GoogleSheets.cellUpdatedInSpreadsheet.Value == "FALSE"){ 

Step 5  
Expand and enjoy! Here's my masterpiece: 

[ ![r/ifttt - Guide to tricking IFTTT into supporting multiple conditions and storing variables: IF this AND/OR that happened in the past, and now this happens, then do X. \(Using spreadsheets and Filter code\)](https://preview.redd.it/fsu0fxgg2u841.png?width=1618&format=png&auto=webp&s=d6b327c8b43fb554a506250cb9476a75d325575c) ](https://preview.redd.it/fsu0fxgg2u841.png?width=1618&format=png&auto=webp&s=d6b327c8b43fb554a506250cb9476a75d325575c)


___


## Comments

### This is cool.

I remember this link from the past. Just adding here for info.


https://medium.com/@pebneter/when-if-is-not-enough-55b6e57d8742

The other thing I heard about recently was Home Assistant for raspberry pi. ⏤ by *tresswa* (↑ 3/ ↓ 0)
├─ I just read some of the explanation of what Apilio is, and it seems like its exactly the same idea as  what i just did.  Seems way easier too, but Google Sheets is free.... 

If i ever expand my smart home i will give it a go because my masterpiece sheet  takes like 20 applets just to toggle the lights and change color temps. I'm afraid of the monster i will create. ⏤ by *tom_0334* (↑ 3/ ↓ 0)
├── I like your method though. I haven’t tinkered with this level of stuff, but I’m going to follow your guide. ⏤ by *tresswa* (↑ 1/ ↓ 0)
├── What smart lights do you use? ⏤ by *tresswa* (↑ 1/ ↓ 0)
├─── I use Yeelight, mostly because i liked their led strip ⏤ by *tom_0334* (↑ 2/ ↓ 0)
├── “But google sheets is free. “ and thus is why I love this solution. ⏤ by *pickled_ricks* (↑ 1/ ↓ 0)
├── Also try Macrodroid, it is like a local non-cloud version of apilio.

Uses webhooks to set variables from IFTTT and super easy to learn.

I use routine + IFTTT + macrodroid for complex automation rules. ⏤ by *mikesrd2019* (↑ 1/ ↓ 0)
├── You're ready to level up. Get yourself a pi, and start around with screwing nodered, docker, and huginn. ⏤ by *jabies* (↑ 1/ ↓ 0)
└────


#### This seems like a neat workaround. I'll have to give it a try. ⏤ by *ElSabioUno* (↑ 2/ ↓ 0)

#### That's clever, saved that post! ⏤ by *m-p-3* (↑ 2/ ↓ 0)

##### Very helpful. Thanks! ⏤ by *burkybang* (↑ 1/ ↓ 0)

##### This is genius and I am so impressed. ⏤ by *pickled_ricks* (↑ 1/ ↓ 0)

##### Looks good! I asked a question earlier today that this can solve. Will try this next week. ⏤ by *marshallandy83* (↑ 1/ ↓ 0)

##### Very helpful. It's a good workaround but IFTTT should be able to do this from within the app by now. Without a smart person, our smart homes are nothing more than remote switches and sensors to turn lights on and off etc. A true smart home, would be more integrated and apply some logic to requests. Hopefully, the new alliance will be working on making things smarter and easier to setup and manage in the near future. ⏤ by *dnateo* (↑ 1/ ↓ 0)

##### This is exactly what I need. Thank you! ⏤ by *fc518* (↑ 1/ ↓ 0)
##### Thanks for your solution ! 

&amp;#x200B;

It works great but sadly there is a little delay so this can't apply to everything...

After some research i found Integromat and well, it looks amazing ! I'm only starting with it but it seems very powerful and the free tier is generous. It's originally a Zapier like but it has ifttt webhook integration as a huge bonus. And best of all it have a great interface. The only downside i can see is that it must be a little complicated for some users.

&amp;#x200B;

Just check it out :  [https://www.integromat.com/](https://www.integromat.com/) ⏤ by *Khelddit* (↑ 1/ ↓ 0)

#### Hello thanks for this guide, very helpful !

Just a tip that seems to work from my manual tests :

If you put an empty value in a cell, the update trigger is not processed so this can be used to only trigger an action when you change the value from an empty string to an actual value and not when you reset it ;)

This way you can avoid your filter in step 4

&amp;#x200B;

EDIT: Finally doing so is spaming applets fails in IFTTT so this is probably not a good idea ⏤ by *Khelddit* (↑ 1/ ↓ 0)

#### Thanks for explaining the filter code. I wanted a notification to let me know once my wife is on the way back from work (when she is about ten min eta to my workplace) to fetch me from my workplace. But I want the notification only in the evening as she passes by the road on the way to work too. 

#### Unfortunately the google sheet triggers can be quite unreliable. Sometimes, within a min it can give me a notifcation, sometimes up to 15 min, no notification. ⏤ by *sliko45* (↑ 1/ ↓ 0)

#### Slow clap. ⏤ by *givemethatflute* (↑ -1/ ↓ 0)

#### This is so good! I've made one to turn on my phone charger if I'm home and the battery is low, and turn it off again when the battery hits 80% (to reduce battery cycling). ⏤ by *Dan4096* (↑ 1/ ↓ 0

#article #ifttt 