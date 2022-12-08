---
tags:: apps
---
# GitHub - nextcloud/notifications: Notifications app for Nextcloud

This app provides a backend and frontend for the notification API available in [Nextcloud](https://github.com/nextcloud/server/). The API is used by other apps to notify users in the web UI and sync clients about various things. Some examples are:

  * 📬 [Federated file sharing](https://github.com/nextcloud/server/tree/master/apps/federatedfilesharing): You received a new remote share
  * 📑 [Comments](https://github.com/nextcloud/server/tree/master/apps/comments): Another user mentioned you in a comment on a file
  * 🚢 [Update notification](https://github.com/nextcloud/server/tree/master/apps/updatenotification): Available update for an app or nextcloud itself
  * 📣 [Announcement center](https://github.com/nextcloud/announcementcenter): An announcement was posted by an admin

## Screenshot

![Screenshot of the notification icon and dropdown](https://raw.githubusercontent.com/nextcloud/notifications/master/docs/screenshot.png)

## Developers

### Install and enable the notifications app

  * Clone this app into the "apps" folder of your nextcloud instance.
    
    
    git clone https://github.com/nextcloud/notifications.git
    
    
    
    
    
    
      * 
    
    
    Enable the app (Log in as the admin into your nextcloud, go to "+ Apps" and search for the "notifications" app to
    enable it).
    
    
    
    
    
      * 
    
    
    When you modified the code make sure to execute make dev-setup from within the app´s root folder to install develop dependencies and afterwards build the javascript with make build-js-production.
    
    
    
    
    
    
    
    ### Creating notifications for your app
    
    
    
    
    For information how to make your app interact with the notifications app, see
    [Sending and processing/"mark as read" notifications as a Nextcloud App](https://github.com/nextcloud/notifications/blob/master/docs/notification-workflow.md)
    in the wiki.
    
    
    
    
    If you want to present notifications as a client, see [Reading and deleting notifications as an Nextcloud Client](https://github.com/nextcloud/notifications/blob/master/docs/ocs-endpoint-v1.md).
    
    
    
    
    
    


___

#article 