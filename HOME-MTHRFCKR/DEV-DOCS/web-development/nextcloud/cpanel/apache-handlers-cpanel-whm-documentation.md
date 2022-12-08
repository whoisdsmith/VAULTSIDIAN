---
created: 2022-08-05T11:30:05 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/advanced/apache-handlers/
author: 
---

# Apache Handlers | cPanel & WHM Documentation

---
## Apache Handlers

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/advanced/apache-handlers/)

___

Last modified: _July 6, 2022_

## Overview

Apache handlers control how your site’s Apache web server software manages certain file types and file extensions. Apache can handle CGI scripts and server-parsed files. The file extensions for these files include `.cgi`, `.pl`, `.plx`, `.ppl`, `.perl`, and `.shtml`.

You can configure Apache to use an existing handler to handle a new file type. To do this, manually add the handler and extension in this interface.

## Create an Apache Handler

To add an Apache handler, perform the following steps:

1.  Enter the handler name in the _Handler_ text box. cPanel includes the following built-in handlers:
    
    -   `default-handler` — Sends the file and uses Apache’s default handler for static content.
    -   `send-as-is` — Sends the file with HTTP headers intact.
    -   `cgi-script` — Handles the file as a CGI script.
    -   `imap-file` — Parses the file as an `imagemap` rule file.
        
        -   For more information, read [Apache’s documentation](http://httpd.apache.org/docs/2.2/mod/mod_imagemap.html).
    -   `server-info` — Retrieves the server’s configuration information.
        
    -   `server-parsed` — Parses the file for server-side includes.
        
    -   `server-status` — Retrieves the server’s status report.
        
    -   `type-map` — Parses the file as a type map file.
        
        -   For more information, read [Apache’s documentation](http://httpd.apache.org/docs/2.2/mod/mod_negotiation.html).
2.  Enter the file extension in the _Extension(s)_ text box.
    
    -   A file extension consists of the letters after the dot (`.`) in a file name (for example, `filename.fileextension`).
    -   Space-separate multiple extensions (for example, `.cgi` `.pl` `.ppl`).
3.  Click _Add_.
    

Note:

This interface does **not** allow you to create custom Apache handlers.

## Remove an Apache Handler

To remove a user-defined handler, perform the following steps:

1.  Click _Delete_ under the _Remove_ heading for the appropriate handler in the _User Defined Apache Handlers_ table.
2.  Click _Yes_.

Note:

You **cannot** remove the file extensions that Apache automatically handles.
