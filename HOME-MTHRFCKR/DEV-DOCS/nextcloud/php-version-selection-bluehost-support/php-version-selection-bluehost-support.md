---
created: 2022-08-05T09:00:44 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/php-version-selection
author: 
---

# PHP Version Selection | Bluehost Support

---
## Overview

**Please note:** We will be updating to PHP version **8.0** in batches beginning in 2022. Keep an eye out for communications on when your account will be updated and what changes, if any, you will need to make. For more information on updating content for PHP compatibility, read our guide on [What to do if your Site Does not Work with Newer Versions of PHP](https://www.bluehost.com/help/article/php-upgrade). To learn more about what is changing with PHP 8.0, please see [PHP.net's release notes](https://www.php.net/releases/8.0/en.php).

Our servers support PHP 7.4 and higher. PHP versions 7.4 and higher offer a significant improvement to speed and memory usage over past PHP versions. It also comes with better error handling and many bug fixes.

Before making the switch, you need to be aware of backward compatibility issues with scripts: Older PHP coding may not be compatible with newer PHP versions. Therefore, ensure to **"Avoid skipping versions,"** and instead, **"make updates incrementally."**

It is important to check first the "**Compatibility"** of your site against **new versions of PHP** before upgrading. Sites built with WordPress can use the [PHP Compatibility Checker plugin](https://wordpress.org/plugins/php-compatibility-checker/). You can also check [PHP Manual](https://www.php.net/manual/en/appendices.php) for reviewing the new and deprecated features of PHP.

___

-   [PHP Config](https://www.bluehost.com/help/article/php-version-selection#config)
-   [M](https://www.bluehost.com/help/article/php-version-selection#enable)[ultiPHP Manager](https://www.bluehost.com/help/article/php-version-selection#multiphp)
-   [Generate PHP.INI](https://www.bluehost.com/help/article/php-version-selection#generate-ini)
-   [What is php.ini?](https://www.bluehost.com/help/article/php-version-selection#What)
-   [Things to Keep in Mind](https://www.bluehost.com/help/article/php-version-selection#things)

___

The process for updating your PHP version will depend on what type of account you have set up. Older accounts use the Legacy interface, while updated accounts will use the Bluerock interface.

Most customers should use [Bluerock](https://www.bluehost.com/help/article/php-version-selection#multiphp) instructions. However, if you are unsure whether to use Bluerock or Legacy, please see this article [Bluerock vs. Legacy](https://www.bluehost.com/help/article/rock-vs-legacy). It will show you the difference between the two interfaces.

## How to Change Versions Using PHP Config (Legacy)

You can change your PHP version in Legacy accounts by following these steps:

1.  Log in to your [Bluehost control panel.](https://my.bluehost.com/)
2.  Under the Hosting tab, click **cPanel** in the submenu.  
    ![[Blue Host/Knowledge Base/PHP Version Selection  Bluehost Support/legacy-cpanel-tab.png]]
3.  Scroll down and look for the **programming** section, then click the **PHP Config.**   
    ![[php-config.png]]
4.  Select the version of PHP you're interested in using.
5.  Click **Save Change.**

**Note:** This option only works with Legacy Account. Please see below for Rock Instructions.

## How to Change Versions Using MultiPHP Manager (Bluerock)

You can change your PHP version in Bluerock accounts by following these steps.

1.  Log in to your [Bluehost control panel.](https://my.bluehost.com/)
2.  Click on the **Advanced** tab from the side navigation menu to the left.
3.  In the **SOFTWARE** section, click **MultiPHP Manager**.
    
    ![[phpinimanagerv1.gif]]
    
4.  Check the box next to the website(s) this PHP version will apply to.
5.  Choose the **PHP Version**, then click **Apply**.

**Please note:** If a domain is set to **Inherit**, it will automatically take on whatever PHP setting is assigned to the main domain.

## Generate php.ini

To generate a new php.ini file:

1.  Log in to your [Bluehost control panel.](https://my.bluehost.com/)
2.  Click on the **Advanced** tab from the side navigation menu to the left.
3.  Under the **Software** section, select the **MultiPHP INI Editor**.  
    ![[Blue Host/Knowledge Base/PHP Version Selection  Bluehost Support/rock-phpini-bh.png]]
4.  Select the path by clicking on the drop-down menu under Basic Mode **Selecting a location**.
5.  Choose the domain name.  
    ![[Blue Host/Knowledge Base/PHP Version Selection  Bluehost Support/multi-php-ini-editor-settings.png]]
6.  Once you're done, scroll down and click **Apply.**

**Note:** If you have any further questions about configuring the php.ini file, there are extensive descriptions within the file itself. You may also check this article [MultiPHP INI Editor](https://www.bluehost.com/help/article/multiphp-ini-editor) and find more help at http://www.php.net/docs.php.

## What is php.ini?

The php.ini file is the default configuration file for running applications that require PHP. It is used to declare settings and control variables such as upload sizes, file time-outs, resource limits, etc.   
Your server is already configured with standard settings for PHP, which your site will use by default. Unless you need to change one or more settings, there is no need to create or modify a php.ini file.

## Things to Keep in Mind

If you are using a custom php.ini file that references PHP modules that are not available in your selected version, your site may not work. Either remove the custom php.ini file (which will cause the server to use the default php.ini file) or create a php.ini file compatible with your selected version.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
