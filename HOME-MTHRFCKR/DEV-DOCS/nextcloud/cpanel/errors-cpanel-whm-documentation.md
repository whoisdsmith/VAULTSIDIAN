---
created: 2022-08-05T11:28:47 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/metrics/errors/
author: 
---

# Errors | cPanel & WHM Documentation

---
## Errors

_Valid for versions 102 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/metrics/errors/82/)

#### [84](https://docs.cpanel.net/cpanel/metrics/errors/84/)

#### [102](https://docs.cpanel.net/cpanel/metrics/errors/)

___

Last modified: _July 8, 2022_

## Overview

The interface displays up to 300 of the most recent entries in your web server’s error logs, in reverse chronological order.

## Error details

The interface includes entries in the the `/var/log/apache2/` file.

Note:

This interface works with [NGINX® with Reverse Proxy](https://docs.cpanel.net/knowledge-base/web-services/nginx-with-reverse-proxy) and [Apache®](https://docs.cpanel.net/ea4/apache/introduction-to-apache/). If you run NGINX on your server, this interface only displays the errors for web traffic from the Apache logs. NGINX and Apache log different types of errors to their error log, and NGINX’s log does **not** log web traffic.

The interface displays error log entries from the user’s domains. The interface also displays entries that include the username for the account from the `/var/log/apache2/suexec_log` file.

-   To view older entries, access the individual log files.
-   The Apache logs record all of the requests that Apache handles. Tasks that other services handle may have separate log locations.

## Additional information

The server handles the configuration of the log files. Contact your system administrator to change the level of information in the log files.

For more information about individual error messages and other configuration options, visit the [Apache documentation](http://httpd.apache.org/docs/2.4/).
