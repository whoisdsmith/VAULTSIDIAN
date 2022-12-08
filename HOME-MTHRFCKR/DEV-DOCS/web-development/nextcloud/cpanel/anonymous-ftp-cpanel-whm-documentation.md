---
created: 2022-08-05T11:26:18 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/files/anonymous-ftp/
author: 
---

# Anonymous FTP | cPanel & WHM Documentation

---
## Anonymous FTP

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/files/anonymous-ftp/)

___

Last modified: _May 5, 2021_

## Overview

This interface lets you define how anonymous users interact with your FTP server. Anonymous FTP users can connect to your FTP server without a password. You can use this feature to make content publicly available for download.

When users log in to FTP anonymously, they must use the `anonymous@example.com` username, where `example.com` represents your domain’s name. This requirement directs the server to the correct `public_ftp` directory.

Note:

-   This interface is only available if your hosting provider enables FTP services **and** anonymous FTP.
-   If an anonymous user does **not** include the domain name, one of the following errors will appear:
    -   If the server uses the Pure-FTP FTP server, users receive a _421 Can’t change directory to /var/ftp/_ error message.
    -   If the server uses the ProFTP FTP server, users receive a _530 Login Authentication Failed_ error message.
-   For information about your FTP accounts, read our [FTP Accounts](https://docs.cpanel.net/cpanel/files/ftp-accounts) documentation.

## Anonymous FTP settings

Warning:

We **strongly** recommend that you do **not** allow anonymous users the ability to upload files to your FTP server. This will prevent malicious software uploads, which can harm your website.

To configure the _Anonymous FTP_ feature’s settings, perform the following steps:

1.  Select or deselect the checkboxes for the permissions that you wish to allow or deny.
2.  Click _Save_.

## Anonymous FTP Welcome Message

You can set a message that anonymous FTP users see when they connect to your FTP server.

To set a message, perform the following steps:

1.  Enter your message in the _Anonymous FTP Welcome Message_ text box.
2.  Click _Save_.
