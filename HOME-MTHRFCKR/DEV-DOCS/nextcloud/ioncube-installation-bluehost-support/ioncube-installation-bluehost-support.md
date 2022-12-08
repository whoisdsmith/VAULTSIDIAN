---
created: 2022-08-05T09:11:44 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/ioncube-installation
author: 
---

# IonCube Installation | Bluehost Support

---
## Summary

**IonCube** is an encryption/decryption tool for PHP applications; data can be secured through it. It also restricts unauthorized PHP applications and can assist in optimizing your website's pages. IonCube loaders are used for decoding encoded files while running on a web server. To learn more about this, please visit their [official site](https://www.ioncube.com/).

___

Our servers are IonCube compatible. If you need IonCube to use a script on your website, you need to install it for your **Apache/PHP installation**. If you need IonCube to access scripts from within the /cpanel, /whm, or /webmail interface, you need to install it for **cPanel/WHM/Webmail installation**. There are different methods for each, and the instructions for doing both are discussed in the sections below:

-   [Installing IonCube for cPanel/WHM/Webmail](https://www.bluehost.com/help/article/ioncube-installation#cpanel-whm-webmail)
    -   [Installing via the WHM](https://www.bluehost.com/help/article/ioncube-installation#whm-install)
    -   [Installing via the CLI](https://www.bluehost.com/help/article/ioncube-installation#cli-install)
-   [Installing IonCube Loader for Apache/PHP](https://www.bluehost.com/help/article/ioncube-installation#apache-php)
    -   [Installing IonCube using the CLI version of PHPExtensionManager](https://www.bluehost.com/help/article/ioncube-installation#extension-manager)
    -   [Installing IonCube using the WHM](https://www.bluehost.com/help/article/ioncube-installation#install-whm)
    -   [Installing IonCube using the CLI version of EasyApache](https://www.bluehost.com/help/article/ioncube-installation#install-easy-apache)

___

## Installing IonCube for cPanel/WHM/Webmail

### Installing via the WHM

Initially, you need to enable the IonCube loader for plugins that use cPanel's version of PHP, like Softaculous. And to do this GUI method of installation, you must have administrative privileges, namely, the root password.

**Note:** This section only covers how to enable IonCube in cPanel's internal version of PHP. If you want to activate IonCube for your public website, you need to use Easy Apache 4 in WHM. Instructions on these can be found in the next section.

1.  Log into WHM.
2.  Using the search bar on the left, look for the **Server Configuration** section and click **Tweak Settings** from the list.  
    ![[whm-new-ioncube-tweak.png]]
3.  Navigate to the **PHP tab** or use the find box and type **loader**.  
    ![[whm-new-ioncube-tweak-settings.png]]
4.  Click the check box next to **Ioncube** and hit on the **Save** button.  
    ![[whm-new-select-ioncube-tweak-settings.png]]

### Installing via the CLI

To complete this task, you must have shell access to the server as the user root (ex: ssh client like Putty)

1.  Log in to the shell as the user root.
2.  Edit **/etc/cpanel/cpanel.config** and find the line that starts with **phploader=**. If there is no value after the equal sign, you can append Ioncube to it (ex: **phploader=ioncube**). If there is another loader already in place, you can add your new loader by adding a comma first and then adding your loader (ex: **phploader=someloader,ioncube**)
3.  Next, execute the following command:
    
    ```
     /usr/local/cpanel/whostmgr/bin/whostmgr2 –updatetweaksettings
    ```
    
4.  And then **/usr/local/cpanel/bin/checkphpini**
5.  And finally **/usr/local/cpanel/bin/install\_php\_inis**

##   
Installing IonCube Loader for Apache/PHP

### Installing IonCube using the CLI version of PHPExtensionManager

This is the most preferred method of many, all it does is install the loaders and does not require you to rebuild Apache and PHP. Thus, making it the fastest method. To use this method, you need to have shell access to the server as the user root via either the console or SSH.

1.  Log in to the console as root.
2.  Run this command:
    
    ```
     /scripts/phpextensionmgr install IonCubeLoader
    ```
    

After installing ionCube Loader, You can verify it by the Linux command line using the command below: 

```
php -v
```

Or we can also create a small PHP script (**info.php**) in your web server document root using the following content and access the webpage.

```
<?php
    phpinfo();
?>
```

Now access created PHP script in a web browser, and you will find that the ionCube loader is enabled in your PHP install.

### Installing IonCube using the WHM

**Note:** This method uses the GUI version of EasyApache to install the Ioncube loader; if you do not want to rebuild Apache and PHP, then don't use this method.

1.  Log in to the WHM as the user root.
2.  On the left-hand side, scroll down and click the **EasyApache** link
3.  Under **Profile**, select **Previous Saved Config** and click the **Start customizing based on profile** button.
4.  Under **Apache Version,** click **Next Step**
5.  Under **PHP Version,** click **Next Step**
6.  Under **Short Options List,** check the **Ioncube Loader for PHP** option and click the **Save and Build** button.
7.  This process will take a while to complete, roughly 10-30 minutes depending on your hardware.

### Installing IonCube using the CLI version of EasyApache

This method requires shell access as the user root via either the console or SSH.

1.  Log in to the console as root.
2.  Run this command:
    
    ```
    /scripts/easyapache
    ```
    
3.  Select **Previously Saved Config** and then select **Start customizing based on profile**
4.  Under **Apache Version,** choose **Next Step**
5.  Under **PHP Version,** select **Next Step**
6.  Under **Short Option Lists,** check the **IonCube Loader for PHP** and then select **Save and Build**
7.  This process will take a while to complete, roughly 10-30 minutes depending on your hardware.

**Important**: For these changes to apply to any site or files hosted outside of your public\_html directory, you will need to change your PHP settings to use Single php.ini or FastCGI. For instructions on doing this, please see our article, [PHP Config](https://www.bluehost.com/help/article/php-config).

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
