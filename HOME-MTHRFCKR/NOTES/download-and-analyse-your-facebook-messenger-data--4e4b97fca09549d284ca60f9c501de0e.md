# Download and Analyse Your Facebook Messenger Data | by June Tao Ching | Towards Data Science

![Download%20and%20Analyse%20Your%20Facebook%20Messenger%20Data%20%204e4b97fca09549d284ca60f9c501de0e/1AvnDAyE7jHxKu7KbnRVHaQ.jpeg](Download%20and%20Analyse%20Your%20Facebook%20Messenger%20Data%20%204e4b97fca09549d284ca60f9c501de0e/1AvnDAyE7jHxKu7KbnRVHaQ.jpeg)

Photo by [Tim Bennett](https://unsplash.com/@timbennettcreative?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/facebook?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

With over 2 billions user, Facebook is the most popular platform today. Most of the facebook users use Facebook Messenger app to communicate to each other, including me. I am really curious how I behave on this platform and how the rise of other social media apps like Instagram, WeChat and SnapChat impact my usage on Facebook.

Today, I am going to show you how to download your Facebook message data and how to analyse it.

## Download your Facebook Data

-   Open your Facebook and go into **Settings & Privacy** > **Settings**
-   Go to **Your Facebook Information** > **Download Your Information**
-   Select the data range “**All of my data**”, format “**JSON**” and Media Quality “**High**” _(Feel free to change the media quality as high media quality will consume more storage)_
-   Select **Messages** only _(At this case, I am only interested at my message data, you may try on other data as well)_
-   Click on **Create File**

Facebook will create a zip file on their server and notify you when the file is ready to download. It took me around one day to get the zip file.

## Pre-process your Facebook Message Data

Before working on any analysis, the first thing that we have to do is pre-process the data. These are the folder inside the message data after we unzip the downloaded file.

Folders in Message Data

We are only interested at inbox.

    Folder Structure of Inbox:
    📂 inbox
    ┣ 📂 alex
    ┃  ┗ 📜 message_1.json
    ┃  ┗ 📂 photos
    ┗ 📂 brian
       ┗ 📜 message_1.json
       ┗ 📜 message_2.json
       ┗ 📜 message_3.json
       ┗ 📂 photos

This is the general folder structure in Inbox. If you have a lot text message with someone, you might have multiple message JSON files.

Now, we have to write a Python script to extract the information we need in all these JSON files.

I am going to iterate all the subfolders in inbox to read all JSON files with filename starts with “message”.

`folders.remove(".DS_Store")` is used here to remove the system file in macOS. It is to prevent the error in the loop later. _(Windows user can ignore this)_

`datetime.fromtimestamp(message[“timestamp_ms”] / 1000).strftime(“%Y-%m-%d %H:%M:%S”)` is used here to convert the timestamp into something that is readable by human. I also converted it into string so I can write it into an output file without any issue.

This is the sample output file you will get with the Python Script above. Now you can analyse your Facebook message data with any of the visualisation tool.

    output.csv
    "2016-03-20 13:48:46",Brian,Okay
    "2016-03-20 13:48:10",June,See you
    "2016-03-20 13:48:01",Matthew,We are at ....

## Analyse my Facebook Message Behaviour

My Facebook Messenger Activity Trend

-   Separation of Messenger from Facebook App does increased my usage on Facebook Messenger. At first, I really hate it because it forced me to use 2 different apps. But I found out that it actually reduced my distraction by Facebook and enable me to focus on messaging (No more non-stop scrolling on Facebook while messaging!).
-   I was hooked to SnapChat for a certain period because of its fancy face filter and the 24 hours stories feature. The drop of usage is started by SnapChat but it wasn’t the main reason of the continuous dropping because Instagram also introduce Stories feature!
-   When Instagram started to introduce DM (Direct Message) feature, it didn’t manage to hook me because it didn’t have the feature I am looking for such as call, special interactions (sticker, gifs, etc) at that time. When Instagram also released Stories feature, it immediately hooked me into the platform because I already have a lot of friends using Instagram (I believed this is also one of the major reason Instagram can win over SnapChat, Instagram already has huge user base compared to SnapChat).
-   After 2017, my was diversified into more apps such as WeChat, WhatsApp and Telegram. This caused continuous dropping on usage since 2017.

Other than this analysis, we also can work on some analysis like

-   Usage on weekday vs weekend
-   Usage on day vs night
-   What is the phrase/word you use the most frequent?

Now you have learnt how to **download your Facebook message data** and analyse it. I hope this article is useful to you. Do drop me a comment if I made any mistakes or typos.

You can view the complete script in my **[Github](https://github.com/chingjunetao/medium-article/blob/master/analyse-facebook-messenger-data/analyse-fb-message.py)**. Cheers!

**If you enjoyed reading this piece, you might also enjoy these:**

**You can find links to my other works on Medium and follow me [here](https://medium.com/@chingjunetao). Thanks for reading!**
