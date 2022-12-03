# Use Siri to Run Applets - IFTTT

---


-   [Create your Applet](https://help.ifttt.com/hc/en-us/articles/360053753113-Use-Siri-to-Run-IFTTT-Applets#CreateyourApplet)
-   [Create the Siri Shortcut](https://help.ifttt.com/hc/en-us/articles/360053753113-Use-Siri-to-Run-IFTTT-Applets#CreatetheSiriShortcut)
-   [Tell Siri](https://help.ifttt.com/hc/en-us/articles/360053753113-Use-Siri-to-Run-IFTTT-Applets#TellSiri)

![mceclip0.png](https://help.ifttt.com/hc/article_attachments/360088595933/mceclip0.png)  

Voice commands are becoming a popular method of interacting with devices and apps. You can use voice commands to run actions for any service on IFTTT.

Siri is the voice-activated assistant from Apple. Siri can be used on your iOS or iPadOS device, HomePod, or Apple Watch to kick off an Apple Shortcut that triggers an IFTTT Applet.

## Create your Applet

Your applet will use [Webhooks](https://ifttt.com/maker_webhooks) as the trigger. It can use any action you choose. If you’re subscribed to IFTTT Pro or IFTTT Pro+, you can trigger multiple actions and include [queries](https://help.ifttt.com/hc/en-us/articles/360053502173-What-is-a-query-) and [filter code](https://help.ifttt.com/hc/en-us/articles/360052451954-Building-with-filter-code). We’ll cover those advanced use cases in a separate article.

1.  Head to [https://ifttt.com/create](https://ifttt.com/create) and add Webhooks 'Receive a web request' as the **_If This_** trigger  
    ![mceclip2.png](https://help.ifttt.com/hc/article_attachments/360087457474/mceclip2.png)
2.  When prompted, enter your Event Name. You’ll use this information in a few minutes to set up the Siri portion of your setup. For this example, I’ll use turn\_off\_lights.
3.  Add the **_Then_** portion of your applet -- this is the action service -- authenticate if necessary, and select any required settings. For this example, I’ll select Yeelight's 'Toggle lights on/off'.  
    ![mceclip3.png](https://help.ifttt.com/hc/article_attachments/360088596113/mceclip3.png)
4.  Click Continue 
5.  When prompted, edit the Applet title if you want to customize it
6.  Click Finish to save your new Applet  
    ![mceclip4.png](https://help.ifttt.com/hc/article_attachments/360088596153/mceclip4.png)  
    

## Create the Siri Shortcut

1.  While still on IFTTT, click (or tap on mobile) on the Webhooks ![mceclip6.png](https://help.ifttt.com/hc/article_attachments/360088596333/mceclip6.png) icon to view the Service detail page
2.  Click (or tap on mobile) the **Documentation** button to view your private key and the URL you can use with this service. _Don’t share this secret key with anyone or they’ll be able to use it to run your Applets._
3.  On the Webhooks documentation page, in the **{event}** field, enter the Event Name you set in step 3 above. Mine is **turn\_off\_lights**. Keep this documentation page handy -- you’ll need to copy items from it in the next few steps.
4.  On your iOS device, open the Shortcuts app
5.  Tap + to add a new shortcut
6.  Tap + to add action. Search for and add the 'Text' item.
7.  Copy the private key from your IFTTT Webhooks screen and paste it into the Text area in the new shortcut
8.  Tap + to add a second action. Search for and add a second 'Text' item.
9.  Enter the Event Name you set up earlier in IFTTT. Mine is **turn\_off\_lights**. 
10.  Tap + to add a third action. Search for and add a 'URL' item.
11.  Copy the entire URL you see on your IFTTT Webhooks screen and paste it into the URL area in the new shortcut. Make sure it includes your event name.  
    [  
    https://maker.ifttt.com/trigger/turn\_off\_lights/with/key/xLDzNMtSYfBnQmVqVLxqKQT3\_NJ\_R3DvISBVsx4Jh\_xxf1a2rgUrrnrWrLnwxXN](https://maker.ifttt.com/trigger/turn_off_lights/with/key/xLDzNMtSYfBnQmVqVLxqKQT3_NJ_R3DvISBVsx4Jh_xxf1a2rgUrrnrWrLnwxXN)  
    Your shortcut should look like this (with your own values in the text and URL fields).
    
    ![mceclip0.png](https://help.ifttt.com/hc/article_attachments/360087457854/mceclip0.png)
    
12.  Tap + to add a fourth and final action. Search for and add a 'Get contents of URL' item.
13.  Tap Show More in the new action you added and confirm Method is set to 'GET'  
    ![mceclip2.png](https://help.ifttt.com/hc/article_attachments/360088596553/mceclip2.png)  
    
14.  Tap Next, give your new shortcut a name (this is what you’ll use to tell Siri to run), and save it. I named mine “Turn off the lights”.

## Tell Siri

To run your new Applet, all you need to do is tell Siri! In my example, I say, “Hey Siri, turn off the lights.” It’ll work on any Siri-enabled Apple device logged into the same Apple ID you used when you created your shortcut.

Remember, you can always set any Applet to notify you when it runs (it will do so with a notification from the [IFTTT app](https://apps.apple.com/us/app/ifttt/id660944635)) and you can also check your Activity logs in the IFTTT app and on IFTTT.com to see information about each Applet event.

Enjoy!