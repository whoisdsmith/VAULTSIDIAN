---
created: 2022-08-05T11:28:31 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/metrics/bandwidth/
author: 
---

# Bandwidth | cPanel & WHM Documentation

---
## Bandwidth

_Valid for versions 84 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/metrics/bandwidth/82/)

#### [84](https://docs.cpanel.net/cpanel/metrics/bandwidth/)

___

Last modified: _May 13, 2020_

Important:

This feature only appears if your hosting provider’s [server profile](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary) enables it.

## Overview

The _Bandwidth_ interface displays bandwidth usage information in several sets of graphs. Each graph contains information about bandwidth usage over a specific period of time.

The graphs display bandwidth information in six categories:

-   _HTTP_ — Web traffic.
-   _POP3_ — Email that you retrieved from your accounts on the server.
-   _IMAP_ — Email that you retrieved from your accounts on the server.
-   _FTP_ — File transfers.
-   _SMTP_ — Email that your accounts sent.
-   _Total (all services)_

Note:

-   The _Total (all services)_ category provides the combined total of all of the other categories.
-   The system **only** records bandwidth for SMTP (sent) messages. The system does **not** include POP3 or IMAP (received) messages in bandwidth calculation.

This information allows you to monitor the heaviest traffic times for your website, and helps you to decide whether to purchase additional bandwidth.

## Time zone

The interface displays the server’s time zone setting as follows:

```perl
All times are in the "America/Chicago" time zone
```

If the system detects that your browser’s time zone does not match the server’s time zone, the interface will contain a notice that resembles the following:

```perl
Set the time to "America/Chicago" time zone and reload.
```

Click the link to reset the time zone and reload the interface.

## Past 24 hours

The _Past 24_ hours graph displays the data transfer rate in bits per second for the current day, averaged into five minute intervals.

![[Bandwidth  cPanel & WHM Documentation/bandwidth24hours.png]]

By default, this graph updates every two hours. However, if your hosting provider adjusts the bandwidth data process interval in WHM’s [_Statistics Software Configuration_](https://docs.cpanel.net/whm/server-configuration/statistics-software-configuration) interface (_WHM >> Home >> Server Configuration >> Statistics Software Configuration_), this affects the amount of bandwidth data that the system displays.

Use this graph to view the following information:

-   Small-scale trends (for example, quick spikes in traffic at specific times).
-   Changes over the course of the day (for example, increases and decreases in traffic).

## Past week

The _Past week_ graph displays the data transfer rate, in bits per second, over the past seven days, averaged into five-minute intervals.

![[Bandwidth  cPanel & WHM Documentation/bandwidthpastweek.png]]

A sample Past week graph.

Use this graph to view the following information:

-   Larger-scale trends (for example, spikes in traffic at the same time each day for the past three days).
-   Changes from the past week (for example, increases or decreases in traffic over a period of two to seven days).

## Past year

The _Past year_ graph displays the total amount of data that the system transferred over a period of 12 months (one year).

![[Bandwidth  cPanel & WHM Documentation/bandwidthpastyear.png]]

Use this graph to find long-term trends over an entire year. For example, this graph might indicate that your account receives a heavy burst of traffic at mid-month every month.

## Monthly pie charts

The monthly pie charts display the relative amounts of data that your cPanel account’s various services and domains use in each month.

![[Bandwidth  cPanel & WHM Documentation/bandwidthpiecharts.png]]

A sample pie chart

Use the pie charts to view the following information:

-   The total amount of data that the system transferred for the month.
-   Changes in the relationships between services from month to month. For example, SMTP total bandwidth increased from 5% to 50% in one month, while HTTP bandwidth decreased.
-   Changes in the bandwidth usage of one domain relative to another domain. For example, the domain `example1.com` accounts for 50% of the overall traffic of all sites, and `example2.com` accounts for about 25%.

To view the _Bandwidth Transfer Detail_ interface for a month, click that month’s pie chart.

Note:

Click a _usage_ link for a month to look up the usage information for an individual website or service. A new interface will display detailed monthly traffic information for that particular service or website.

## The Bandwidth Transfer Detail interface

To view the bandwidth transfer information for a particular month, click _Total (all services)_ for that month.

This interface contains a series of bandwidth usage graphs for the following types of traffic:

-   HTTP
-   SMTP
-   FTP
-   POP3
-   IMAP

### All Traffic (monthly)

The _All Traffic_ monthly graph displays the hourly average bytes that the system transferred for the month. It provides a detailed version of the data that the _Past year_ graph displays.

![[Bandwidth  cPanel & WHM Documentation/bandwidthalltrafficmonthly.png]]

Use this graph to find trends over a period of several days or weeks. For example, this graph might indicate that your account receives heavier traffic on a specific day of the month.

### Monthly traffic graphs for services

The monthly traffic graphs serve the same purpose as the _All Traffic_ graph, but the system separates the data for individual services.

### All Traffic (daily)

The _All Traffic_ daily graph displays 30-minute averages of bits that the system transferred per second. It is a more detailed version of the _All Traffic_ monthly graph.

### Daily traffic graphs by service

Under the _All Traffic_ graph is a series of one or more bar graphs for specific services. These serve the same purpose as the _All Traffic_ graph, but the system separates the data for individual services.

### Bandwidth By Day

The _Bandwidth by Day_ table lists the total amount of the cPanel account’s data that the system transferred on a specific day of the month, in megabytes (MB).

Click a day in the table to view more information about that day’s traffic.

![[Bandwidth  cPanel & WHM Documentation/bandwidthbyday.png]]

Note:

We recommend that you view the _Bandwidth by Day_ table at least 24-48 hours **after** the last day of the period for which you wish to obtain data. This allows the system to gather and process the traffic data.

## Non-recorded bandwidth information

The _Bandwidth_ displays information about your website, rather than about your cPanel & WHM server. As a result, the system does **not** count the following processes towards your bandwidth usage or allotment:

-   Protocols such as file manager uploads and downloads.
-   Incoming mail that other servers deliver.
-   POP/IMAP bytes received for tasks such as polling for new email.
-   SMTP (received) mail.
-   DNS activity.
-   Any user processes spawned by cron jobs that perform network activity.

You systems administrator can monitor your cPanel & WHM server’s bandwidth via the _Munin_ plugin, which they can download in WHM’s [_Manage Plugins_](https://docs.cpanel.net/whm/cpanel/manage-plugins) interface (_WHM >> Home >> cPanel >> Manage Plugins_).
