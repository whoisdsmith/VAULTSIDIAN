---
created: 2022-08-05T11:23:50 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/knowledge-base/third-party/third-party-software/
author: 
---

# Third Party Software | cPanel & WHM Documentation

---
## Third Party Software

___

Last modified: _July 26, 2022_

## Overview

cPanel & WHM ships with a large collection of third-party software that performs a wide variety of functions. A large number of third parties distribute their software under various open-source license agreements. cPanel, L.L.C. includes copies of all applicable licenses on your server, and ensures that source packages (SRPMs) are publicly available.

## License information

You can find copies of all of the license agreements that apply to cPanel, L.L.C.’s third-party software in the `/usr/local/cpanel/3rdparty/share/` directory on your server. For example, the `/usr/local/cpanel/3rdparty/share/common-licenses/LGPL-2` file is a copy of the GNU Lesser General Public License version 2.

### Find license information

To determine which license a third-party application uses, check the `/usr/local/cpanel/3rdparty/share/name/copyright` file, where `name` represents the template or package name.

Note:

Some third-party packages distribute under multiple licenses. Because of this, you may see multiple `License` entries.

### Find a source package (SRPM)

To find the SRPM for a specific third-party package, perform the following steps:

1.  Navigate to our [package update server](http://httpupdate.cpanel.net).
    
2.  Navigate to the directory for the version of cPanel & WHM for which we shipped the package.
    
3.  Navigate to the `src/` directory. The system lists all SRPMs as `.src.cpm` files.
    

For example, you can find Perl’s SRPM at `http://httpupdate.cpanel.net/RPM/11.46/src/` as the `cpanel-perl-514.5.14.4-4.cp1146.src.rpm` file.

## Third-party software

We publish lists of third-party software in each version’s [Release Notes](https://docs.cpanel.net/release-notes/).
