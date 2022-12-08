---
created: 2022-08-05T11:30:27 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/advanced/indexes/
author: 
---

# Indexes | cPanel & WHM Documentation

---
## ndexes

_Valid for versions 88 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/advanced/indexes/82/)

#### [88](https://docs.cpanel.net/cpanel/advanced/indexes/)

___

Last modified: _May 13, 2020_

## Overview

When a visitor accesses a directory rather than a page on your web site, the browser typically displays the directory’s index page. If no index page exists, the browser displays a list of the files in that directory. Use the _Indexes_ interface to define how the server displays a specific directory’s index to a visitor, or to disable the index display for a directory.

## Configure directory settings

To configure your directory settings, perform the following steps:

1.  Click _Settings_ and then select one of the following locations in which to begin navigation:
    
    -   _Home_ — Begin navigation in the home directory for the domain.
        
    -   _Web Root_ — Begin navigation in the document root for the account’s primary domain.
        
    -   _Document Root for_ — Select the domain that corresponds to the document root in which you wish to begin navigation.
        
2.  To configure the interface to always open your selection from Step 1, select the _Always open this directory in the future_ checkbox.
    
3.  Click _Save Changes_.
    

## Manage index settings

To manage a directory’s index settings, perform the following steps:

1.  Navigate to the desired folder with the following:
    
    -   To navigate a directory, click the folder icon (![[Indexes  cPanel & WHM Documentation/indexesfolder.png]]) or the directory’s name.
        
    -   To navigate up one level of the directory tree, click _Up One Level_ at the top of the list of directory contents.
        
    -   To to navigate the home directory, click _Home_ above the list of directories.
        
    -   To view and select subdirectories, click the parent directory’s name. Then, click the desired subdirectory name.
        
2.  To configure the security settings for a directory or subdirectory, click _Edit_ under the _Actions_ column. A new interface will appear.
    
3.  Select one of the following options:
    
    -   _Inherit_ — The directory inherits the parent directory’s index setting. If the parent directory does not possess index settings, the directory uses the system default settings.
        
    -   _No Indexing_ — The server does not list the contents of the directory. Browsers display a message that states that the contents are forbidden.
        
    -   _Show Filename Only_ — The server lists the directory’s contents as filenames only.
        
    -   _Show Filename and Description_ — The server lists file names and additional information, such as file size and file type.
        
4.  Click _Save_. The new index setting will appear in the _Indexes_ interface under the _Index Type_ column.
