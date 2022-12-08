---
created: 2022-08-05T11:29:27 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/metrics/visitors/
author: 
---

# Visitors | cPanel & WHM Documentation

---
## Visitors

_Valid for versions 102 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/metrics/visitors/82/)

#### [102](https://docs.cpanel.net/cpanel/metrics/visitors/)

___

Last modified: _December 7, 2021_

## Overview

This interface displays detailed information about recent visits to your website. This information helps you to learn about your audience and monitor frequent visitors so that you can adjust your website content to fit their needs. It also helps you locate and fix errors, such as missing pages or broken links.

If your server runs [Apache®](https://docs.cpanel.net/ea4/apache/introduction-to-apache/), this interface displays entries from the following files, where `domainname` represents the domain:

-   SSL — `/var/log/apache2/domlogs/`
-   Non-SSL— `/usr/local/apache/domlogs/domainname`

If your server runs [NGINX®](https://docs.cpanel.net/knowledge-base/web-services/nginx-with-reverse-proxy), this interface displays entries from one of the following files, where `domainname` represents the domain:

-   Piped logging is enabled —The interface displays entries from one of the following files, depending on whether SSL is enabled or not:
    -   SSL — `/var/log/nginx/domains/domainname-ssl_log`
    -   Non-SSL — `/var/log/nginx/domains/domainname`
-   Piped logging is **not** enabled — `/var/log/nginx/domains/domainname`

Logs for Apache will **not** appear when NGINX is enabled, and vice versa. For more information, read our [NGINX with Reverse Proxy](https://docs.cpanel.net/knowledge-base/web-services/nginx-with-reverse-proxy/#log-files) documentation.

Note:

If your hosting provider rotates the log file, the interface will display fewer entries.

## View latest visitor details

To view your latest visitor details, click the magnifying glass icon (![[Visitors  cPanel & WHM Documentation/glass-icon.jpg]]) for that domain.

By default, the interface displays the following information:

-   _IP_ — The visitors’ IP address.
    
-   _URL_ — The specific URL that the visitor accessed.
    
-   _Time_ — The time when the visitor accessed your website.
    
-   _Size (bytes)_ — The amount of data that the server sent to the visitor for this resource.
    
-   _Referring URL_ — The web address from which the visitor navigated to the resource.
    
-   _User Agent_ — The browser that the visitor used to access your website.
    

## Additional data

Click the gear icon (![[Visitors  cPanel & WHM Documentation/gear.png]]) to choose to display the following additional data:

-   _Status_ — The [HTTP code](https://docs.cpanel.net/knowledge-base/web-services/http-error-codes-and-quick-fixes/) indicates whether the resource loaded successfully or resulted in an error.
    
-   _Method_ — The request-response between the client and server (for example, GET or POST).
    
-   _Protocol_ — The version of HTTP that the server used to serve the resource to the visitor (for example, 1.1).
    

To search for additional records, enter your search criteria in the _Search_ text box.
