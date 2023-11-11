---
created: 2022-07-16T01:28:09 (UTC -04:00)
tags: [cron,job,run,on,gt,wish]
source: https://manage.accuwebhosting.com/knowledgebase/3043/How-to-set-the-cron-job-to-run-a-PHP-script-in-cPanel.html
author: AccuWeb Hosting
---

# How to Set the Cron Job to Run a PHP Script in cPanel? - Knowledgebase - AccuWebHosting

> ## Excerpt
> This article will help how to setup cron job for a PHP file in cPanel  
What is Cron?  
Cron

---

# How to Set the Cron Job to Run a PHP Script in cPanel?

___

**This article will help how to setup cron job for a PHP file in cPanel**

## What is Cron?

Cron is a Linux module that allows you to run commands at specified time intervals. It is used to schedule a task that is executed periodically. In Windows, it’s called Scheduled Tasks.  

  

It can be used to schedule jobs such as commands or shell scripts to perform backups, schedule package updates, run script files etc., that run on the server periodically and automatically in the background at specific times, dates, or intervals.

## What is PHP Script?

PHP (**Hypertext Preprocessor**) is a widely-used open source general-purpose scripting language that is especially suited for web development and can be embedded into HTML. Before you think to run a program, we will need to write a PHP script. This script could be related to the task that you want to perform.  

  

**There are four main parts of a cron command.**

1.  **Timing** – set the minutes, hours, days, months, and weekday.
2.  **Execute** – the cron job needs to call **PHP** to run, which is located at **/usr/bin/php** path.
3.  **Script Path** – the full path of the file you want to run.  
    \[For example, /home/user/public\_html/index.php\]
4.  **Output** – you can write the cron output to a file or discard it, **/dev/null 2>&1** will discard. You can skip this optional part.

**How to set the cron job to run a PHP script in cPanel?**

1.  Login to cPanel.  

2.  Go to cPanel >> Home >> Advanced >> Cron Jobs.  
      

    ![01-click-on-the-cronjob-option](https://manage.accuwebhosting.com/kb-images/How-to-setup-cron-for-a-PHP-script-in-cPanel/01-click-on-the-cronjob-option.png "01-click-on-the-cronjob-option")  

## Set a Cron Email

1.  In the Email text box, enter the email address on which you wish to receive the cron notifications. Click on **Update Email** button.  
      

    ![02-update-email-for-cron](https://manage.accuwebhosting.com/kb-images/How-to-setup-cron-for-a-PHP-script-in-cPanel/02-update-email-for-cron.png "02-update-email-for-cron")  

      

    **Disable email notifications:**  

      

    To disable email notifications for all cron jobs, remove the email address. If you do not want an Email notification for the Cron, you should add /dev/null 2>&1 in the command field. It will send the output to NULL.

## Add New Cron Job

Please refer to the following steps to add a cron job, perform the following steps.

1.  Select the interval at which you wish to run the cron job from the appropriate menus, or enter the values in the text boxes under Common Settings. It allows you to select a commonly-used interval. The system will configure the appropriate settings in the Minute, Hour, Day, Month, and Weekday text boxes for you. So, you can select the appropriate option from combo-box if you don't want to enter values manually.  

-   **Minute** — Select the number of minutes between each time the cron job runs, or the minute of each hour on which you wish to run the cron job.  

-   **Hour** — Select the number of hours between each time the cron job runs, or the hour of each day on which you wish to run the cron job.  

-   **Day** — Select the number of days between each time the cron job runs, or the day of the month on which you wish to run the cron job.  

-   **Month** — Select the number of months between each time the cron job runs, or the month of the year in which you wish to run the cron job.  

-   **Weekday** — Select the days of the week on which you wish to run the cron job.  

-   **General Examples of cron job:**  
    \* \* \* \* \* /usr/bin/php /home/user/public\_html/index.php > /dev/null 2>&1  
    
-   **Domain-specific example:  
      

    **/usr/local/bin/ea-php56 /home/user/public\_html/index.php  

    
-   In the above example, replace “ea-php56” with the PHP version assigned to the domain you want to use on a script. You can go to the MultiPHP Manager to check PHP version assigned to your domain.  

-   In the Command text box, enter the command that you wish the system to run OR enter the path of your PHP script.  

2.  Click **Add New Cron Job** button.  
      

    ![03-add-new-cron-job](https://manage.accuwebhosting.com/kb-images/How-to-setup-cron-for-a-PHP-script-in-cPanel/03-add-new-cron-job.png "03-add-new-cron-job")  

## Edit a Cron Job

1.  To edit a cron job, perform the following steps:  
      

    \- Locate the cron job that you wish to edit and click **Edit**.  

      

    \- Edit the settings that you wish to change and click **Edit Line**.  

      

    ![04-edit-line-cron-job](https://manage.accuwebhosting.com/kb-images/How-to-setup-cron-for-a-PHP-script-in-cPanel/04-edit-cron-job.png "04-edit-cron-job")  

      

    ![05-edit-line-cron-job](https://manage.accuwebhosting.com/kb-images/How-to-setup-cron-for-a-PHP-script-in-cPanel/05-edit-line-cron-job.png "05-edit-line-cron-job")  

## Delete a Cron Job

1.  To delete a cron job, perform the following steps:  
      

    \- Click on **Delete** button.  

      

    ![06-delete-the-cron-job.png](https://manage.accuwebhosting.com/kb-images/How-to-setup-cron-for-a-PHP-script-in-cPanel/06-delete-the-cron-job.png "06-delete-the-cron-job")  

      

    NOTE: If you schedule a cron job to run very often, they may degrade your server performance.

___

→ Looking to set automated tasks on Linux VPS using cron? Please refer to [**set cron on Linux VPS**](https://manage.accuwebhosting.com/knowledgebase/2438/How-to-set-Automate-Tasks-on-a-Linux-VPS-Using-Cron.html) for more details.   

  

→ Looking to set cron to backup MySQL DB and remove older backup? Please refer to [**set cron for MySQL DB**](https://manage.accuwebhosting.com/knowledgebase/3632/How-to-set-up-a-cron-to-take-MySQL-Database-Backup-daily-and-remove-the-older-backup-files-that-are-older-than-10-days.html) for more details.

___

### Was This Answer Helpful?

Yes No
