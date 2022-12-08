---
created: 2022-08-05T09:00:15 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/zend-optimizer-general#zend-optimizer
author: 
---

# Zend Optimizer | Bluehost Support

---
## What is Zend Optimizer?

Zend Optimizer is configured to work on any Bluehost server. To ensure it works properly for your account, you need to enable the "zend\_extension" option in your php.ini in all folders where the scripts are that need it. You can enable this using the "PHP Configuration" option in cPanel. Follow the steps in the [PHP Config](https://www.bluehost.com/help/article/php-config) article to install the default php.ini file to your account.

___

-   [What is Zend Optimizer?](https://www.bluehost.com/help/article/zend-optimizer-general#zend-optimizer)
-   [Common Issues](https://www.bluehost.com/help/article/zend-optimizer-general#common-issues)

___

## Enable Zend Optimizer

The simplest way is to enable Zend Optimizer before installing the default php.ini file. The configuration options are also listed if you want to copy the options and paste them into your current php.ini file.

## Common Issues

> **My Error Log gives an error that looks like "Zend Optimizer for PHP x.x.x Cannot Be Found" or similar -- How do I Confirm Zend Optimizer is configured properly?**

The **Zend Optimizer** is a module that improves the performance of PHP code. It is often used to help dynamic sites that use PHP have better page load performance; some sites may also require this--if it's missing, the site will fail to load properly and give an error similar to this one:   
_PHP Warning: Zend Optimizer for PHP 4.4.x cannot be found (expected at '/usr/local/Zend/lib/Optimizer-2.5.10/php-4.4.x/ZendOptimizer.so') - try reinstalling the Zend Optimizer in Unknown on line 0_

This may be visible directly on the website, or in your PHP error logs, or both. Zend Optimizer is installed on the server and just needs to be enabled in the php.ini file. You may need to [install the default php.ini](https://www.bluehost.com/help/article/php-version-selection) file as well.

If you are still seeing the error, please copy down the path to the script seeing issues; then, using either **File Manager** or **FTP** or **Bash** (terminal), verify the following:

-   The directory has a php.ini file
-   The php.ini file has no capitalizations in the filename and has permissions of 440 or greater.
-   The php.ini is newly created to rule out possible PHP version mismatches.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
