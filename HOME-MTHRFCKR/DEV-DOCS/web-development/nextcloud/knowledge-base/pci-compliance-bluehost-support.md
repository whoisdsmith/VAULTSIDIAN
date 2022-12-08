---
created: 2022-08-05T09:40:50 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/pci-compliance
author: 
---

# PCI Compliance | Bluehost Support

---
Bluehost does not support PCI compliance on all accounts.

-   Shared Hosting accounts will not be PCI compliant on their own.
-   Shared Hosting customers can achieve PCI compliance with a full CDN solution (meaning DNS will only be fully pointed through the service) such as [Cloudflare](https://www.bluehost.com/help/article/cloud-flare-guide).

Customers on VPS and Dedicated servers will be able to achieve PCI compliance; however, this is ultimately up to you. If you are able to provide a valid PCI scan, Bluehost will make the updates identified in the scan when possible.

When doing a PCI scan, occasionally, the scanning company finds problems with certain things. This article aims to address some common issues and provide account owners with peace of mind.

___

-   [Weak Ciphers](https://www.bluehost.com/help/article/pci-compliance#ciphers)
-   [UserDir options for a domain](https://www.bluehost.com/help/article/pci-compliance#userdir)
-   [Mod\_frontpage](https://www.bluehost.com/help/article/pci-compliance#mod_frontpage)
-   [Mailman](https://www.bluehost.com/help/article/pci-compliance#mailman)
-   [Vulnerability in /scgi-bin](https://www.bluehost.com/help/article/pci-compliance#scgi)

___

## Weak Ciphers

First, here is an example of what a problem report might read like:

```
Protocol: TCP 
  Port: 443 
  Program:  https
  Synopsis: The remote service supports the use of weak SSL  ciphers. 
  Description: The remote host supports the use of SSL ciphers that offer either weak   encryption or no encryption at all. 
      See also http://www.openssl.org/docs/apps/ciphers.html
  Solution:  Reconfigure the affected application if possible to avoid use of weak ciphers. 
```

In this case, this is **NOT** cPanel related, but a problem with the Apache .conf file. We can identify this by the port number that was reported. If the port had been 2095, 2082... etc., then it is cPanel, and a Bluehost administrator will need to fix the ciphers. But if the port is 443, it means the cipher line in the apache .conf file is missing for that domain.

Bluehost technical support can run a rebuild on Apache, and it should add the cipher line into the Apache .conf file.

## UserDir options for a domain

Again, here is an example:

```
Protocol: TCP
Port: 443/80 
Program: https/http 
```

Some distributions of Apache, especially in Red Hat 7.0, allow an attacker to probe a system for user names via requests for user home pages (e.g., http://host/~username).

Disabling the UserDir directive in the Apache configuration file (httpd.conf) will prevent this, although it will also prevent users from providing their own web pages. Alternately, specify ErrorDocuments for both 403 (Forbidden) and 404 (Page Not Found) Responses. We can disable UserDir on an account. Contact Technical Support to have this changed.

Currently, when disabling it, it will update /var/cpanel/userdata/username/somedomain.com however it will **not** update /var/Cpanel/userdata/username/somedomain.com\_SSL. Technical support may need to be reminded to check both locations and ensure userdirprotect is changed from -1 to 1.

We intend to fix this so both locations are updated automatically in the future when requests like this are made.

## Mod\_frontpage

Most people know this is just a false positive on the PCI scan. However, the Patch information we have on Mod\_frontpage that makes it secure will be provided for comfort's sake.  
 

The version that is running is frontpage-2002-SR1.2 and poses no security threat.

Also, with Apache 2.x or 2.2.x compiled through EasyApache, fpexe is replaced by "/scripts/fp-auth" which is never setuid root and poses no security threat.

## Mailman

Sometimes a PCI scan will yield something like:

```
Unencrypted Login Information Disclosure for the following link: http://example.com/mailman/admin/mailman
```

Unfortunately, the mailman alias is a global httpd.conf alias, so there is no way to turn it off on a per-user basis. We use suexec, and that anything with mailman is run as a different user on the server, as like with Anonymous FTP, than a customer's scripts.

We are aware that mailman does allow unprotected passwords, but any compromise to that system will **NOT** compromise a customer's account. We are aware some of the PCI scans are flagging this and are looking into a possible fix.  
 

## Vulnerability in /scgi-bin

This will come up as a false positive. /scgi-bin/ is aliased to the scgiwrap binary, which is a common patch for cPanel and Suexec. This script can only be run by the nobody user (and thus can't run from an http request) as demonstrated below:

**$ curl boundlessether.com/scgi-bin/namazu.cgi**

```
scgiwrap: Caller must be the nobody user
```

**$ curl boundlessether.com/scgi-bin/non\_existant\_script.cgi**

```
scgiwrap: Caller must be the nobody user
```

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
