---
created: 2022-08-05T11:27:15 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/the-cpanel-interface/server-information-for-cpanel/
author: 
---

# Server Information for cPanel | cPanel & WHM Documentation

---
## Server Information for cPanel

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/the-cpanel-interface/server-information-for-cpanel/)

___

Last modified: _July 11, 2022_

## Overview

The _Server Information_ interface displays information about your account and the server that hosts your account. You can use this interface to determine your server’s version of cPanel & WHM or specifics about Apache or PHP on your account.

## Server Information

The _Server Information_ table displays the following information:

-   _Hosting Package_ — The hosting package for your account. The hosting package that your account uses determines the limitations of your account (for example, your email account quota or your monthly bandwidth quota). To change your hosting package, contact your hosting provider.
-   _Server Name_ — The name for the server that hosts your account.
-   _cPanel Version_ — The version of cPanel & WHM that runs on your account’s server. For more information, read our [Product Versions and the Release Process](https://docs.cpanel.net/knowledge-base/cpanel-product/product-versions-and-the-release-process) documentation.
-   _Apache Version_ — Your account’s version of Apache. For more information about Apache on cPanel & WHM servers, read our [Introduction to Apache](https://docs.cpanel.net/ea4/apache/introduction-to-apache) documentation.
-   _PHP Version_ — Your account’s default version of PHP. You can configure PHP for your domains in cPanel’s [_MultiPHP Manager_](https://docs.cpanel.net/cpanel/software/multiphp-manager-for-cpanel/) interface (_cPanel >> Home >> Software >> MultiPHP Manager_).
-   _MySQL Version_ — The server’s version of MySQL® or MariaDB database software.
-   _PostgreSQL Version_ — The server’s version of the PostgreSQL® database software.
-   _Architecture_ — The processor architecture for the server that hosts your account.
-   _Operating System_ — The operating system type for the server that hosts your account.
-   _Shared IP Address_ — Your account’s shared IP address. This IP Address will be a public-facing IP address.
-   _Dedicated IP Address_ — Your account’s dedicated IP address, if one exists. This IP Address will be a public-facing IP address.
-   _Local IP Address_ — This is an internal IP Address for the server.
-   _Path to Sendmail_ — The absolute filepath to the Perl installation for the server that hosts your account.
-   _Path to Perl_ — The Perl version for the server that hosts your account.
    
    Note:
    
    cPanel & WHM servers include multiple Perl installations. For more information, read our [Guide to Perl](https://api.docs.cpanel.net/guides/guide-to-perl/) documentation
    
-   _Perl Version_ — The Perl version for the server that hosts your account.
-   _Kernel Version_ — The kernel version for the server that hosts your account

## Service Information

The _Service Information_ table displays the following status information for each of your server’s services:

-   _Service_ — The service name.
-   _Details_ — Information about the service’s current status on the server.
    -   Some services display up if the service is currently operational, and down if the service has encountered problems.
    -   Other services display a number, to indicate the current load, or a percentage, to indicate the current percentage of memory that the item uses.
-   _Status_ — An icon that indicates the service’s current status. A green check icon (
    
    ![[Server Information for cPanel  cPanel & WHM Documentation/green-check-mark-status.png]]
    
    ) indicates that the service is operational. Other icons may indicate a problem with the service.
