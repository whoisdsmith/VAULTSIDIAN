---
created: 2022-08-05T11:26:28 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/files/directory-privacy/
author: Authorized Users
---

# Directory Privacy | cPanel & WHM Documentation

---
## Directory Privacy

_Valid for versions 88 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/files/directory-privacy/82/)

#### [88](https://docs.cpanel.net/cpanel/files/directory-privacy/)

___

Last modified: _January 18, 2021_

## Overview

This interface allows you to protect specific directories in your cPanel account’s files. After you enable this feature for a directory, when users attempt to view that directory via a website, the system prompts them to log in.

Note:

-   This feature modifies `htaccess` and `htpasswd` configurations in order to restrict access to files on your websites.
    
-   This feature does **not** protect directories that users access via FTP, SFTP, Web Disk, or other services, or when they access files locally.
    

## Select a directory

To use this interface, select a directory to manage.

-   To select a directory, click the desired directory’s name.
    
-   To view and select subdirectories, click the parent directory’s name. Then, click the desired subdirectory name.
    

To configure the security settings for a directory or subdirectory, click _Edit_ under the _Actions_ column.

Note:

-   A protected directory’s subdirectories inherit their parent directory’s password protection.
    
-   The lock icon (![[Directory Privacy  cPanel & WHM Documentation/directoryprivacylock.png]]) indicates that _Directory Privacy_ configurations already exist for that directory.
    

### Security Settings

Important:

You **must** perform these steps and click _Save_ in order to enable this feature.

To password protect the selected directory, perform the following steps:

1.  Select the _Password protect this directory_ checkbox.
    
    Note:
    
    To remove password protection from a directory, deselect the _Password protect this directory_ checkbox. Then, click _Save_.
    
2.  Enter a display label for the directory in the _Enter a name for the protected directory_ text box.
    
    Note:
    
    This name **only** functions as a label for the directory. Do **not** confuse it with the directory’s actual name.
    
3.  Click _Save_. A confirmation message will appear. Click _Go Back_ to return to the directory’s configuration.
    

Important:

After you complete this process, you **must** create a user that can access this directory.

### Create User

Warning:

To create a user for a directory, the directory must have correct directory permissions. If you cannot create a user, change the directory’s permissions to `0700` in cPanel’s [_File Manager_](https://docs.cpanel.net/cpanel/files/file-manager) interface (_cPanel >> Home >> Files >> File Manager_).

To create an authorized user for the selected directory, perform the following steps:

1.  Enter the desired username in the _Username_ text box.
    
2.  Enter and confirm the new password in the appropriate text boxes.
    
    Note:
    
    -   The system evaluates the password that you enter on a scale of 100 points. `0` indicates a weak password, while `100` indicates a very secure password.
        
    -   Some web hosts require a minimum password strength. A green password _Strength_ meter indicates that the password is equal to or greater than the required password strength.
        
    -   Click _Password Generator_ to generate a strong password. For more information, read our [Password & Security](https://docs.cpanel.net/cpanel/preferences/password-and-security) documentation.
        
    
3.  Click _Save_. A confirmation message will appear. Click _Go Back_ to return to the directory’s configuration.
    

Note:

To change an existing user’s password, enter the user’s information and the new desired password. Then, click _Save_.

### Authorized Users

The _Authorized Users_ menu lists the directory’s existing authorized users. To delete a user, select that user and click _Delete User_. A confirmation message will appear. Click _Go Back_ to return to the directory’s configuration.
