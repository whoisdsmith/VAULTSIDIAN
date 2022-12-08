---
created: 2022-08-05T11:13:30 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/cron-jobs-with-php-and-other-file-types
author: 
---

# Cron Jobs with PHP and other File Types | Bluehost Support

---
## Overview

This article will provide examples of different commands you can use in Cron Job. If you need a different explanation on Cron Jobs, please refer to this list of Cron Job articles.

___

-   [Cron Job Basics](https://www.bluehost.com/help/article/cron-job-basics)
-   [Setup or Remove a Cron Job](https://www.bluehost.com/help/article/setup-remove-or-edit-a-cron-job)
-   [Crons Running at Specific Date and Time](https://www.bluehost.com/help/article/cron-time)
-   [Specify a Cron Job to use a Specific php.ini File](https://www.bluehost.com/help/article/specify-a-cron-job-to-use-a-specific-phpini-file)
-   [Cron Jobs with PHP and other File Types](https://www.bluehost.com/help/article/cron-jobs-with-php-and-other-file-types#cron-job-with-php)

___

**Important:** The lines below are examples of command lines. Bold sections must be changed.

Depending on the home directory your account resides on you may need to adjust /home/ to /home#/. To view the home directory for your account, simply view the stats column on the main cPanel page of your account and look for the home directory.

## Cron Jobs with PHP and other File Type

**Please note:** We will be updating to PHP version **8.0** in batches beginning in 2022. Keep an eye out for communications on when your account will be updated and what changes, if any, you will need to make. For more information on updating content for PHP compatibility, read our guide on [What to do if your Site Does not Work with Newer Versions of PHP](https://www.bluehost.com/help/article/php-upgrade). To learn more about what is changing with PHP 8.0, please see [PHP.net's release notes](https://www.php.net/releases/8.0/en.php).

### PHP

Command to run a PHP5 cron job:

```
php /home/username/public_html/cron.php
```

Optional flags are sometimes required for a PHP cron job:

```
php -q /home/username/public_html/cron.php
```

Command to use a specific php.ini file:

```
php -c /home/username/public_html/php.ini /home/username/public_html/myscript.php
```

Command to GET a remote file:

```
/usr/bin/GET http://www.example.com/file.php
```

### Perl

Command to run a CGI cron job:

```
perl /home/username/public_html/cgi-bin/file.pl
```

### SSH

Command to run a shell script cron job:

```
/bin/sh /home/username/public_html/file.sh
```

### MySQL

It is good practice to not type your password out in the following commands but to use the -p flag alone and have the system prompt you for the password. This is why your password stays secure and is never on the server as plain text.

Command to import a database:

```
mysql -u mysql_user -ppassword database_name < backup.sql
```

Command to export a database:

```
mysqldump -u mysql_user -ppassword database_name > backup.sql
```

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
