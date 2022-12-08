---
created: 2022-08-05T09:11:02 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/php-pear-packages
author: 
---

# PHP Pear Packages | Bluehost Support

---
## Overview

Many PHP PEAR packages are already included with cPanel. Click the **PHP PEAR Packages** icon in the cPanel, then click **"Show System Installed Modules."** If the extension required is not listed, below are two options for installing additional PHP PEAR Packages.

___

-   [Installing PHP PEAR Packages included with cPanel](https://www.bluehost.com/help/article/php-pear-packages#install-cpanel)
-   [Manually installing PHP PEAR Packages](https://www.bluehost.com/help/article/php-pear-packages#install-manual)
-   [Configuring the php.ini file for installed PEAR Packages](https://www.bluehost.com/help/article/php-pear-packages#configure)

___

## Installing PHP PEAR Packages included with cPanel

The cPanel includes a selection of PEAR Packages that can automatically be installed. Simply follow these steps to use the cPanel's PEAR Package installer.

1.  Log in to your [Bluehost cPanel account.](https://my.bluehost.com/cgi-bin/cplogin)
2.  Under **Programming,** click the **PHP PEAR Packages** icon.
3.  Use the search box or click the button to show all available PEAR extensions.
4.  Click the **Install Now** button next to the extension you wish to install to your account.
5.  Follow the php.ini [configuration steps](https://www.bluehost.com/help/article/php-pear-packages#configure) shown below.

## Manually installing PHP PEAR Packages.

If the PEAR Package is not already installed and is not available to install via the cPanel, you may install the package manually by following these steps:

1.  Download the PEAR package from the internet, and often this will be from pear.php.net.
2.  Upload the file to the home directory inside the PHP folder. If the PHP folder does not already exist in the home directory, simply create one.
3.  Extract the file (if needed).
4.  Follow the php.ini [configuration steps](https://www.bluehost.com/help/article/php-pear-packages#configure) shown below.

## Configuring the php.ini file for installed PEAR Packages

In order for scripts to use the PEAR package(s) that have been installed with either of the above methods, make sure the php.ini file references the correct php/ directory.

1.  Open the php.ini file with a standard text editor or code editor. You may use the file manager edit tool.
2.  Locate the line which begins with include\_path. It should look similar to:
    
    ```
    include_path = ".:/usr/lib64/php:/usr/share/pear"
    ```
    
    **Note**: If this line begins with a semicolon, remove the semicolon
    
3.  Change this path to include the path of your PHP folder (separated by a colon). For example:
    
    ```
    include_path = ".:/usr/lib64/php:/usr/share/pear:/home#/username/php"
    ```
    
    Where /home#/username/ is the home directory for your account as shown in the main cPanel page on the left stats column.
    

If you still are unable to use the PHP PEAR package after following these steps, ensure you have modified the php.ini file, which is in the same directory as your PHP script. Alternatively, you may modify the php.ini file in public\_html and have chosen a single php.ini from the PHP Config icon in the cPanel. The single php.ini option indicates that all PHP scripts should use the php.ini file found in public\_html.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
