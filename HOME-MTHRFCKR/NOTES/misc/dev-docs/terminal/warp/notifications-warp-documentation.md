---
created: 2022-07-16T16:03:03 (UTC -04:00)
tags: []
source: https://docs.warp.dev/features/integrations-and-plugins
author: 
---

# Notifications - Warp Documentation

> ## Excerpt
> Have you ever ran a program on the terminal and started doing something else, only to find out a long time later that the program was waiting for a password to continue? No longer! Warp can now send you desktop notifications when you are away from the app and something meaningful happens in your terminal sessions, like when a command completes or when you're prompted to enter a password!

---
Have you ever ran a program on the terminal and started doing something else, only to find out a long time later that the program was waiting for a password to continue? No longer! Warp can now send you desktop notifications when you are away from the app and something meaningful happens in your terminal sessions, like when a command completes or when you're prompted to enter a password!

## 

Getting Started

To get started with notifications,

-   1.
    
    Go to Settings->Features in Warp and toggle Notifications on. You can also toggle notifications on via the command palette. Note: if you got to this page using the notifications banner, feel free to skip this step.
    

-   2.
    
    The first time you enable notifications in Warp, a MacOS request for permissions will appear.
    
    -   Depending on your MacOS version, this request will look slightly different. In any case, you will want to 'Allow'/'Accept' the request so that Warp is allowed to send you desktop notifications.
        
    
    -   If you accidentally denied it or would like to enable notifications later, check the troubleshooting guide below.
        
    

-   3.
    
    Once accepted, you're ready to receive notifications! If you'd like a zero-config setup, then you're all done! But, if you'd like to manually configure _which types_ of notifications you receive, keep on reading!
    

![](https://848020679-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MbqIgTw17KQvq_DQuRr%2Fuploads%2Fgit-blob-767326013a33c3ea59331afc88ea23f613523585%2Fnotifications-demo.gif?alt=media)

## 

Configuring Notifications

To configure notifications, go to Settings->Features and scroll to Notifications. Once there, you can configure the different notification triggers to your liking.

## 

Notification Triggers

A notification trigger is a reason for which Warp can send you a notification. Currently, we support two different triggers:

-   1.
    
    **Long-running commands.** Warp can send you a notification when a command completes after a configurable number of seconds.
    

-   2.
    
    **Password prompts.** Warp can send you a notification when a running command needs you to enter a password to proceed.
    

For either of these triggers, Warp will only send you a desktop notification if you are using a different app at the time the trigger is fired.

## 

Troubleshooting Warp Notifications

## 

I'm not receiving notifications when I expect them!

If you have notifications enabled in Warp (under Settings->Features) but you still aren't receiving desktop notifications, try the following:

-   1.
    
    Make sure that you are navigated away from Warp when you expect to receive the notification.
    

-   2.
    
    Make sure 'Do not Disturb' mode is turned off.
    

-   3.
    
    Go to System Preferences->Notifications and select Warp in the list. Make sure either banner style or alert style notifications are selected.
    

## 

I don't want to receive notifications!

The easiest way to disable notifications is within Warp itself. Go to Settings->Features and toggle off Notifications. After that, Warp won't try to send you notifications anymore!

## 

I have another problem!

We're sorry that notifications aren't working the way you expect them to! Please reach out to us on [Discord](https://warp.dev/discord) or [GitHub](https://github.com/warpdotdev/Warp/issues) and we can help you debug further!
