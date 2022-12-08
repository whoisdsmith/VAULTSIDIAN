---
created: 2022-08-05T11:23:35 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/software/perl-modules/
author: 
---

# Perl Modules | cPanel & WHM Documentation

---
## Perl Modules

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/software/perl-modules/)

___

Last modified: _July 11, 2022_

## Overview

Perl modules are software components in the Perl language. This interface allows you to search for and install Perl modules from the [CPAN](http://search.cpan.org/) repository to your website.

Note:

You **must** install Perl modules before you can use them inside of a Perl program.

## Module Include Path

The Module Include Path section of the interface displays the location where the system will store your modules. If you wish to reference those modules from other modules or programs, use this include path.

## Using Your Perl Module

The _Using Your Perl Module(s)_ section of the interface lists a choice of code that you **must** include in the top of your Perl script. This code represents the location of Perl that the system will use to run the script.

## Install Perl module

To install a Perl module, perform one of the following actions:

-   If you know the name of the desired module, enter it in the _Install a Module_ text box and click _Install Now_.
    
-   Enter a search term in the _Search_ text box and click _Go_. The interface will display modules related to that search term.
    
-   Click _Show Available Modules_ to display a list of available Perl modules at the CPAN repository.
    

Note:

The interface will **not** display every module available at CPAN.

The interface displays the following information for the modules:

-   _Module_ — Name The module’s name.
    
-   _Version_ — The module’s version number.
    
-   _Actions_ — The actions that you may perform for that module. For each module, you can perform the following actions:
    

Note:

If you did **not** find the desired module, repeat this process until you locate the appropriate module.

## The Installed Modules table

The _Installed Modules_ table displays all of the modules that exist on your cPanel account.

For each installed module, the table displays the following information:

-   _Module_ — Name The module’s name.
    
-   _Version_ — The module’s version number.
    
-   _Actions_ — The actions that you may perform for that module. For each module, you can perform the following actions:
    
    -   _Update_ — Update the module.
        
    -   _Reinstall_ — Reinstall the module from CPAN.
        
    -   _Uninstall_ — Remove the module from your server.
        
    -   _Show Documentation_ — Read the module’s documentation on CPAN.
        

## System modules

cPanel & WHM includes specific Perl modules.

-   To display a list of the system-installed Perl modules, click _Show System Installed Modules_.
    
-   For more information on Perl modules, read our [Guide to Perl in cPanel & WHM](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-perl-environments/) and [Third-Party Software](https://docs.cpanel.net/knowledge-base/third-party/third-party-software/) documentation.
