---
created: 2022-08-05T11:17:43 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/advanced/cron-jobs/
author: 
---

# Cron Jobs | cPanel & WHM Documentation

---
## Cron Jobs

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/advanced/cron-jobs/)

___

Last modified: _July 6, 2022_

## Overview

Cron jobs are scheduled tasks that the system runs at predefined times or intervals. Typically, a cron job contains a series of simple tasks that the system runs from a script file.

Important:

-   Exercise caution when you schedule cron jobs. We recommend that you allow enough time between cron jobs for the previous cron job to complete. If you schedule them to run too often, the server could start another cron job before the last cron job ends. This duplication may degrade performance.
    
-   For more information about cron jobs, read [Red Hat’s Scheduling a Cron Job](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/ch-Automating_System_Tasks#s1-Scheduling_a_Recurring_Job_Using_Cron) documentation.
    

## Add a cron email

The _Cron Email_ section of the interface allows you to enter an email address for the system to send notifications when your cron jobs run. To set an email address, perform the following steps:

1.  In the _Email_ text box, enter the email address at which you wish to receive the notifications.
    
2.  Click _Update Email_.
    

### Disable email notifications

To disable email notifications for all cron jobs, remove the email address.

To disable email notifications for a single cron job, perform the following steps:

1.  Locate the cron job for which to disable email notifications in the _Current Cron Jobs_ table and click _Edit_.
    
2.  In the _Command_ text box, add the`/dev/null 2>&1` line to the end of the command. For example:  
    
    ```bash
    /usr/local/cpanel/bin/is_script_stuck /dev/null 2>&1
    ```
    
3.  Save your changes.
    

## Add a cron job

To create a cron job, perform the following steps:

1.  Select the interval at which you wish to run the cron job from the appropriate menus, or enter the values in the text boxes.
    
    -   _Common Settings_ — Select a commonly-used interval. The system will configure the appropriate settings in the _Minute_, _Hour_, _Day_, _Month_, and _Weekday_ text boxes for you.
        
    -   _Minute_ — The number of minutes between each time the cron job runs, or the minute of each hour on which you wish to run the cron job.
        
    -   _Hour_ — The number of hours between each time the cron job runs, or the hour of each day on which you wish to run the cron job.
        
    -   _Day_ — The number of days between each time the cron job runs, or the day of the month on which you wish to run the cron job.
        
    -   _Month_ — The number of months between each time the cron job runs, or the month of the year in which you wish to run the cron job.
        
    -   _Weekday_ — The days of the week on which you wish to run the cron job.
        
2.  In the _Command_ text box, enter the command that you wish the system to run.
    
    Important:
    
    -   You **must** specify settings for the _Minute_, _Hour_, _Day_, _Month_, _Weekday_, and _Command_ text boxes.
        
    -   Exercise **extreme** caution when you use the `rm` command in a cron job. If you do **not** declare the correct options, you may delete your home directory’s data.
        
    -   If your cron job runs a custom script, the script requires the execute permission. For more information, read Red Hat’s [Linux Permissions](https://www.redhat.com/sysadmin/introduction-chmod) documentation.
        
    
    Note:
    
    Specify the absolute path to the command that you wish to run. For example, if you wish to run the `public_html/index.php` file in your home directory, enter the following command:
    
    ```bash
    /home/user/public_html/index.php
    ```
    
3.  Click _Add New Cron Job_.
    

### Cron job example

To run a script that resides in your home directory once an hour, perform the following steps:

1.  In the _Common Settings_ menu, select the _Once Per Hour(0 \* \* \* \*)_ option.
    
2.  In the _Command_ text box, enter the script’s name. For example:
    
    ```bash
    ./my-script.sh
    ```
    
    Remember:
    
    You must set the correct file permissions to allow a script to execute.
    
3.  Click _Add New Cron Job_. The interface will display a success message.
    

## View existing cron jobs

The _Current Cron Jobs_ table displays your existing cron jobs.

### Edit a cron job

To edit a cron job, perform the following steps:

1.  Locate the cron job that you wish to edit and click _Edit_.
2.  Edit the settings that you wish to change and click _Edit Line_.

### Delete a cron job

To delete a cron job, perform the following steps:

1.  Click _Delete_ next to the cron job that you wish to delete.
2.  Click _Delete_.
