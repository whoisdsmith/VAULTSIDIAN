---
created: 2022-08-05T11:26:38 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/files/file-manager/
author: 
---

# File Manager | cPanel & WHM Documentation

---
## File Manager

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/files/file-manager/)

___

Last modified: _August 20, 2021_

## Overview

cPanel organizes all the files in your account into folders. Use the _File Manager_ interface to manage and edit your files.

Note:

-   Whenever you access a folder that contains a Git™ repository, we **strongly** recommend that you do **not** update any files or directories. Changes could cause serious problems with the repository, regardless of whether you created it in the [_Git Version Control_](https://docs.cpanel.net/cpanel/files/git-version-control) interface (_cPanel >> Home >> Files >> Git™ Version Control_).
-   When a toolbar action **isn’t** available, the icon displays in gray.
-   You can **only** use certain _File Manager_ actions with **one** file at a time. Select the desired file **before** you attempt these actions.
-   Any attempt to rename, edit, or view multiple files at the same time will **only** affect the first listed file in the folder.

## Change Settings

To change the folder in which the _File Manager_ interface opens, perform the following steps:

1.  Click _Settings_. The _Preferences_ interface will appear.
    
2.  Select a folder to open by default:
    
    -   _Home Directory_ — The main folder for your account.
    -   _Web Root (public\_html or www)_ — The most direct route to your files.
    -   _Public FTP Root (public\_ftp)_ — The folder for your FTP files.
    -   _Document Root for:_ — The folder for the domain that you select from the menu.
3.  To display hidden files in the interface, select _Show Hidden Files (dotfiles)_.
    
4.  To prevent messages about character encodings from displaying, select _Disable Character Encoding Verification Dialogs_.
    
5.  Click _Save_.
    

### Character encoding verification dialogs

When you edit a file with the _Edit_ or _HTML Editor_ actions, an interface appears to confirm the file’s character encoding. Use the menu to select the correct character encoding for the file. Then, click _Edit_ to continue.

-   Click _Toggle Help_ for more information about how to select the correct character encoding.
-   Click _Disable Encoding Check_ to turn off future encoding verifications.

Warning:

If you select the wrong initial encoding, your file may become corrupt. If your file displays as a series of special characters, **immediately** abort your action and select the correct encoding. **Do not save the file**.

## Working with files and folders

The _File Manager_ interface allows you to perform many actions on your files and folders.

### Create or copy files or folders

To create a new file or folder, perform the following steps:

1.  Click _\+ File_ or _\+ Folder_ in the toolbar. A new interface will appear.
2.  Enter the new item’s name in the _New File Name:_ or _New Folder Name:_ text box.
    
    Note:
    
    To rename a folder or file, click the name. Then, enter the new name in the text box. Press the _Return_ key to save the change.
    
3.  Enter the location in which the system will create the item in the _New file will be created in:_ or _New folder will be created in:_ text box.
4.  Click _Create New File_ or _Create New Folder_.

To copy one or more files, perform the following steps:

1.  Select the files you want to copy.
    
    Note:
    
    You **cannot** create a copy of an item within the same folder.
    
2.  Click _Copy_ from the toolbar at the top of the interface. The _Copy_ interface will appear.
    
    Note:
    
    You can also right-click and select _Copy_ from the menu.
    
3.  In the _Copy_ interface, enter the file path for which you want to save the item in the _Enter the file path that you want to copy this file to:_ text box.
4.  Click _Copy File(s)_ to copy the files.

To copy a folder that contains files, perform the following steps:

1.  Select the folder that you want to copy.
2.  Use your preferred file compression application to compress the folder.
    
    Note:
    
    How you compress your folder will be based on your OS. For example, in macOS® 11.5, right-click the folder icon and select the `Compress "Folder"` option.
    
3.  Click _Upload_ from the toolbar and upload the compressed file by either dragging and dropping it or using the _Select File_ button.
4.  Now that your folder appears in the _File Manager_ interface, select it and click the _Extract_ in the toolbar in the top of the interface. This will extract your folder.

### Move files or folders

To move one or more files, perform the following steps:

1.  Select the file or files that you want to move.
2.  Click _Move_ in the toolbar at the top of the interface. The _Move_ interface will appear.
3.  Enter the file path that you want to move the file to in the _Enter the file path that you want to move this file to:_ text box.
4.  Click _Move File(s)_ to move the file.

You can also move files by:

-   Dragging a file icon into a new destination folder.
-   Clicking on a file and then clicking _Rename_ in the toolbar.

### Update file or folder permissions

To modify a file or folder’s permissions, perform the following steps:

1.  Select the file or folder for which to change the permissions.
2.  From the toolbar, click _Permissions_. The _Change Permissions_ interface will appear.
3.  Use the checkboxes or text boxes to change the item’s permissions. This setting defaults to `0644`.
4.  Click _Change Permissions_ to save your changes.

### Delete or restore files and folders

Note:

-   When you delete files or folders, the system does **not** permanently delete the files. Instead, the system moves the files to the _Trash_ folder.
-   Click _Empty Trash_ to permanently delete the _Trash_ folder’s contents.

To delete a file or folder, perform the following steps:

1.  Select the file or folder you want to delete.
2.  In the toolbar, click _Delete_. The _Trash_ interface will appear.
3.  Click _Confirm_ to confirm that you want to delete the file or folder.

To restore a file or folder, perform the following steps:

1.  Click _View Trash_ from the toolbar.
2.  Select the file or folder that you want to restore.
3.  Click _Restore_ in the toolbar.
4.  Confirm that you want to restore the item.

## Other item actions

Note:

The _Compress_ and _Extract_ actions will **only** work with the `.zip` format if Zip exists on your server. Your hosting provider can use WHM’s [_EasyApache 4_](https://docs.cpanel.net/whm/software/easyapache-4-interface) interface (_WHM >> Home >> Software >> EasyApache 4_) to install this [PHP extension](https://docs.cpanel.net/ea4/php/php-options/#current-php-extensions).

Right-click files or folders to select from a menu of actions that the system customizes based on the file’s type.

| Feature | Displays for | Description |
| :-- | :-- | :-- |
| _Upload_ | Files | Upload individual items, such as files or images.
Note:

You **cannot** upload a folder through this interface. Create a new folder and upload the desired files into it.



 |
| _Download_ | Files | Download files to save them locally. |
| _Rename_ | Files, Compressed Files, Folders | Rename the file or folder. |
| _Edit_ | Files | Open the selected file in an editor.

Warning:

You **cannot** edit a file in this interface if it contains more than one megabyte (1 MB) of data. To edit the file, you **must** download it and use a local editor.



 |
| _HTML Editor_ | Files | Open the selected HTML file in a visual [HTML editor](https://docs.cpanel.net/cpanel/files/html-editor).

Warning:

You **cannot** edit a file in this interface if it contains more than one megabyte (1 MB) of data. To edit the file, you **must** download it and use a local editor.



 |
| _View_ | Files | View the contents of the selected file. |
| _Extract_ | Compressed Files | Extract the selected `*.zip`, `*.Gz`, or `*.Bz2` archive and store the files in a folder. |
| _Compress_ | Files, Compressed Files, Folders | Compress the selected files or folders to a single `*.zip`, `*.Gz`, or `*.Bz2` archive and store the compressed file to a specified folder. |
| _Password Protect_ | Folders | Set a username and password to restrict access to a folder.

Note:

Your hosting provider must enable this feature.



 |
| _Leech Protection_ | Folders | Redirect users who have shared the password to a restricted area of your site. The system will redirect accounts that exceed a set number of logins in a two hour period to a selected URL, or receive an internal server error message.

Note:

Your hosting provider must enable this feature.



 |
| _Manage Indices_ | Folders | Customize the way users view a folder on the web.

Note:

Your hosting provider must enable this feature.



 |

### Search for an item

The _Search_ text box at the top-right corner of the interface allows users to search for a specific file. By default, the _Search_ text box searches all files in the home folder. You can limit the search to the document root at `/home/user/public_html`, where `user` represents your cPanel username. You can also limit the search to the folder in the interface.

To search for a file, perform the following steps:

1.  Use the _Search_ menu to select the folder to search. You can select from the following options:
    
    -   _All Your Files_
    -   _only public\_html_
    -   _Current Directory_
2.  Enter the desired file name in the text box.
    
3.  Click _Go_.
    

A new interface displays the filenames that match your search.

-   To go to a folder, or go to the folder that contains the file, double-click the desired item in the list.
-   If no files that include your search term exist, a _No records found_ message appears.
