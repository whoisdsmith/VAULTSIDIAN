---
created: 2022-08-05T11:29:19 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/metrics/webalizer/
author: 
---

# Webalizer | cPanel & WHM Documentation

---
## Webalizer

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/metrics/webalizer/)

___

Last modified: _July 8, 2022_

## Overview

The _Webalizer_ interface displays traffic statistics from the Webalizer statistics program.

-   For more information about Webalizer, visit the [Webalizer website](http://www.webalizer.org/).
-   To view all of the possible configuration options for Webalizer, read Webalizer’s [Configuration Files](http://www.webalizer.org/webalizer.1.html) documentation.

Important:

This interface **only** appears in your cPanel account if your hosting provider selects the _Webalizer_ feature in WHM’s [_Feature Manager_](https://docs.cpanel.net/whm/packages/feature-manager) interface (_WHM >> Home >> Packages >> Feature Manager_).

## View your Webalizer statistics

To view Webalizer statistics, click _View_ for the domain that you wish to view. A new interface will appear and display a graph and a summary of the Webalizer traffic statistics for that domain.

To view detailed monthly statistics, click that month’s link. A new interface will appear and display charts and tables with the following information:

-   Daily and hourly statistics in graphs and tables.
-   The links through which visitors access your website.
-   HTTP codes.
-   Operating systems.
-   Browser information.
-   Countries of origin.

Note:

Your hosting provider may allow you to view Webalizer statistics without the need to log in to cPanel.

-   To do this, navigate to `http://example.com/stats`, where `example.com` represents your domain name, and log in with your unique Webalizer directory username and password.
-   To use this functionality, your hosting provider **must** create the `/home/username/public_html/webalizer/stats` directory, where username represents your cPanel username. Then, they **must** create a unique username and password for this directory.
