---
created: 2022-08-05T11:24:09 (UTC -04:00)
tags: []
source: https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-perl-environments/
author: 
---

# Guide to Perl in cPanel - Perl Environments

---
# Guide to Perl in cPanel - Perl Environments

## [](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-perl-environments//#introduction)

Introduction

cPanel & WHM servers include multiple Perl environments. Your Perl modules can use these Perl environments, but they may require certain modifications in order to function correctly.

## [](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-perl-environments//#perl-environments)

Perl environments

### [](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-perl-environments//#cpanel--whm-version-94-and-later)

cPanel & WHM version 94 and later

| Perl environments | Perl version | Location | Applications that use this Perl environment | Additional information |
| --- | --- | --- | --- | --- |
| The server's Perl binary | 
-   Perl 5.10 on CentOS, CloudLinux, and RHEL 6, and Amazon Linux.
-   Perl 5.16 on CentOS, CloudLinux, and RHEL 7
-   Perl 5.26.3 on CentOS, CloudLinux, and RHEL 8.

. | `/usr/bin/perl` | 

-   Operating system maintenance scripts.
-   Some custom modules.

 | Manage modules for this Perl environment with the cpan command or with WHM's [_Module Installers_](https://docs.cpanel.net/whm/software/module-installers/) interface (_WHM >> Home >> Software >> Module Installers_). |
| cPanel-included Perl installation | Perl 5.32 | 

-   This environment self-embeds and compiles in the cPanel binary.
-   `/usr/local/cpanel/3rdparty/bin/perl` = This location is a symlink.
-   Install custom modules for this Perl environment into the `/opt/cpanel/perl5/532/site_lib` directory. `@INC` walks this directory after it walks all other directories for modules.

 | 

-   The cPanel & WHM software.
-   cPanel system maintenance scripts (in the `/usr/local/cpanel/scripts` directory).
-   CGI scripts.

 | 

-   This environment allows you to manage the system's Perl binary independently from cPanel & WHM. Use it when you write Perl scripts for a cPanel & WHM server.
-   For more information about how to modify scripts and modules to use this Perl environment, read our [Modules and Scripts](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-modules-and-scripts) documentation.

 |

### [](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-perl-environments//#cpanel--whm-version-86-through-92)

cPanel & WHM version 86 through 92

| Perl environments | Perl version | Location | Applications that use this Perl environment | Additional information |
| --- | --- | --- | --- | --- |
| The server's Perl binary | 
-   Perl 5.8.8 on CentOS, CloudLinux™, and Red Hat® Enterprise Linux (RHEL) 5 (cPanel & WHM version 56 **only**).
-   Perl 5.10 on CentOS, CloudLinux, and RHEL 6, and Amazon Linux.
-   Perl 5.16 on CentOS, CloudLinux, and RHEL 7.

 | `/usr/bin/perl` | 

-   Operating system maintenance scripts.
-   Some custom modules.

 | Manage modules for this Perl environment with the cpan command or with WHM's [_Module Installers_](https://docs.cpanel.net/whm/software/module-installers/) interface (_WHM >> Home >> Software >> Module Installers_). |
| cPanel-included Perl installation | Perl 5.30 | 

-   This environment self-embeds and compiles in the cPanel binary.
-   `/usr/local/cpanel/3rdparty/bin/perl` = This location is a symlink.
-   Install custom modules for this Perl environment into the `/opt/cpanel/perl5/530/site_lib` directory. `@INC` walks this directory after it walks all other directories for modules.

 | 

-   The cPanel & WHM software.
-   cPanel system maintenance scripts (in the `/usr/local/cpanel/scripts` directory).
-   CGI scripts.

 | 

-   This environment allows you to manage the system's Perl binary independently from cPanel & WHM. Use it when you write Perl scripts for a cPanel & WHM server.
-   For more information about how to modify scripts and modules to use this Perl environment, read our [Modules and Scripts](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-modules-and-scripts) documentation.

 |

### [](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-perl-environments//#cpanel--whm-version-78-through-84)

cPanel & WHM version 78 through 84

| Perl environments | Perl version | Location | Applications that use this Perl environment | Additional information |
| --- | --- | --- | --- | --- |
| The server's Perl binary | 
-   Perl 5.8.8 on CentOS, CloudLinux™, and Red Hat® Enterprise Linux (RHEL) 5 (cPanel & WHM version 56 **only**).
-   Perl 5.10 on CentOS, CloudLinux, and RHEL 6, and Amazon Linux.
-   Perl 5.16 on CentOS, CloudLinux, and RHEL 7.

 | `/usr/bin/perl` | 

-   Operating system maintenance scripts.
-   Some custom modules.

 | Manage modules for this Perl environment with the cpan command or with WHM's [_Module Installers_](https://docs.cpanel.net/whm/software/module-installers/) interface (_WHM >> Home >> Software >> Module Installers_). |
| cPanel-included Perl installation | Perl 5.28 | 

-   This environment self-embeds and compiles in the cPanel binary.
-   `/usr/local/cpanel/3rdparty/bin/perl` = This location is a symlink.
-   Install custom modules for this Perl environment into the `/opt/cpanel/perl5/528/site_lib` directory. `@INC` walks this directory after it walks all other directories for modules.

 | 

-   The cPanel & WHM software.
-   cPanel system maintenance scripts (in the `/usr/local/cpanel/scripts` directory).
-   CGI scripts.

 | 

-   This environment allows you to manage the system's Perl binary independently from cPanel & WHM. Use it when you write Perl scripts for a cPanel & WHM server.
-   For more information about how to modify scripts and modules to use this Perl environment, read our [Modules and Scripts](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-modules-and-scripts) documentation.

 |

### [](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-perl-environments//#cpanel--whm-version-70-through-76)

cPanel & WHM version 70 through 76

| Perl environments | Perl version | Location | Applications that use this Perl environment | Additional information |
| --- | --- | --- | --- | --- |
| The server's Perl binary | 
-   Perl 5.8.8 on CentOS, CloudLinux™, and Red Hat® Enterprise Linux (RHEL) 5 (cPanel & WHM version 56 **only**).
-   Perl 5.10 on CentOS, CloudLinux, and RHEL 6, and Amazon Linux.
-   Perl 5.16 on CentOS, CloudLinux, and RHEL 7.

 | `/usr/bin/perl` | 

-   Operating system maintenance scripts.
-   Some custom modules.

 | Manage modules for this Perl environment with the cpan command or with WHM's [_Module Installers_](https://docs.cpanel.net/whm/software/module-installers/) interface (_WHM >> Home >> Software >> Module Installers_). |
| cPanel-included Perl installation | Perl 5.26 | 

-   This environment self-embeds and compiles in the cPanel binary.
-   `/usr/local/cpanel/3rdparty/bin/perl` = This location is a symlink.
-   Install custom modules for this Perl environment into the `/opt/cpanel/perl5/526/site_lib` directory. `@INC` walks this directory after it walks all other directories for modules.

 | 

-   The cPanel & WHM software.
-   cPanel system maintenance scripts (in the `/usr/local/cpanel/scripts` directory).
-   CGI scripts.

 | 

-   This environment allows you to manage the system's Perl binary independently from cPanel & WHM. Use it when you write Perl scripts for a cPanel & WHM server.
-   For more information about how to modify scripts and modules to use this Perl environment, read our [Modules and Scripts](https://api.docs.cpanel.net/guides/guide-to-perl/guide-to-perl-in-cpanel-modules-and-scripts) documentation.

 |
