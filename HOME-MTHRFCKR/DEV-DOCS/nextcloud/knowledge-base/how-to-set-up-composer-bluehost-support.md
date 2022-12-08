---
created: 2022-08-05T11:13:39 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/bh-how-to-set-up-composer
author: 
---

# How to Set Up Composer | Bluehost Support

---
The information about Composer below is provided by Bluehost as a courtesy. Please keep in mind that this is not something our Support agents can further assist you with. If you require assistance or have further questions, we suggest looking into Composer instructional guides or forums available online.

___

-   [What is Composer?](https://www.bluehost.com/help/article/bh-how-to-set-up-composer#composer)
-   [Setting up Composer](https://www.bluehost.com/help/article/bh-how-to-set-up-composer#setup)
    1.  [Enable your SSH Access](https://www.bluehost.com/help/article/bh-how-to-set-up-composer#enable-ssh)
    2.  [Run the PHP version required by your application](https://www.bluehost.com/help/article/bh-how-to-set-up-composer#run-php)
    3.  [(Optional) Run any additional INI settings required by your application](https://www.bluehost.com/help/article/bh-how-to-set-up-composer#run-addons)
    4.  [Run your "composer" command together with the "argument"](https://www.bluehost.com/help/article/bh-how-to-set-up-composer#run-composer)
    5.  [Run the module or extension you want to install](https://www.bluehost.com/help/article/bh-how-to-set-up-composer#run-mod-ext)

___

### What is Composer?

Composer is a PHP package manager used to install specific modules or extensions within a specific directory, which may be required if these modules or extensions are not present in the global PHP installation on a server. By default, Composer is installed in our Shared, VPS, and Dedicated hosting servers. 

-   Online documentation about Composer is available. Here is one of them: [https://getcomposer.org/doc/](https://getcomposer.org/doc/)
-   You can also view available PHP packages here: [https://packagist.org/](https://packagist.org/)

As a precaution, we suggest generating a backup of your website first before making any changes or running any commands that may directly affect your website or application. Bluehost offers [**CodeGuard**](https://www.bluehost.com/help/article/codeguard), a security professional that provides full protection and daily monitoring of your website or application.

### Setting up Composer

Composer is typically used by advanced users who are familiar with the particulars of Composer and are comfortable running commands in SSH. As always, it is best to generate a backup of your website before making any changes or running any commands as Bluehost is not responsible for the aftereffects these commands may cause on your website.

Here are the general guidelines you can use in setting up Composer:

1.  **Enable your SSH Access**  
    Make sure your jail shell access (SSH) is enabled.
    -   For Shared hosting, please check out the article, [How to enable SSH/Shell from cPanel](https://www.bluehost.com/help/article/ssh-access#enable), for details.
    -   To enable SSH access for individual cPanels in your VPS/Dedicated hosting, please refer to the instructions in the article: [VPS and Dedicated Servers SSH Access](https://www.bluehost.com/help/article/ssh-access#vps).

 

2.  **Run the PHP version required by your application**  
    **Example:**
    
    ```
    /opt/cpanel/ea-php74/root/usr/bin/php
    ```
    
    In the sample command line above, the PHP version executed is 7.4 (_ea-php74_). Depending on the needs of your application, specify the **PHP version** in your command line together with the **full path to the php binary**. The recommended method is to _**cd**_ into the directory where you want to run Composer, then execute the full path to the php binary you want to use.  
    **Example:**
    1.  ```
        cd /home/user/public_html
        ```
        
    2.  ```
        /opt/cpanel/ea-php56/root/usr/bin/php /opt/cpanel/composer/bin/composer diagnose
        ```
        

 

3.  (Optional) **Run any additional INI settings required by your application**  
    **Example:**
    
    ```
    /opt/cpanel/ea-php74/root/usr/bin/php -d memory_limit=512M
    ```
    
    In the sample single command line above, it invokes the memory limit to be set to 512M (_\-d memory\_limit=512M_). Modifying the memory limit is not required but can be modified if the default 256M is not sufficient for your application.

 

4.  **Run your "composer" command together with the "argument"**  
    **Example:**
    
    ```
    /opt/cpanel/composer/bin/composer require spatie/laravel-tags
    ```
    
    In the single command line above, "_composer require"_ is executed. For the list of composer commands and arguments, you may visit the online documentation: [https://getcomposer.org/doc/03-cli.md](https://getcomposer.org/doc/03-cli.md).

 

5.  **Run the module or extension you want to install**  
    **Example:**
    
    ```
    /opt/cpanel/composer/bin/composer require spatie/laravel-tags
    ```
    
    In the single command line above, the package "spatie/laravel-tags" is executed.
    
    Notice that the commands were executed in a single line.
    
    **Example** (entire command in a single command line):
    
    ```
    /opt/cpanel/ea-php74/root/usr/bin/php -d memory_limit=512M  /opt/cpanel/composer/bin/composer require spatie/laravel-tags
    ```
    

 

Keep in mind that the command, arguments, and modules or extensions you will run in SSH will depend on the requirements of your application, which our Support team is unable to walk you through. Bluehost cannot guarantee how these will affect your website or application. Please be guided accordingly.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
