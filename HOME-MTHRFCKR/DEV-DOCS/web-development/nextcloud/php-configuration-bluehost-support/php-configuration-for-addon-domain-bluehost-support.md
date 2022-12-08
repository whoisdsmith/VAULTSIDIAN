---
created: 2022-08-05T09:11:29 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/php-configuration-for-addon-domain
author: 
---

# PHP Configuration for Addon Domain | Bluehost Support

---
## Overview

To use specific PHP settings only for a particular addon domain you will need to place a php.ini file in the addon domain's folder.

## Configure PHP for an Addon Domain

If you need to generate a new php.ini file, this can be done in the cPanel by clicking on the icon "PHP Config", choose your version of PHP and then click **Save**. This will copy the server's master php.ini to your public\_html directory as "php.ini.default". This file must then be moved to the addon's folder and renamed to php.ini.

If you are using the 'single php.ini' option in the cPanel's **PHP Config** section, you will need to create a .htaccess file in the addon's folder. In the addon's .htaccess file it needs to contain a regular PHP handler:

```
AddHandler application/x-httpd-php7 .php
```

To verify your addon domain is using the php.ini file you have set up, you can create a new file in the addon's folder called info.php containing the following PHP code:

```
<?php
phpinfo();
?>
```

Viewing the info.php file in a web browser should show you all the PHP settings from the addon's php.ini including the "Loaded Configuration File". This is the path to the php.ini file being used.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
