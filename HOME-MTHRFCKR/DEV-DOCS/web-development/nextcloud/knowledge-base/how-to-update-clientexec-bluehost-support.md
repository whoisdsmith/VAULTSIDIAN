---
created: 2022-08-05T09:10:23 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/clientexec-update
author: 
---

# How to Update ClientExec | Bluehost Support

---
## Summary

This article will show you how to update your version of ClientExec to the latest. This article does not provide instructions for an incremental update, but a full update.

___

-   [Backup your MySQL Database](https://www.bluehost.com/help/article/clientexec-update#backup-mysql)
-   [Prepare to update ClientExec](https://www.bluehost.com/help/article/clientexec-update#prepare)
-   [Update ClientExec](https://www.bluehost.com/help/article/clientexec-update#update-clientexec)

___

### Backup your MySQL Database

1.  Login to your [cPanel Account](https://my.bluehost.com/cgi-bin/cplogin)
2.  Scroll down to the **Databases** section.
3.  Click the **phpMyAdmin** icon.
4.  Choose your ClientExec database from the left-hand side (Should be labeled something like \_cxdb1)
5.  Click the **Export** tab.
6.  Click the **Go** button to create a backup of your database.

### Prepare to update ClientExec

1.  You will need to download the latest version of ClientExec from the [ClientExec download page](https://www.clientexec.com/download.php).   
    Note: Please choose the ionCube encoded copy
2.  Once downloaded unzip the file.
3.  It is recommended that you remove all but the config.php **file** and **upload** directory from the server.
4.  Upload all but the **config.php** and **uploads** directory to the server

### Update ClientExec

1.  To start the update process you will need to enter the URL of your ClientExec installation and append /install.php to the URL. (e.g. http://example.com/members/install.php)
    
    **Note**: It is possible that you will need to update your version of PHP, if so please see [PHP Version Selection (PHP Config)](https://www.bluehost.com/help/article/php-version-selection)
    
2.  Log in using your ClientExec E-mail/Username and Password
3.  Agree to the End-user license agreement
4.  Choose to continue
5.  Check the box stating that you have created a backup of your database and click **Continue**

Your installation of ClientExec should now be updated. If you have additional questions or troubleshooting it is recommended that you refer to [the official upgrade instructions](https://www.clientexec.com/members/index.php?fuse=knowledgebase&view=KB_viewArticle&articleId=281) provided by ClientExec.
