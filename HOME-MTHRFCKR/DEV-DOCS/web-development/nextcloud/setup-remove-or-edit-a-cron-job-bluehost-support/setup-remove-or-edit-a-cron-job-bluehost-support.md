---
created: 2022-08-05T09:12:26 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/setup-remove-or-edit-a-cron-job
author: 
---

# Setup, Remove, or Edit a Cron Job | Bluehost Support

---
This article will provide instructions on how to setup, remove or edit a Cron Job. If you need a different explanation on Cron Jobs, please refer to this list of Cron Job articles:

___

-   [Cron Job Basics](https://www.bluehost.com/help/article/cron-job-basics)
-   [Setup, Remove, or Edit a Cron Job](https://www.bluehost.com/help/article/setup-remove-or-edit-a-cron-job#setup-cron-job)
-   [Crons Running at Specific Date and Time](https://www.bluehost.com/help/article/cron-time)
-   [Specify a Cron Job to use a Specific php.ini File](https://www.bluehost.com/help/article/specify-a-cron-job-to-use-a-specific-phpini-file)
-   [Cron Jobs with PHP and other File Types](https://www.bluehost.com/help/article/cron-jobs-with-php-and-other-file-types)

___

## Setup a Cron Job

Cron jobs allow you to automate certain commands or scripts on your site. You could set a command or script to run at a specific time every day, week, etc. For example, you could set a cron job to delete temporary files every week to free up disk space.

1.  Log in to your [Bluehost control panel.](https://bluehost.com/cgi-bin/cplogin)
2.  Locate the **Cron Job** Icon:  
    **Bluerock Account:**
    
    1.  From the **Advanced** tab from the side navigation menu to the left, then look for the **Advanced** section.
    2.  Click the **Cron Jobs** icon.  
        ![[Advanced-advanced-cron-jobs.png]]
    
    **Legacy Account:**
    
    1.  Select the cpanel tab from the navigation menu that stretches across the top of your screen.
    2.  Scroll down and under the advanced section, click the **Cron Jobs** icon.  
        ![[Legacy-cpanel-advanced-cron-jobs.png]]
    
    **Warning:** You need to have a good knowledge of Linux commands before you can use cron jobs effectively. Check your script with your hosting administrator before adding a cron job.
    
3.  Make sure the **current email** address is valid. Enter a new email and click the **Update Email** button.  
    ![[Advanced-advanced-cron-jobs-update-email.png]]
    
    -   **Common Settings**– You can use this drop-down list to populate all but the last fields.
    -   **Minute** – The minute setting for the cron job.
    -   **Hour** – The hour setting for the cron job.
    -   **Day** – The day setting for the cron job.
    -   **Month** – The month setting for the cron job.
    -   **Weekday** – The weekday setting for the cron job.
    -   **Command** – The cron job command to execute. If you want to execute a script, then it would look similar to the command below.
    
    ```
    /usr/local/bin/php -c /home/username/public_html/myscript.php
    ```
    
4.  Set the frequency of your Cron Job by using the drop-down box for each setting, or use the **Common Settings** to choose from a list of regularly used intervals. Common Settings include every 15 minutes to once a year.  
    ![[Advanced-advanced-cron-jobs-common-settings-drop-down.png]]
5.  Enter in the desired command and click the **Add New Cron Job** button.  
    ![[Advanced-advanced-cron-jobs-add-new-cron-job.png]]

You have just created a Cron Job to execute a file at a certain time and date with the desired repetition.

## View existing cron jobs

The Current Cron Jobs table displays your existing cron jobs.

![[Advanced-advanced-cron-jobs-current-cron-jobs.png]]

### Edit a cron job

To edit a cron job, perform the following steps:

1.  Locate the cron job that you wish to edit and click the **Edit** button.
2.  Edit the settings that you wish to change and click **Edit Line**.

### Delete a cron job

To delete a cron job, perform the following steps:

1.  Click the **Delete** button next to the cron job that you wish to delete.
2.  Click the **Delete** button again to delete it successfully.

**Note:** The edit panel has fewer common settings to choose from, so if you are having trouble getting the correct interval, copy the command, delete the Cron Job, and then recreate it using the Add New Cron Job section.
