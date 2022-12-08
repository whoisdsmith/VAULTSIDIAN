---
created: 2022-08-05T09:10:46 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/configure-the-php-environment-with-php-ini
author: 
---

# How To Configure The PHP Environment With PHP ini | Bluehost Support

---
___

-   [Overview](https://www.bluehost.com/help/article/configure-the-php-environment-with-php-ini#overview)
-   [Update PHP Version or Generate new php.ini File](https://www.bluehost.com/help/article/configure-the-php-environment-with-php-ini#update-php)
-   [Add PHP handlers](https://www.bluehost.com/help/article/configure-the-php-environment-with-php-ini#php-handler)
-   [CGI Type](https://www.bluehost.com/help/article/configure-the-php-environment-with-php-ini#cgi-type)
-   [Standard PHP (Default)](https://www.bluehost.com/help/article/configure-the-php-environment-with-php-ini#standard-php)
-   [PHP Single php.ini](https://www.bluehost.com/help/article/configure-the-php-environment-with-php-ini#php-single-php)
-   [PHP FastCGI](https://www.bluehost.com/help/article/configure-the-php-environment-with-php-ini#php-fastcgi)

___

## Overview

The version of PHP helps keep your site secured, running efficiently, and compatible with any plugins. This article explains how to generate a new php.ini file if you are into changing the PHP version or made an error with your current php.ini file.  Upgrading your PHP will automatically create the new php.ini file.   

## Update PHP Version or Generate new php.ini File

**Important note**: PHP versions PHP 7.0 and PHP 7.1 are **deprecated**. We recommend that you update to a supported version of PHP.

**Please note:** We will be updating to PHP version **8.0** in batches beginning in 2022. Keep an eye out for communications on when your account will be updated and what changes, if any, you will need to make. For more information on updating content for PHP compatibility, read our guide on [What to do if your Site Does not Work with Newer Versions of PHP](https://www.bluehost.com/help/article/php-upgrade). To learn more about what is changing with PHP 8.0, please see [PHP.net's release notes](https://www.php.net/releases/8.0/en.php).

### Bluerock

1.  Log in to your [Bluehost control panel.](https://my.bluehost.com/)
2.  Click the **Advanced** tab from the side navigation menu to the left.  
    ![[Blue Host/Knowledge Base/How To Configure The PHP Environment With PHP ini  Bluehost Support/rock-advanced-tab.png]]
3.  Under the **Software** section, click on the **MultiPHP Manager** icon.
    
    ![[Blue Host/Knowledge Base/How To Configure The PHP Environment With PHP ini  Bluehost Support/rock-bluehost-software-multiphp-manager.png]]
    
4.  Select the domain that you want to set up or update from the list.  
    ![[select-domain-multiphp-manager.png]]
5.  Select the version of PHP you would like to use at the top right-hand side.  
    ![[select-php-version-multiphp-manager.png]]
6.  Click the **Apply** button to finish the update.  
    ![[select-apply-button-multiphp-manager.png]]

### Legacy

1.  Log in to your [Bluehost control panel.](https://my.bluehost.com/)
2.  Click the **cpanel** sub-tab from the navigation menu that stretches across the top of your screen.  
    ![[Blue Host/Knowledge Base/How To Configure The PHP Environment With PHP ini  Bluehost Support/legacy-cpanel-tab.png]]
3.  Locate the **PHP Config** tool under the programming category.  
    ![[legacy-php-config.png]]
4.  Select the domain that you want to set up or update.
5.  Choose the version of PHP you will be using.
6.  Choose any extensions you might need for your scripts.
7.  Click the **Save Changes** button.

If you have any further questions about configuring the php.ini file, there are extensive descriptions within the file itself. You may also find more help at [http://www.php.net/docs.php](http://www.php.net/docs.php).

**Note**: The **Advanced** tab will load your cPanel. **Legacy** accounts will feature a **horizontal navigation** bar at the top of the screen, while **Bluerock** account users will see a **vertical navigation** menu on the left-hand side of the screen. To learn more, please see [Bluerock vs. Legacy](https://www.bluehost.com/help/article/rock-vs-legacy).

## Add PHP handlers

You can customize the version of PHP that runs PHP files by directly editing the .htaccess file. Once the .htaccess file has been created or located:

1.  Right-click on the .htaccess file and select **code edit**.
2.  You may get a popup asking about encoding. If so, click the edit button.
3.  At the top of the file, insert the PHP handler for the version you would like to use. If there is a handler in the file already, it should be removed or replaced with the new handler.

**Below are the available PHP handlers:**

-   **PHP 5.4**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php54” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php54___lsphp .php .php5 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

-   **PHP 5.5**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php55” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php55___lsphp .php .php5 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

-   **PHP 5.6**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php56” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php56___lsphp .php .php5 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    ```
    

-   **PHP 7.0**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php70” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php70___lsphp .php .php7 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

-   **PHP 7.1**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php71” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php71___lsphp .php .php7 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

-   **PHP 7.2**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php72” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php72___lsphp .php .php7 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

-   **PHP 7.3**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php73” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php73___lsphp .php .php7 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

-   **PHP 7.4**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php74” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php74___lsphp .php .php7 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

-   **PHP 8.0**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php80” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php80___lsphp .php .php8 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

-   **PHP 8.1**
    
    ```
    php – BEGIN cPanel-generated handler, do not edit
    Set the “ea-php81” package as the default “PHP” programming language.
    <IfModule mime_module>
    AddHandler application/x-httpd-ea-php81___lsphp .php .php8 .phtml
    </IfModule>
    php – END cPanel-generated handler, do not edit
    
    ```
    

4.  Once you have added one of those codes, click Save. The account will then use the PHP version you selected.

## CGI Type

Below are options to consider when selecting the PHP type.

### Standard PHP (Default)

By default, all accounts use standard PHP. A PHP script will use the server's master php.ini configuration file with standard PHP selected if the script's directory does not contain a php.ini file. Each hosting account initially has a copy of the php.ini file in the public\_html directory. You may make any changes to this file, and the modification will take precedent over the master file. With standard PHP selected in the cPanel, you will need to copy the modified php.ini file into all subdirectories containing PHP files to use the custom PHP settings.

Different folders can have different php.ini files containing different PHP settings. If you need to use different PHP settings for two different scripts, you can place them in their own folder and with their own php.ini file.

### PHP Single php.ini

To avoid copying the same php.ini file to each and every directory containing PHP files, you may select PHP Single php.ini. This option changes the PHP handler defined in ~/public\_html/.htaccess to indicate that all subfolders use the same php.ini found in public\_html/.

The .htaccess PHP handler is recursive through all subdirectories unless a subdirectory has a .htaccess file defining a PHP handler.

### PHP FastCGI

Using the PHP FastCGI option makes all your PHP applications run through mod\_fcgid instead of mod\_suphp. FastCGI uses only one php.ini file located in the public\_html directory. Please refer to [PHP FastCGI](https://www.bluehost.com/help/article/fastcgi-for-php) for detailed information about PHP FastCGI, including benefits and potential problems.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
