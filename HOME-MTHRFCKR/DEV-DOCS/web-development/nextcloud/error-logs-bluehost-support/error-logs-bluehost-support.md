---
created: 2022-08-05T09:10:37 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/error-logs
author: 
---

# Error Logs | Bluehost Support

---
### Overview

The cPanel Error Logs tool is useful when debugging scripts and finding missing files or broken links you may not be aware of. If the error messages you find are related to your website, and you are unsure what they mean or how to fix the issue.

**Note:** This article will cover how to access error logs and what to look for when reviewing them. If you are looking for information on how to manage the error pages, please click [here](https://www.bluehost.com/help/article/error-pages). To enable Debug Mode in WordPress, [check this article.](https://www.bluehost.com/help/article/wp-debug)

___

-   [Error Logs Overview](https://www.bluehost.com/help/article/error-logs#Overview)
-   [Main Error Logs](https://www.bluehost.com/help/article/error-logs#main-log)
-   [PHP Error Logs](https://www.bluehost.com/help/article/error-logs#php-log)

___

## Error Logs Overview

The cPanel Error Logs tool is useful when debugging scripts and finding missing files or broken links you may not be aware of. If the error messages you find are related to your website, and you are unsure what they mean or how to fix the issue, it is advisable to contact the script developer for further troubleshooting. There are 2 different sections of the Error logs page you should be aware of:

 

### Main Error Log

![[rtaImage.png]]

This section shows the last few lines of the server's main error log. These lines are displayed in chronological order with the time, IP address of the visitor, and the error message. Because this is a shared server, you will see errors for all accounts on the server. If you are trying to locate error messages originating from your hosting account, you may need to refresh your URL, which has the error/problem and then refresh the Error Logs page.

### PHP Error Logs

The PHP Error Logs will show errors related to PHP scripts only for your account. These errors are sorted by directory and do not automatically disappear, as do the main error logs. The errors shown are stored in the error\_log file within each directory. If you would like to clear the PHP error\_logs, simply delete the error\_log files in each directory using File Manager or FTP.

**Note**: At the bottom of the Error Logs page, you can limit each section's output to a specific number of lines. There is also a link to the Process Manager cPanel tool.

1.  Access **File Manager**
2.  Look for **error\_log** file, right-click, then hit on **view**.   
    ![[filemanager_errorlog.png]]

### Shared and Reseller

You can log in to cPanel and click the Error Log icon. This contains the last 300 Apache errors triggered by your website.

### VPS and Dedicated Server

On a Dedicated Server or VPS without a cPanel installation, most log files would be located in the **/var/log/** directory. The Apache log would then be located in the **/var/log/httpd/** directory.

However, for all of our servers with cPanel installs, the Apache error log's actual location is **/usr/local/apache/logs/error\_log**, where “error\_log” is simply a plain text file.
