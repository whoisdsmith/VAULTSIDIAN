---
created: 2022-08-05T09:11:19 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/multiphp-ini-editor
author: 
---

# MultiPHP INI Editor | Bluehost Support

---
Bluehost cPanel’s MultiPHP INI Editor allows you to make configuration changes to your PHP settings. This is along with MultiPHP Manager, which gives you a way to change the PHP version of your sites.

This article will provide you information on how to edit php.ini using two modes, such as basic and editor.

___

-   [Editing the PHP.INI](https://www.bluehost.com/help/article/multiphp-ini-editor#editing-php-ini)
-   [Basic Modes](https://www.bluehost.com/help/article/multiphp-ini-editor#basic)
-   [Editor Mode](https://www.bluehost.com/help/article/multiphp-ini-editor#editor)

___

## Editing the PHP.INI

Before making the changes, you need to be aware of backward compatibility issues with scripts: Older PHP coding may not be compatible with newer PHP versions. Avoid skipping versions, and instead, make updates gradually. Take note since this is a global change and will affect how the specified PHP version operates for the server.

### Basic Modes

It allows you to make changes to some common types of PHP configuration.

1.  Log in to your [Bluehost control panel](https://my.bluehost.com/).
2.  Click on the **Advanced** tab from the side navigation menu to the left.
3.  Under the **Software** section, select the **MultiPHP INI Editor**.  
    ![[Blue Host/Knowledge Base/MultiPHP INI Editor  Bluehost Support/rock-phpini-bh.png]]
4.  From the drop-down, select the home directory or a domain’s document root to open the corresponding PHP configuration.  
    ![[Blue Host/Knowledge Base/MultiPHP INI Editor  Bluehost Support/multi-php-ini-editor-settings.png]]
5.  Under the **Basic Mode**, there is an option to edit the most commonly changed variables:
    -   max\_execution\_time
    -   max\_input\_vars
    -   memory\_limit
    -   upload\_max\_filesize  
        ![[multi-php-ini-editor-settings-php-derective1.png]]
6.  Once the changes have been made, select the **Apply** button.

### Editor Mode

It makes your life easier by adding custom PHP configuration changes. It allows you as well to change PHP variables that are not shown in the Basic Mode.

**Important Note**: You must be extremely cautious when you make changes to it. Errors could have resulted in a non-functional PHP script. Only advanced users should use this section.

1.  Log in to your [Bluehost control panel](https://my.bluehost.com/).
2.  Click on the **Advanced** tab from the side navigation menu to the left.
3.  Under the **Software** section, select the **MultiPHP INI Editor**.  
    ![[Blue Host/Knowledge Base/MultiPHP INI Editor  Bluehost Support/rock-phpini-bh.png]]
4.  Under the **Editor Mode**, there is a drop-down; select the home directory or a domain’s document root to open the corresponding PHP configuration.  
    ![[multi-php-ini-editor-settings-editor-mode.png]]
5.  In the Search text field, type the PHP setting you are looking to update.
    
    PHP has been configured to use the following settings on our shared and reseller servers:
    
    ```
    php_flag display_errors Off (cannot adjust)
    php_flag memory_execution_time 30 (MAXIMUM in seconds)
    php_flag max_input_time 60 (MAXIMUM in seconds)
    php_flag max_input_vars 1000 (MAXIMUM in seconds)
    php_flag memory_limit 256M (MAXIMUM amount of memory a script may consume)
    php_flag post_max_size 260M (MAXIMUM) 
    php_flag session.gc_maxlifetime 1440 (MAXIMUM) 
    php_flag session.save_path "/var/cpanel/php/sessions/ea-php70" (MAXIMUM) 
    php_flag upload_max_filesize 256M (MAXIMUM) 
    php_flag zlib.output_compression off (cannot adjust)
    ```
    
    ![[multi-php-ini-editor-settings-editor-mode-code.png]]
6.  Once the change has been made, select the **Save** button.

**Pro Tip**: To verify that the changes take effect, please look at the phpinfo page. To access it, follow this link format https://example.com/phpinfo.php.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
