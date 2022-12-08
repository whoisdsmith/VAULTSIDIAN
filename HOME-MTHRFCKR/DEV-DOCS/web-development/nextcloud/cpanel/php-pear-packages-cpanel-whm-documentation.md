---
created: 2022-08-05T11:22:18 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/software/php-pear-packages/
author: 
---

# PHP PEAR Packages | cPanel & WHM Documentation

---
## PHP PEAR Packages

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/software/php-pear-packages/)

___

Last modified: _May 13, 2020_

## Overview

PHP PEAR packages are software components that developers write in the PHP language. The _PHP PEAR_ Packages interface allows you to search for and add PEAR packages to your website, or view all of your website’s available PHP packages.

## Module Include Path

The _Module Include Path_ section of the interface displays the location where the system will store your modules. If you wish to reference those modules from other modules or programs, use this include path.

## Using Your PHP Extension and Application

The _Using Your PHP Extensions Module(s)_ section of the interface lists a choice of code that you **must** include in the top of your PHP module or application. This code represents the location of PHP that the system will use to run the module or application.

## Install PEAR package

To install a PEAR package, perform one of the following actions:

-   If you know the name of the desired module, enter it in the _Install a PHP Extensions and Applications Package_ text box and click _Install Now_.
    
-   Enter a search term in the _Search_ text box and click _Go_, and click _Install_ next to the package that you wish to install.
    
-   Click _Show Available Modules_ to display a list of available PEAR packages, and click _Install_ next to the package that you wish to install.
    

The interface displays the following information for the modules:

-   _Module Name_ — The module’s name.
    
-   _Version_ — The PEAR package’s version number.
    
-   _Description_ — A description of the module.
    
-   _Actions_ — The actions that you may perform for that module.
    

## Installed PEAR packages

The _Installed Modules_ table lists all of the PEAR packages that exist on your server.

For each installed PEAR package, the table displays the following information:

-   _Module_ — Name The PEAR package’s name.
    
-   _Version_ — The PEAR package’s version number.
    
-   _Actions_ — You can perform the following actions for each PEAR package:
    
    -   _Update_ — Update the PEAR package.
        
    -   _Reinstall_ — Reinstall the PEAR package.
        
    -   _Uninstall_ — Remove the PEAR package from your server.
        
    -   _Show Docs_ — Read the PEAR package’s documentation.
        

## System modules

cPanel includes specific pre-installed PEAR packages. To see a list of pre-installed PEAR packages, click _Show System Installed Modules_.

Warning:

You **cannot** remove cPanel’s system modules.
