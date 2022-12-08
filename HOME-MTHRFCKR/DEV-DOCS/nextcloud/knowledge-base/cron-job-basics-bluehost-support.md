---
created: 2022-08-05T09:12:30 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/cron-job-basics
author: 
---

# Cron Job Basics | Bluehost Support

---
## Overview

This article will provide an overview of what Cron Jobs is. If you are unfamiliar with Cron Jobs, please read this carefully, as Cron Jobs is a more advanced feature of your account. If you are familiar with Cron Jobs and want instructions on using Cron Jobs, please refer to this list of Cron Job articles:

___

-   [Cron Job Basics](https://www.bluehost.com/help/article/cron-job-basics#what-is-cron-job)
-   [Setup, Remove or Edit a Cron Job](https://www.bluehost.com/help/article/setup-remove-or-edit-a-cron-job)
-   [Cron Running at Specific Date and Time](https://www.bluehost.com/help/article/specify-a-cron-job-to-use-a-specific-phpini-file)
-   [Specify a Cron Job to use a Specific php.ini File](https://www.bluehost.com/help/article/specify-a-cron-job-to-use-a-specific-phpini-file)
-   [Cron Jobs with PHP and other File Types](https://www.bluehost.com/help/article/cron-jobs-with-php-and-other-file-types)

___

## What is a Cron Job?

A **Cron Job** is a Linux command for scheduling a task (command). Cron Jobs allow you to automate specific commands or scripts on your server to complete repetitive tasks automatically.

This can be a very resourceful tool as a Cron Job can be set to run by 15 minute or hourly increments, a day of the week or month, or any combination of these. Bluehost limits Cron Jobs on shared servers to run in increments no less than every 15 minutes as excessive Cron Jobs can cause unnecessary loads on the server.

For example, you could set a Cron Job to delete temporary files every week so that unnecessary files are not using up your disk space. Some scripts, such as Drupal, may even require you to set up a Cron Job to perform certain functions.

**Warning:** It is important that you familiarize yourself with how Cron Jobs works. You need to have a good knowledge of Linux commands before you can use Cron Jobs effectively.

Check your script with your hosting administrator before adding a Cron Job.

For most Cron Jobs, there are three components present:

1.  The script that is to be called or executed.
2.  The command that executes the script on a reoccurring basis. This is typically set in the cPanel.
3.  The action or output of the script, which depends on what the script being called does. Frequently, scripts are called a Cron Job to modify files or databases; however, they can perform other tasks that do not modify data on the server, like sending out email notifications.

**Note:** Most scripts that require a Cron Job will give you specific instructions on what needs to be set up, frequently giving examples.

## Cron Job Limits

### Shared

**Important:** You **may not** run a Cron Job more often than every 15 minutes.

If you are getting errors when using the **GET** command, please contact us and request access.

### VPS and Dedicated Server

You may run a Cron Job as often as you desire.

We enable **GET** and **WGET** by default.

## Cron Job Environment

-   The initial working directory for the process is your home directory.
-   Because the processes are run in a non-interactive shell, .bashrc and other startup files are not read.
-   Only /usr/bin and /bin will be checked for the specified executable. Executables in other directories must be specified as absolute paths, such as /ramdisk/bin/php5, or relative paths, such as ./my\_program.
-   When running a script, the interpreter must be specified either in a valid #! line using a full path or at the command line.
-   File arguments must be specified with absolute paths or paths relative to the current working directory.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
