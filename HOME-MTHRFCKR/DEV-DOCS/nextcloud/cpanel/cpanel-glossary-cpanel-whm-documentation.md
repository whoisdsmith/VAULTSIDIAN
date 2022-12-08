---
created: 2022-08-05T11:23:23 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/
author: Authoritative Nameserver
---

# cPanel Glossary | cPanel & WHM Documentation

---
## cPanel Glossary

_Valid for versions 106 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/82/)

#### [88](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/88/)

#### [90](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/90/)

#### [92](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/92/)

#### [94](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/94/)

#### [96](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/96/)

#### [98](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/98/)

#### [100](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/100/)

#### [102](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/102/)

#### [104](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/104/)

#### [106](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/)

___

Last modified: _July 13, 2022_

## A

##### A (Address) Entry

A record that resides on your server and that contains your server’s hostname and IP address. The A entry tells DNS servers the identity of your server, which allows visitors to find your server on the internet. You can add an A entry for your hostname in WHM’s [_Add an A Entry for Your Hostname_](https://docs.cpanel.net/whm/dns-functions/add-an-a-entry-for-your-hostname) interface (_WHM >> Home >> DNS Functions >> Add an A Entry for Your Hostname_).

##### Absolute Domain Name

See [Fully Qualified Domain Name](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#fqdn).

##### Access Control List (ACL)

Permissions that a server’s owner grants to a reseller. You can define ACLs in the _Edit Privileges_ section of WHM’s [_Reseller Center_](https://docs.cpanel.net/whm/resellers/reseller-center) interface (_WHM >> Home >> Resellers >> Reseller Center_).

Note:

Access Control Lists are **not** the same as Account Creation Limits.

##### Account

A record that lets you access privatized information. For example, your cPanel account lets you manage your website. You can create new cPanel & WHM accounts in WHM’s [_Create a New Account_](https://docs.cpanel.net/whm/account-functions/create-a-new-account) interface (_WHM >> Home >> Account Functions >> Create a New Account_).

##### Account Enhancements

Account Enhancements allow you to control whether a cPanel account can access a third-party application, without modifying the account’s [package](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/#package) settings.

-   To add or remove Account Enhancements from an existing cPanel account, use WHM’s [_Modify an Account_](https://docs.cpanel.net/whm/account-functions/modify-an-account) interface (_WHM >> Home >> Account Functions >> Modify an Account_).
-   You can add Account Enhancements to a new cPanel account in WHM’s [_Create a New Account_](https://docs.cpanel.net/whm/account-functions/create-a-new-account) interface (_WHM >> Home >> Account Functions >> Create a New Account_).

Note:

-   If you have not installed any third-party applications that use Account Enhancements, the _Account Enhancements_ section will not appear in WHM’s [_Modify an Account_](https://docs.cpanel.net/whm/account-functions/modify-an-account) (_WHM >> Home >> Account Functions >> Modify an Account_) or [_Create a New Account_](https://docs.cpanel.net/whm/account-functions/create-a-new-account) interfaces (_WHM >> Home >> Account Functions >> Create a New Account_).
    
-   To configure a third-party application to use Account Enhancements, you must [add account enhancements](https://api.docs.cpanel.net/guides/guide-to-cpanel-plugins-in-the-jupiter-theme/guide-to-cpanel-plugins-add-plugins/#add-account-enhancements) during the installation process.
    
-   To allow a [Reseller](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#reseller) to assign and unassign Account Enhancements, you must enable the _Use Root Account Enhancements_ privilege in WHM’s [_Edit Reseller Nameservers and Privileges_](https://docs.cpanel.net/whm/resellers/edit-reseller-nameservers-and-privileges) interface (_WHM >> Home >> Resellers >> Edit Reseller Nameservers and Privileges_).
    

##### Account Suspension

The restriction of an account, usually because of unpaid fees. Hosting providers can suspend accounts until they receive payment, and then unsuspend the account.

-   [Suspended accounts retain all of their data](https://docs.cpanel.net/knowledge-base/accounts/what-happens-when-you-suspend-an-account), but visitors cannot access their websites.
-   You can suspend and unsuspend accounts in WHM’s [_Manage Account Suspension_](https://docs.cpanel.net/whm/account-functions/manage-account-suspension) interface (_WHM >> Home >> Account Functions >> Manage Account Suspension_).

##### Account-Level Filter

A rule that determines where to deliver email for a domain’s main email account that meets certain criteria.

More:

For more information, read our [How to Configure Mail Filters](https://docs.cpanel.net/knowledge-base/email/how-to-configure-email-filters/) documentation.

##### Addon Domain

An additional domain name that a cPanel account owns. The system stores each addon domain in its own configurable directory.

-   This allows website owners to manage multiple domains from a single cPanel account.
-   You can create and manage addon domains in cPanel’s [_Domains_](https://docs.cpanel.net/cpanel/domains/domains) interface (_cPanel >> Home >> Domains >> Domains_).

Note:

You **must** register addon domains with a [domain name registrar](http://wikipedia.org/wiki/Domain_name_registrar).

##### Addons (cPAddons)

Additional services for cPanel users (for example, blogs, message boards, and shopping carts). You can install cPAddons in WHM’s [_Install cPAddons Site Software_](https://docs.cpanel.net/whm/cpanel/install-cpaddons-site-software) interface (_WHM >> Home >> cPanel >> Install cPAddons Site Software_).

Warning:

In cPanel & WHM version 104, we deprecated the cPAddons-related interfaces and plan to remove it in a future release. For more information, read our [cPanel Deprecation Plan](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-deprecation-plan).

##### AlmaLinux OS

An open-source, community-driven Linux operating system distribution from [CloudLinux, Inc.](https://www.cloudlinux.com/). [AlmaLinux OS](https://almalinux.org/) is one of cPanel & WHM’s supported operating systems.

For more information, read our [Installation Guide](https://docs.cpanel.net/installation-guide/) documentation.

##### Amazon® Linux

[Amazon Machine Instance (AMI)](https://aws.amazon.com/amazon-linux-ami/) images.

More:

For more information, read our [How to Launch an AWS AMI Instance](https://docs.cpanel.net/knowledge-base/web-services/launch-an-aws-ami-instance/) documentation.

##### Analog

[A program](http://www.c-amie.co.uk/analog/) that provides information about the visitors to a website in both graphical and statistical views. You can work with information from Analog in cPanel’s [_Analog Stats_](https://docs.cpanel.net/cpanel/metrics/analog-stats) interface (_cPanel >> Home >> Metrics >> Analog Stats_).

##### Ancestor Domain Control Validation

Successful [Domain Control Validation](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#domain-control-validation) (DCV) of a domain applies to all of its subdomains as well. For example, if the `example.com` domain succeeds, the `store.example.com` subdomain would also succeed.

##### Anonymous FTP

A protocol that lets visitors who don’t have FTP accounts upload and download files to and from a website. Although it poses security risks, anonymous FTP is convenient if you want to make files publicly available to download. You can configure anonymous FTP in cPanel’s [_Anonymous FTP_](https://docs.cpanel.net/cpanel/files/anonymous-ftp) interface (_cPanel >> Home >> Files >> Anonymous FTP_).

Important:

When you set up anonymous FTP, you **must** change file permissions and directory access permissions in order to protect any sensitive information.

##### Apache®

[A web server software](https://www.apache.org/) that receives requests from browsers and serves web pages to the browsers. You can configure Apache in WHM’s [_Apache Configuration_](https://docs.cpanel.net/whm/service-configuration/apache-configuration) interface (_WHM >> Home >> Service Configuration >> Apache Configuration_).

##### Apache Handler

[A record](https://httpd.apache.org/docs/current/handler.html) that determines how the Apache software processes a specific type of file. By default, Apache only handles certain file types. You can configure Apache handlers in cPanel’s [_Apache Handlers_](https://docs.cpanel.net/cpanel/advanced/apache-handlers) interface (_cPanel >> Home >> Advanced >> Apache Handlers_).

##### Apache SpamAssassin™

An application that filters suspected spam. You can configure [Apache SpamAssassin](http://spamassassin.apache.org/) to filter spam more or less aggressively, based on the user’s needs.

-   You can enable this service in WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_).
-   You can create spam filters in cPanel’s [_Spam Filters_](https://docs.cpanel.net/cpanel/email/spam-filters) interface (_cPanel >> Home >> Email >> Spam Filters_).

##### API Token

An authorization key hash that [lets third-party applications run API functions](https://api.docs.cpanel.net/guides/guide-to-api-authentication/guide-to-api-authentication-api-tokens-in-whm/) with WHM account data. You can manage API tokens in WHM’s [_Manage API Tokens_](https://docs.cpanel.net/whm/development/manage-api-tokens-in-whm) interface (_WHM >> Home >> Development >> Manage API Tokens_).

##### Application Key (app\_key)

A value that uniquely identifies each application within the cPanel interface.

-   [Each `app_key` value](https://api.docs.cpanel.net/guides/guide-to-cpanel-interface-customization-and-branding-in-the-jupiter-theme/guide-to-cpanel-interface-customization-appkeys/) is unique to a single item.
-   You can use these values when you develop [cPanel plugins](https://api.docs.cpanel.net/guides/guide-to-cpanel-plugins-in-the-jupiter-theme/).

##### Application Programming Interface (API)

A set of programming standards and tools that third-party or internal developers can use to interact with a software application. cPanel, L.L.C. provides [APIs](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#api) that you can use to customize and integrate with [cPanel or Webmail](https://api.docs.cpanel.net/cpanel/introduction/), [WHM](https://api.docs.cpanel.net/whm/introduction/), and [Manage2](https://docs.cpanel.net/manage2/knowledge-base/guide-to-the-manage2-api).

##### atd

A [daemon](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#daemon) that performs scheduled tasks for the `at` command on Linux operating systems. cPanel & WHM uses the `at` daemon to [check system health after updates](https://docs.cpanel.net/whm/server-configuration/update-preferences).

##### Authentication

A process that lets you confirm the identity of someone with whom the server shares sensitive information. In software, authentication usually involves either a username and password set or a public and private key pair.

-   You can configure two-factor authentication (2FA) for [cPanel](https://docs.cpanel.net/cpanel/security/two-factor-authentication-for-cpanel) or [WHM](https://docs.cpanel.net/whm/security-center/two-factor-authentication-for-whm) accounts.
-   Third-party integrators can use [several methods to authenticate with cPanel & WHM](https://api.docs.cpanel.net/guides/guide-to-api-authentication/).

##### Authoritative Nameserver

A nameserver that returns responses to queries for one or more [DNS zones](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#dnszones). Name Server (NS) records point to the domain’s authoritative nameserver. These nameservers **don’t** cache DNS information for related domains.

More:

For more information, read our [How to Set Up Nameservers in a cPanel & WHM Environment](https://docs.cpanel.net/knowledge-base/dns/how-to-set-up-nameservers-in-a-cpanel-environment) documentation.

##### AutoConfig

A process that sets up users’ Thunderbird®, Outlook® or Outlook® Express accounts to receive their cPanel email.

More:

For more information, read our [AutoConfig and Autodiscover](https://docs.cpanel.net/knowledge-base/email/autoconfig-and-autodiscover/) documentation.

##### Autoresponder

Autoresponders allow you to automate replies to incoming email. You can configure automatic email response messages in cPanel’s [_Autoresponders_](https://docs.cpanel.net/cpanel/email/autoresponders) interface (_cPanel >> Home >> Email >> Autoresponders_).

##### AutoSSL

A feature in WHM that provides free, [Domain-Validated SSL certificates](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#domain-validated-ssl) to users’ domains.

-   The system periodically inspects users’ installed certificates and replaces those that are about to expire or that are insufficient to provide a baseline level of security.
-   This feature is available in WHM’s [_Manage AutoSSL_](https://docs.cpanel.net/whm/ssl-tls/manage-autossl) interface (_WHM >> Home >> SSL/TLS >> Manage AutoSSL_).

##### AWStats (Advanced Web Statistics)

A program that provides information about the visitors to a website. [AWStats](http://awstats.sourceforge.net/) presents information in both graphical and statistical views. You can work with AWStats data in cPanel’s [_Awstats_](https://docs.cpanel.net/cpanel/metrics/awstats) interface (_cPanel >> Home >> Metrics >> Awstats_).

## B

##### Backscatter

Backscatter is the term for bounced email messages (or failed Delivery Status Notifications) that the system erroneously sent to a domain when an attacker forged the domain’s name as the sender of spam.

-   Use [SPF](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#spf) on your mail server to reduce backscatter.
-   Outscatter, misdirected bounces, blowback, and collateral spam are common synonyms for this term.

##### Backup

A copy of your website’s or server’s files, directories, databases, and email configurations.

-   We recommend that [cPanel users](https://docs.cpanel.net/cpanel/files/backup-for-cpanel) store a backup copy of their website on a personal computer.
-   We recommend that [system administrators](https://docs.cpanel.net/whm/backup/backup-configuration) create server and account backups often.

##### Bandwidth

The total size of all of the files that the system transferred to visitors’ computers.

-   Every time a visitor views a file, such as a web page, image, video, or audio file, the server transfers that file to the visitor’s computer.
-   Hosting providers often limit a site owner’s bandwidth because it can affect the performance of the server.

cPanel users can check bandwidth use in cPanel’s [_Bandwidth_](https://docs.cpanel.net/cpanel/metrics/bandwidth) interface (_cPanel >> Home >> Metrics >> Bandwidth_).

##### Bayes Testing (Bayesian Spam Filtering)

A method by which you can filter spam based on statistics. This method uses tokens (generally words) in emails to determine whether an incoming message is spam.

-   This technique relies on [Bayesian statistics](http://en.wikipedia.org/wiki/Bayesian_statistics). Bayesian classifiers correlate the use of tokens with spam and non-spam emails to calculate a probability that an email is or is not spam.
-   You can create spam filters in cPanel’s [_Spam Filters_](https://docs.cpanel.net/cpanel/email/spam-filters) interface (_cPanel >> Home >> Email >> Spam Filters_).
-   The _Junk_ button in Roundcube also uses Bayesian spam filtering to train the system to recognize spam.

##### Berkeley Internet Name Domain (BIND)

The most prominently-used DNS server software. This is also referred to as `named`.

More:

For more information, visit the [BIND website](https://www.isc.org/software/bind).

##### Blackhole (Black Hole)

One of the options for how to handle mail that the default or catch-all email addresses of cPanel users receive.

-   This option discards mail after the server accepts it. For this reason, it may result in additional spam that your users receive, and places a larger load on your server than the fail option.
-   You can create filters in cPanel’s [_Spam Filters_](https://docs.cpanel.net/cpanel/email/spam-filters) interface (_cPanel >> Home >> Email >> Spam Filters_).

##### Blacklist

**See also:** [Greylisting](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#greylisting), [Whitelist](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#whitelist).

A method of access control for privileges to a defined list of users, programs, or network addresses. In cPanel & WHM, this term can refer to:

-   In [BoxTrapper](https://docs.cpanel.net/cpanel/email/boxtrapper), a list of rejected email senders. BoxTrapper automatically deletes any messages from senders who are on the blacklist.
    
-   In [cPHulk](https://docs.cpanel.net/whm/security-center/cphulk-brute-force-protection), a list of rejected IP addresses. cPHulk **never** allows logins to your server from IP addresses on the blacklist.
    
-   In [Exim](https://docs.cpanel.net/whm/service-configuration/exim-configuration-manager), a list of IP addresses from which the system drops SMTP connections unconditionally.
    

##### Blocker

A condition that the system discovers and which doesn’t allow the system to perform a version update. The cPanel & WHM update process performs [compatibility checks to identify blockers](https://docs.cpanel.net/knowledge-base/cpanel-product/upgrade-blockers) before it upgrades to a new version.

##### Bounce Message

An email reply that informs a sender that there was a problem with email delivery.

##### BoxTrapper

An application that requires senders to reply to a verification email in order to filter spam through challenge-response verification.

-   The system only accepts the original email **after** the sender replies to the verification message.
-   You can configure these settings in cPanel’s [_BoxTrapper_](https://docs.cpanel.net/cpanel/email/boxtrapper) interface (_cPanel >> Home >> Email >> BoxTrapper_).

You may also see the following terms:

-   BoxTrapper Blacklist — A list of incoming email addresses that the [BoxTrapper](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#boxtrapper) application automatically blocks. cPanel automatically sends a configurable warning message when it receives mail from a [blacklisted](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#blacklist) address.
    
-   BoxTrapper Ignore List — A list of incoming email addresses that [BoxTrapper](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#boxtrapper) automatically ignores.
    
    Note:
    
    cPanel does **not** send a warning notification on receipt of mail from these addresses.
    
-   BoxTrapper Whitelist — A list of incoming email addresses that [BoxTrapper](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#boxtrapper) automatically accepts.
    

##### Branding

Changes to the cPanel interface to match your company’s logo and brand. Branding changes also include updates to image assets or text labels. For more information, read our [Guide to cPanel Interface Customization and Branding in the Jupiter Theme](https://api.docs.cpanel.net/guides/guide-to-cpanel-interface-customization-and-branding-in-the-jupiter-theme/).

##### Brute Force Attack

An attack during which the attacker enters a large number of combinations of characters in an attempt to decrypt a key. WHM includes [cPHulk](https://docs.cpanel.net/whm/security-center/cphulk-brute-force-protection/), a protection system that lets you lock out brute force attackers after a specified number of failed attempts.

##### Bug

See [Feature](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#feature).

##### Build

A release of cPanel & WHM that uses a specific version number. cPanel, L.L.C. [releases cPanel & WHM builds in different stages](https://docs.cpanel.net/knowledge-base/cpanel-product/product-versions-and-the-release-process) through our [named release tiers](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#release-tiers).

## C

##### .crt File

The file for an [SSL certificate](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl/), an electronic document that ties a public key to a trusted entity. This electronic document is a key piece in the authentication process.

##### Cache

Stored information that the server accesses in lieu of the information source, saving bandwidth and time.

-   You can configure DNS record caches in WHM’s [_Edit DNS Zone_](https://docs.cpanel.net/whm/dns-functions/edit-dns-zone) interface (_WHM >> Home >> DNS Functions >> Edit DNS Zone_).
-   You can configure disk usage cache data in WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_).

##### Cascading Style Sheets (CSS)

A style sheet language in markup language that describes how a document, often in HTML, should appear. The [World Wide Web Consortium (W3C)](https://www.w3.org/) regulates CSS standards.

##### Catch-All Address (Domain Default Address)

Note:

This address is **not** the same as the cPanel account’s system user email account, which catches mail for domains that don’t have a configured default address.

The email address to which cPanel & WHM routes any email messages to nonexistent email accounts on a domain. You can set up a default address in cPanel’s [_Default Address_](https://docs.cpanel.net/cpanel/email/default-address) interface (_cPanel >> Home >> Email >> Default Address_).

##### CentOS

An open-source Linux operating system distribution from the [CentOS Project](https://www.centos.org/). CentOS is one of [cPanel & WHM’s supported operating systems](https://docs.cpanel.net/installation-guide/system-requirements-centos/).

##### Certificate

An electronic document that states the identity of a server. This lets end users know that they communicated with the correct website.

More:

For more information, read our [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl/).

##### Certificate Authority (CA)

An entity that issues digital certificates for server verification.

More:

For more information, read our [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl/).

##### Certificate Authority Authorization Record (CAA)

A DNS record that lets you specify which CA will issue an SSL certificate for a domain. If no CAA record exist for a domain, all CAs can issue a SSL certificate for a domain.

More:

For more information, read Wikipedia’s article about [DNS Certification Authority Authorization](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization) and our our [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl/).

##### Certificate Authority Bundle (CA Bundle)

A file that contains details about an [SSL certificate](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ssl-certificate), such as its issuer and that issuer’s certificates and chain of trust. Browsers include a built-in list of trusted certificate authorities, and compare their lists against CA bundles to determine whether to trust an authority.

More:

For more information, read our [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl/).

##### Certificate Signing Request (CSR)

A request that you send to a certificate authority for an identity certificate.

-   cPanel can generate a CSR for you. However, authorities vary with regard to the information that they require. Check their requirements before you apply for a certificate.
-   You can manage CSRs in the _Certificate Signing Requrest (CSR)_ section of cPanel’s [_SSL/TLS_](https://docs.cpanel.net/cpanel/security/ssl-tls) interface (_cPanel >> Home >> Security >> SSL/TLS_).

More:

For more information, read our [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl/).

##### Chain Of Trust

A record of which certificate authorities have vouched for the authenticity of other certificate authorities. For a certificate authority to sell certificates, another certificate authority must vouch for them.

More:

For more information, read our [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl/).

##### Change Log

A record of the changes that each development or production release of cPanel & WHM includes.

More:

For more information, read our [Change Log](https://docs.cpanel.net/changelogs).

##### Character Set

A code that pairs a sequence of characters with a set of numbers, which allows a computer to store and transmit the characters. UTF-8 and ASCII are popular character sets.

More:

For more information, read Wikipedia’s article about [character sets](http://en.wikipedia.org/wiki/Character_set).

##### Child Node

A non-authoritative [linked node](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#linked-node) that receives tasks from a [parent node](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#parent-node).

##### Classless Inter-Domain Routing (CIDR)

A routing method that lets you create routable subnets with finer granularity than the traditional network classes.

-   CIDR notation is the combination of an IP address and an abbreviated subnet mask. This mask consists of a slash (`/`) and the number of bits (which is between `0` and `32`). Larger numbers indicate smaller network segments. For example, the CIDR notation `192.168.1.64/29` corresponds to an IP address of `192.168.1.64` and a subnet mask of `255.255.255.248`, with a total of eight addresses in the segment.
-   Some cPanel & WHM interfaces (for example, cPanel’s [_IP Blocker_](https://docs.cpanel.net/cpanel/security/ip-blocker) interface (_cPanel >> Home >> Security >> IP Blocker_)) use CIDR notation.

##### Client

Any application that accesses a service on another computer. When you work with cPanel & WHM, for example, you may need to configure [an SFTP client](https://docs.cpanel.net/knowledge-base/ftp/how-to-configure-your-sftp-client/).

-   Web clients include browsers like as Google Chrome™.
-   FTP clients include FileZilla® and Cyberduck.

##### CloudLinux™

A commercial Linux operating system distribution from [CloudLinux, Inc.](https://www.cloudlinux.com/). CloudLinux is one of cPanel & WHM’s supported operating systems.

For more information, read our [Installation Guide](https://docs.cpanel.net/installation-guide/) documentation.

##### Cluster

A group of linked servers. cPanel & WHM has two separate clustering options:

-   [DNS clusters](https://docs.cpanel.net/whm/clusters/dns-cluster) keep DNS records synchronized among a group of computers and eliminates the need for manual updates.
    
-   [Configuration clusters](https://docs.cpanel.net/whm/clusters/configuration-cluster) allow the system to replicate settings from a primary server to secondary servers.
    

##### Command Line Interface (CLI)

A means of interacting with a computer that consists of entering commands. Unix systems often call this a shell.

More:

For more information, read our [How to Access the Command Line](https://docs.cpanel.net/knowledge-base/general-systems-administration/how-to-access-the-command-line) documentation.

##### Common Gateway Interface (CGI)

A protocol that allows a web server to communicate with scripts and other software. The server usually stores CGI scripts in the `cgi-bin` directory.

More:

For more information, read the [Wikipedia Common Gateway Interface article](https://en.wikipedia.org/wiki/Common_Gateway_Interface).

##### Common Vulnerabilities and Exposures (CVE®) System

An archive of publicly-known security threats, vulnerabilities, and exposures. The [CVE system](https://cve.mitre.org/) assigns numbers (CVE identifiers), which provide a reference point when you evaluate the coverage and effectiveness of security tools and services.

##### Compiler

A computer program that translates source code that developers wrote into a language that a computer can read. This helps to protect your server from attacks and vulnerability exploits.

-   You will need to use a compiler with Ruby and other types of application.
-   Use WHM’s [_Compiler Access_](https://docs.cpanel.net/whm/security-center/compiler-access) interface (_WHM >> Home >> Security Center >> Compiler Access_) to manage your system’s complier access.

##### Comprehensive Perl Archive Network (CPAN)

The main repository of [Perl modules](https://api.docs.cpanel.net/guides/guide-to-perl/).

-   The [CPAN library](http://www.cpan.org/) contains over 12,000 modules, most of which are free.
-   You can search CPAN for Perl modules and install them in cPanel’s [_Perl Modules_](https://docs.cpanel.net/cpanel/software/perl-modules/) interface (_cPanel >> Home >> Software >> Perl Modules_).

##### ConfigServer Security & Firewall (CSF)

A stateful firewall, login/intrusion detection, and security plugin for Linux-based servers.

More:

For more information, visit the [CSF website](https://www.configserver.com/cp/csf.html).

##### cPanel

The companion software to [WHM](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#whm). cPanel, L.L.C. designs cPanel to simplify website maintenance for website owners.

More:

-   For more information, read our [documentation for cPanel’s interfaces](https://docs.cpanel.net/cpanel).
-   Developers can [create plugins for cPanel](https://api.docs.cpanel.net/guides/guide-to-cpanel-plugins-in-the-jupiter-theme/).

##### cPanel Market

A system that administrators can use to sell products from various vendors (for example, the cPanel Store) through the cPanel & WHM interface. For example, cPanel’s [_SSL/TLS Wizard_](https://docs.cpanel.net/cpanel/security/ssl-tls-wizard) interface (_cPanel >> Home >> Security >> SSL/TLS Wizard_) uses the cPanel Market to sell [SSL certificates](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ssl-certificate).

Note:

You can [create custom provider modules](https://api.docs.cpanel.net/guides/guide-to-cpanel-market-provider-modules/) for the cPanel Market.

##### cPanel Store

Our online store, through which customers can [purchase various services and products](https://docs.cpanel.net/knowledge-base/cpanel-product/how-to-purchase-a-cpanel-license) such as licenses, support, and [SSL certificates](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ssl-certificate).

##### cPanelID

Your login credentials for cPanel’s Store, ticket system, and [Manage2](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#manage2). You can use your [cPanelID](https://docs.cpanel.net/knowledge-base/accounts/cpanelid/) as an [External Authentication](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#external-authentication) method.

-   Third-party developers can use [External Authentication modules](https://api.docs.cpanel.net/guides/guide-to-external-authentication/) to authenticate with OpenID Connect-compliant identity providers.
-   You can configure External Authentication in WHM’s [_Manage External Authentications_](https://docs.cpanel.net/whm/security-center/manage-external-authentications) interface (_WHM >> Home >> Security Center >> Manage External Authentication_).

##### cpdavd

cPanel’s WebDAV [daemon](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#daemon), which provides access to cPanel’s [_Web Disk_](https://docs.cpanel.net/cpanel/files/web-disk) interface (_cPanel >> Home >> Files >> Web Disk_).

##### cPHulk

A WHM feature that helps [protect your web server](https://docs.cpanel.net/whm/security-center/cphulk-brute-force-protection) from malicious users who try to gain unauthorized access through brute force attacks.

##### cpmove

A copy of a user’s website, which you can create when you run the [`/usr/local/cpanel/scripts/pkgaccount`](https://docs.cpanel.net/whm/scripts/the-pkgacct-script/) script. The `cpmove` file is useful as a backup, and you can manually upload it to restore the user’s web files.

##### cpsrvd

cPanel Service [Daemon](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#daemon), the software that runs cPanel & WHM on your server.

##### CPU Load

The amount of processing capacity that programs on your server are consuming, in percentage format.

More:

For more information, read the [Troubleshooting High Server Loads on Linux Servers](https://forums.cpanel.net/threads/troubleshooting-high-server-loads-on-linux-servers.319352/) forum article.

##### cpuser (file)

A file that has a cPanel account’s user information. It also contains the account’s resource limits, privileges, features, and [package extensions](https://api.docs.cpanel.net/guides/guide-to-package-extensions/). The system stores a file for each cPanel user in the `/var/cpanel/users` directory, under the user’s `username`.

##### Cron Job

A task that the system runs at a scheduled interval. The tasks exist in the `crontab` Unix configuration file.

-   cPanel users can manage cron jobs with cPanel’s [_Cron Jobs_](https://docs.cpanel.net/cpanel/advanced/cron-jobs) interface (_cPanel >> Home >> Advanced >> Cron Jobs_).
-   Server administrators can manage cron jobs with WHM’s [_Configure cPanel Cron Jobs_](https://docs.cpanel.net/whm/server-configuration/configure-cpanel-cron-jobs) interface (_WHM >> Home >> Server Configuration >> Configure cPanel Cron Jobs_).

##### crond or cron

The cron daemon manages cron job scheduling. In Red Hat® systems, like AlmaLinux OS, CentOS, and CloudLinux™, `crond` is the daemon’s name. In Debian® systems, like Ubuntu®, the daemon’s name is `cron`.

You can manage this service daemon from WHM’s [_Service Manager_](https://docs.cpanel.net/whm/service-configuration/service-manager/) interface (_WHM >> Home >> Service Configuration >> Service Manager_).

In cPanel & WHM, the `restartsrv` script’s `crond` service manages both the `crond` and `cron` daemons in their respective systems. For more information, read our [The `restartsrv` script](https://docs.cpanel.net/whm/scripts/the-restartsrv-script) documentation.

##### Cross-Site Request Forgery Attack (XSRF or CSRF)

[A type of malicious attack](https://docs.cpanel.net/knowledge-base/security/basic-security-concepts) that forces a user to execute unauthorized commands, usually through a link, to exploit a trusted website.

-   To help prevent these attacks, cPanel & WHM requires every request to contain a unique per-session security token.
-   One-click attacks or session riding are common synonyms for this term.

##### CURRENT

One of cPanel & WHM’s [release tiers](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#release-tiers). We have tested and verified versions on this tier, but they may not contain all of the proposed functionality of a release.

More:

For more information, read our [Product Versions and the Release Process](https://docs.cpanel.net/knowledge-base/cpanel-product/product-versions-and-the-release-process) documentation.

## D

##### Daemon

A computer program that runs as a background process. The user **cannot** view or directly control this process.

More:

For more information, read our [The cPanel & WHM Service Daemons](https://docs.cpanel.net/knowledge-base/cpanel-product/the-cpanel-service-daemons) documentation.

##### Dangling Symlink

A symbolic link that refers to a pathname that doesn’t exist. For example, a symbolic link could point to a file that doesn’t exist.

##### Data Center

A facility that houses servers. A data center is generally a safe place to keep a server because it typically includes backup power supplies, multiple communication connections, and environmental controls.

##### Dedistribution

The process of moving some or all of a [distributed cPanel account](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#distributed-cpanel-account)’s functionality from a [child node](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#child-node) back to the [parent node](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#parent-node). For example, returning a cPanel account’s mail functionality from a [Mail Node](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#server-profile) child node to the parent node.

##### Default Address (cPanel Account Default Address)

Note:

This address is **not** the same as a domain’s default address, which catches mail for a specific domain after you configure it.

The email address to which cPanel & WHM routes any email messages to nonexistent email accounts or other invalid recipients on your cPanel account. You can check your cPanel account’s default address inbox in cPanel’s [_Manage Email Accounts_](https://docs.cpanel.net/cpanel/email/manage-email-accounts) interface (_cPanel >> Home >> Email >> Manage Email Accounts_).

##### Deprecated

A term that cPanel, L.L.C. uses to describe a feature that we [no longer support or will remove](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-deprecation-plan) in an upcoming release.

##### Dictionary Attack

A method in which a malicious user tries to guess a password with words from a dictionary.

-   This attack is similar to a [brute force attack](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#brute-force).
-   To help prevent this attack type, enable the _Dictionary attack protection_ setting in WHM’s [_Exim Configuration Manager_](https://docs.cpanel.net/whm/service-configuration/exim-configuration-manager) interface (_WHM >> Home >> Service Configuration >> Exim Configuration Manager_).

##### Digital Signature Algorithm (DSA)

A method that you can use to generate public and private keys for the signing of data.

##### Directory Harvest Attack (DHA)

A [brute force attack](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#brute-force) technique. Spammers attempt to find valid email addresses on a server through guesswork and various permutations of common addresses. WHM includes [cPHulk](https://docs.cpanel.net/whm/security-center/cphulk-brute-force-protection/), a protection system that lets you lock out brute force attackers after a specified number of failed attempts.

##### Disk Space Quota

A limit that hosting providers place on the amount of disk space that an account may use.

-   Website owners can locate their usage data in cPanel’s [_Disk Usage_](https://docs.cpanel.net/cpanel/files/disk-usage) interface (_cPanel >> Home >> Files >> Disk Usage_).
-   Server administrators manage users’ disk space quotas in WHM’s [_Quota Modification_](https://docs.cpanel.net/whm/account-functions/quota-modification) interface (_WHM >> Home >> Account Functions >> Quota Modification_).

##### Distributed cPanel Account

A cPanel account that exists on two or more [linked nodes](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#linked-node).

##### DNS Zone

The administrative part of the [Domain Name System (DNS)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#dns). This directs internet traffic to the correct location. For example, `example.com` is a DNS zone with servers that direct its internet traffic. You can add DNS zones to the server in WHM’s [_Add a DNS Zone_](https://docs.cpanel.net/whm/dns-functions/add-a-dns-zone) interface (_WHM >> Home >> DNS Functions >> Add a DNS Zone_).

##### dnsadmin

A program that manages DNS services and DNS clustering.

-   [DNS clusters](https://docs.cpanel.net/knowledge-base/dnsonly/guide-to-dns-cluster-configurations) use dnsadmin.
-   Third-party integrators can create [custom dnsadmin plugins](https://api.docs.cpanel.net/guides/guide-to-custom-dnsadmin-plugins/).

##### Document root

The directory that [contains a domain’s publicly-available files](https://docs.cpanel.net/cpanel/domains/domains).

-   Your primary domain’s document root typically defaults to the `public_html` directory.
-   The document root directories of any addon domains or subdomains depend on your server’s settings.

##### Domain Control Validation

A [CA](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ca) uses Domain Control Validation (DCV) to verify that a certificate requester owns the domain before issuing the certificate. The CA can use one of the three following DCV methods to verify ownership:

-   **Email** — Send a validation email to the administrative contact for the domain.
    
-   **DNS** — Check a special CNAME record for the domain in DNS.
    
-   **HTTP** — Check a hashed text file on the requester’s website.
    

##### Domain Name

The name that a site owner gives to a website, which appears in the website’s URL and email addresses.

-   Generally, domains use the `example.com` format, where `example` is the domain name and `com` is the [top-level domain](http://wikipedia.org/wiki/Top-level_domain).
-   You can add and manage domains in cPanel’s [_Domains_](https://docs.cpanel.net/cpanel/domains/domains) interface (_cPanel >> Home >> Domains >> Domains_).

##### Domain Forwarding (Redirect)

A technique that allows you or your users to automatically send visitors to a domain when they access another domain. For example, a user may reach `example.com` when they enter `example2.com`. You can set up and manage domain forwarding in WHM’s [_Setup/Edit Domain Forwarding_](https://docs.cpanel.net/whm/dns-functions/setup-edit-domain-forwarding) interface (_WHM >> Home >> DNS Functions >> Setup/Edit Domain Forwarding_).

##### Domain Name System (DNS)

The component of the internet that converts human-readable domain names (for example, `www.example.com`) into computer-readable IP addresses (for example, `93.184.216.34`).

-   A DNS record can specify which mail servers exist for a given domain. These records also identify which nameservers contain authoritative information about your domains and services.
-   The nameserver software on your server manages nameserver records. cPanel & WHM offers BIND and PowerDNS as nameserver software options.
    
    Warning:
    
    We removed the MyDNS and NSD nameservers in cPanel & WHM version 106 and later. We **strongly** recommend that you migrate to PowerDNS. For more information, read our [cPanel Deprecation Plan](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-deprecation-plan).
    

##### Domain-Validated (DV) Certificate

A digital certificate for [SSL/TLS](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ssl) verification. The [certificate authority (CA)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ca) verifies that the applicant controls the DNS domain via email, phone, or other method.

-   These certificates are the **least** secure level of domain validation, since the CA does **not** attempt to verify who the domain owner actually is.
-   You can purchase and install DV certificates in cPanel’s [_SSL/TLS Wizard_](https://docs.cpanel.net/cpanel/security/ssl-tls-wizard) interface (_cPanel >> Home >> Security >> SSL/TLS Wizard_).

##### DomainKeys Identified Mail (DKIM)

An email authentication method which attempts to verify that a message actually came from the domain it appears to have originated from. You can enable DKIM in WHM’s [_Enable DKIM/SPF Globally_](https://docs.cpanel.net/whm/dns-functions/enable-dkim-spf-globally) interface (_WHM >> Home >> DNS Functions >> Enable DKIM/SPF Globally_).

##### Domain-based Message Authentication, Reporting, and Conformance (DMARC)

DMARC (Domain-based Message Authentication, Reporting & Conformance) is a technical specification to help reduce the potential for email-based abuse. A DMARC policy uses DNS to confirm that an email message uses a valid [DKIM](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#dkim) and [SPF](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#spf) record, and that the `From:` header matches those records.

-   Many large email networks require that you use a DMARC policy to help protect their users from spam email. To prevent email rejections or spam flags within these networks, your server must use a DMARC policy.
-   You can create and manage DMARC records in cPanel’s [_Zone Editor_](https://docs.cpanel.net/cpanel/domains/zone-editor) interface (_cPanel >> Home >> Domains >> Zone Editor_).

More:

For more information, read [dmarc.org’s documentation](http://dmarc.org/) and our [How to Keep your Email Out of the Spam Folder](https://docs.cpanel.net/knowledge-base/email/how-to-keep-your-email-out-of-the-spam-folder) documentation.

##### Dovecot

An [open-source mail server software](http://www.dovecot.org/) that has optimal security. You can configure your Dovecot mail server settings in WHM’s [_Mailserver Configuration_](https://docs.cpanel.net/whm/service-configuration/mailserver-configuration) interface (_WHM >> Home >> Service Configuration >> Mailserver Configuration_).

##### DNSOnly®

A version of cPanel & WHM that lets you run a dedicated physical nameserver. This version of cPanel & WHM is extremely minimal and **only** replicates DNS zones to your other servers.

More:

For more information, read our [cPanel DNSOnly](https://docs.cpanel.net/knowledge-base/dnsonly/cpanel-dnsonly/) documentation.

##### Dynamic DNS (DDNS) Domain

This type of domain simplifies access to a network that uses a dynamic IP address via a [webcall](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#webcall) URL. For example, a user can use this domain to access their home network, even when the IP address changes. For more information, read our [_Dynamic DNS_](https://docs.cpanel.net/cpanel/domains/dynamic-dns) feature documentation.

## E

##### EasyApache (EA)

A part of cPanel & WHM that installs, modifies, and validates your Apache web server, PHP, and other components.

More:

For more information, read our [EasyApache](https://docs.cpanel.net/ea4) documentation.

##### EDGE

One of cPanel & WHM’s [release tiers](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#release-tiers).

-   Versions on this tier have only had rudimentary testing and are subject to further modification.
-   We don’t recommend this tier for production servers.

More:

For more information, read our [Product Versions and the Release Process](https://docs.cpanel.net/knowledge-base/cpanel-product/product-versions-and-the-release-process) documentation.

##### Elliptic Curve Digital Signature Algorithm (ECDSA)

A variant of [Digital Signature Algorithm](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#DSA) that uses [elliptic-curve cryptography (ECC)](https://en.wikipedia.org/wiki/Elliptic-curve_cryptography). ECDSA provides equivalent security to RSA keys using smaller key sizes. As a result, ECDSA keys generate smaller certificates. Smaller certificates can result in faster connections and website loading times.

##### Email Deliverability

Whether a system can deliver email to recipients. Email deliverability often gauges whether email campaigns will succeed, and it can help you identify mail-related DNS problems. You can view email deliverability information in cPanel’s [_Email Deliverability_](https://docs.cpanel.net/cpanel/email/email-deliverability-in-cpanel) interface (_cPanel >> Home >> Email >> Email Deliverability_).

##### End of Life (EOL)

The stage of software’s lifecycle when the author no longer provides security updates or bug fixes. When a version of cPanel, L.L.C.’s software, an operating system, or third-party software that ships with cPanel & WHM reaches EOL, we **can’t** guarantee support for that version of software.

More:

For more information, read our [Third-Party Software End of Life Policy](https://docs.cpanel.net/knowledge-base/third-party/third-party-software-end-of-life-policy) documentation.

##### Environment Variables

Values that advanced administrators place within specific files on the server to change the behavior of [Apache](https://docs.cpanel.net/ea4), [PHP](https://docs.cpanel.net/cpanel/software/application-manager), and other systems.

Note:

Third-party integrators can use [cPanel environment variables](https://api.docs.cpanel.net/guides/guide-to-cpanel-variables/) in the LiveAPI system and `dynamicui.conf` files.

##### Error Pages

Pages that [display warning messages](https://docs.cpanel.net/knowledge-base/web-services/http-error-codes-and-quick-fixes) when visitors encounter problems while they try to access your site. You can customize these pages in cPanel’s [_Error Pages_](https://docs.cpanel.net/cpanel/advanced/error-pages) interface (_cPanel >> Home >> Advanced >> Error Pages_).

##### Exim

A [free mail transfer agent](http://www.exim.org/) software that is highly flexible and easily configurable. You can modify your Exim configuration in WHM’s [_Exim Configuration Manager_](https://docs.cpanel.net/whm/service-configuration/exim-configuration-manager) interface (_WHM >> Home >> Service Configuration >> Exim Configuration Manager_).

##### EXPERIMENTAL

An [unstable feature or setting](https://docs.cpanel.net/changelogs) that may cause unintended consequences. Exercise **extreme caution** if you enable an _EXPERIMENTAL_ feature or setting.

Important:

-   These features may **not** function with other features or settings.
-   These features are **not** currently effective security controls.
-   _EXPERIMENTAL_ features **don’t** qualify for our security bounty.

##### Extended Fourth Filesystem (ext4)

A journaled filesystem that Linux servers often use. `ext4` is the successor to the `ext3` filesystem. We [require](https://docs.cpanel.net/installation-guide) `ext4` for all cPanel & WHM installations.

##### Extended HELO (EHLO)

**See also:** [HELO](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#helo)

An [Extended Simple Mail Transfer Protocol (ESMTP)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#esmtp) command that a mail server or client sends to identify itself when it connects with another mail server.

-   This command initiates the process of sending an email and follows with the server sending its domain name.
-   The `esmtp` command notifies the receiving server or client that the sending server supports ESMTP extensions.

##### Extended SMTP (ESMTP)

An extension of the original [Simple Mail Transfer Protocol (SMTP)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#smtp)’s protocols. ESMTP sends an [EHLO](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ehlo) request to a mail server or client to identify the server’s supported protocol. The server returns a list of its available ESMTP commands.

##### Extended Validation (EV) Certificate

A digital certificate for [SSL/TLS](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ssl) verification. The [certificate authority (CA)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ca) verifies that the applicant controls the DNS domain with a comprehensive identity validation process.

-   These certificates enable HTTPS on a user’s web browser address bar and state the name of the verified owner.
-   These certificates are the most secure level of domain validation.
-   You can purchase and install certificates in cPanel’s [_SSL/TLS Wizard_](https://docs.cpanel.net/cpanel/security/ssl-tls-wizard) interface (_cPanel >> Home >> Security >> SSL/TLS Wizard_).

##### External Authentication

This feature allows system administrators to grant users the ability to access their cPanel accounts with an external account provider, such as a cPanel ID or with a Google® account.

-   Third-party developers can use [External Authentication modules](https://api.docs.cpanel.net/guides/guide-to-external-authentication/) to authenticate with OpenID Connect-compliant identity providers.
-   You can configure External Authentication in WHM’s [_Manage External Authentications_](https://docs.cpanel.net/whm/security-center/manage-external-authentications) interface (_WHM >> Home >> Security Center >> Manage External Authentication_).

## F

##### Feature

See [Bug](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#bug).

##### File Transfer Protocol (FTP)

A method that you can use to transfer files from one computer to another. cPanel & WHM includes an FTP server that website owners can configure.

-   You **must** install an FTP client (for example, FileZilla and Cyberduck) on the local computer in order to send files to and receive files from the FTP server.
-   You can select an FTP server in WHM’s [_FTP Server Selection_](https://docs.cpanel.net/whm/service-configuration/ftp-server-selection) interface (_WHM >> Home >> Service Configuration >> FTP Server Selection_) and configure it in WHM’s [_FTP Server Configuration_](https://docs.cpanel.net/whm/service-configuration/ftp-server-configuration) interface (_WHM >> Home >> Service Configuration >> FTP Server Configuration_).
-   You can create and manage FTP accounts in cPanel’s [_FTP Accounts_](https://docs.cpanel.net/cpanel/files/ftp-accounts) interface (_cPanel >> Home >> Files >> FTP Accounts_).

##### Filesystem

The system that the operating system uses to manage files and directories. If your server uses multiple partitions, each partition might use a different filesystem.

##### Filter

In cPanel, a tool that processes email based on your preferences. For example, a filter can automatically discard spam or save mail from a specified sender to its own folder.

-   You can apply filters to the main email account on a domain with the [_Global Email Filters_](https://docs.cpanel.net/cpanel/email/global-email-filters) interface (_cPanel >> Home >> Email >> Global Email Filters_).
-   You can customize filters for each individual account with the [_Email Filters_](https://docs.cpanel.net/cpanel/email/email-filters) interface (_cPanel >> Home >> Email >> Email Filters_).
-   WHM users can set up more types of filters, like [Exim filters](https://docs.cpanel.net/knowledge-base/email/how-to-customize-the-exim-system-filter-file).

##### Firewall

A security application that protects servers from intrusion by hackers. For example, CSF is a popular firewall for Linux systems. Linux systems also include a built-in firewall, [iptables](https://www.netfilter.org/projects/iptables/index.html).

More:

For more information, read our [How to Configure Your Firewall for cPanel & WHM Services](https://docs.cpanel.net/knowledge-base/general-systems-administration/how-to-configure-your-firewall-for-cpanel-services) documentation.

##### firewalld

A firewall tool for Linux operating systems. It dynamically manages network and firewall zones and defines trust levels.

More:

For more information, visit the [firewalld](https://firewalld.org/) website.

##### Forceful Reboot

One of the two methods that you can use to restart your server. This method forces the server to restart regardless of any errors that it encounters.

-   **Only** use a forceful reboot if you **cannot** [reboot gracefully](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#graceful-reboot), because it can result in data loss.
-   You can perform forceful and graceful reboots [in the WHM interface](https://docs.cpanel.net/whm/system-reboot/system-reboot/).

##### Forwarder

A tool that lets you forward a copy of every email message that you receive to another address. When a forwarder exists, you still receive mail at the original recipient address.

-   If you create a forwarder **before** you create the original address, the system will forward messages to the end address but **not** to the original address, because it does not exist.
-   You can create and manage forwarders in cPanel’s [_Forwarders_](https://docs.cpanel.net/cpanel/email/forwarders) interface (_cPanel >> Home >> Email >> Forwarders_).

##### Fully Qualified Domain Name (FQDN)

A name that uniquely defines a domain’s location.

-   The FQDN generally uses the `host.example.com.` format, **with** a trailing dot. However, for cPanel & WHM, a final dot is unnecessary, but the domain name must contain **at least** two dots.
-   You **must** write FQDNs in lowercase letters.

## G

##### Gem (RubyGem)

A piece of software in the Ruby language. These exist in the RubyGems repository.

More:

For more information, visit the [RubyGems](https://rubygems.org/) documentation.

##### Generators (Web Statistics Generators)

Software applications that compile log statistics for your web server. For example, they can report the amount of bandwidth that each domain has transferred.

-   cPanel & WHM includes three statistics generators:
    -   [Analog](http://www.c-amie.co.uk/analog/)
    -   [AWStats](https://awstats.sourceforge.io/)
    -   [Webalizer](http://www.webalizer.org/)
-   Server administrators can manage their server’s web statistics and software in WHM’s [_Statistics Software Configuration_](https://docs.cpanel.net/whm/server-configuration/statistics-software-configuration) interface (_WHM >> Home >> Server Configuration >> Statistics Software Configuration_).

##### Globally Unique Identifier (GUID)

A value that the system uses to identify a resource, similar to [UUID](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#uuid). UUID is the more common identifier while Microsoft products are the main users of GUID.

##### GNU Privacy Guard (GnuPG)

A [suite of tools](http://www.gnupg.org/) that you can use for data encryption and signing. Generally, you will use these tools for signing emails. You can create and manage GnuPG keys in cPanel’s [_Encryption_](https://docs.cpanel.net/cpanel/email/encryption) interface (_cPanel >> Home >> Email >> Encryption_).

##### Graceful Reboot

This method stores new system information before the server shuts down and is the preferred way to restart your server.

-   This is the opposite of a [forceful reboot](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#forceful-reboot).
-   You can perform forceful and graceful reboots [in the WHM interface](https://docs.cpanel.net/whm/system-reboot/system-reboot/).

##### Greylisting

**See also:** [Blacklist](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#blacklist), [Whitelist](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#whitelist)

A service that protects a server against unwanted email or spam. When you enable greylisting in WHM’s [_Greylisting_](https://docs.cpanel.net/whm/email/greylisting) interface (_WHM >> Home >> Email >> Greylisting_), the mail server temporarily rejects any email from a sender that the server does not recognize.

-   If the email is legitimate, the originating server attempts to send it again after a delay.
-   After sufficient time passes, the server accepts the email.

##### gzip

A program that compresses files for disk space conservation, minimizes transfer times, and makes the transfer of multiple files easier.

-   The compressed files use the `.gz` file extension.
-   Unix and Linux systems often use gzip with the [tar](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#tar) command to create a tarball file, which uses the `.tar.gz` file extension.
-   You can set the system’s gzip compression level in WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_).

## H

##### .htaccess

A file that resides in a specific directory and contains the directory’s configuration information. The `.htaccess` file may also contain authentication instructions.

##### .htpasswd

A file that resides in a specific directory along with an `.htaccess` file. This file contains encrypted password information when the owner has set up authentication for the directory.

Note:

You can use cPanel’s [_Directory Privacy_](https://docs.cpanel.net/cpanel/files/directory-privacy) interface (_cPanel >> Home >> Files >> Directory Privacy_) to configure directory privacy.

##### Ham

Legitimate messages that the system marks as spam. Use the _Not junk_ button in Roundcube to train the system to recognize ham.

##### HELO

**See also:** [EHLO](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ehlo)

A [Simple Mail Transfer Protocol (SMTP)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#smtp) command that a mail server or client sends to identify itself when it connects with another mail server. This command initiates the process of sending of an email and follows with the server sending its domain name. Older mail clients use this command because these clients don’t require service extensions.

##### Home Directory

A cPanel account’s highest-level directory, which contains all of the files and directories that the account’s websites use. Visitors **cannot** view the files in a home directory unless they reside in the `public_html` directory or one of its subdirectories.

##### Horde Webmail

A [webmail client](https://www.horde.org/apps/webmail) in cPanel & WHM that allows users to check email through a browser.

-   You can use Horde in cPanel’s [_Webmail_](https://docs.cpanel.net/webmail) interface.
-   cPanel & WHM includes [custom Horde data behavior](https://docs.cpanel.net/knowledge-base/webmail/guide-to-horde-data-behavior).

##### Hostname

The unique, human-recognizable name for a server across the internet (for example, `host.example.com`).

-   System administrators can specify or change a server’s hostname with WHM’s [_Change Hostname_](https://docs.cpanel.net/whm/networking-setup/change-hostname) interface (_WHM >> Home >> Networking Setup >> Change Hostname_).
-   The server hostname is distinct from your [domain name](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#domain-name).

##### Hotlink (Inline Link)

A direct link that embeds a file, such as an image or video, from your site into another website.

-   When another site embeds your files, it uses **your** bandwidth to serve those files.
-   You can prevent hotlinking in cPanel’s [_Hotlink Protection_](https://docs.cpanel.net/cpanel/security/hotlink-protection) interface (_cPanel >> Home >> Security >> Hotlink Protection_).

##### httpd.conf

The configuration file for the [Apache web server](http://httpd.apache.org/docs/2.4/configuring.html).

## I

##### ICQ

An instant messaging service that you can use to receive updates from your server. You can configure these notifications in cPanel’s [_Contact Manager_](https://docs.cpanel.net/whm/server-contacts/contact-manager) interface (_WHM >> Home >> Server Contacts >> Contact Manager_).

More:

For more information, visit the [ICQ website](http://www.icq.com/).

##### Identity Provider

A third-party authority (for example, OpenID Connect) that offers external authentication to log in to other sites or services.

-   Third-party developers can use [External Authentication modules](https://api.docs.cpanel.net/guides/guide-to-external-authentication/) to authenticate with OpenID Connect-compliant identity providers.
-   You can configure External Authentication in WHM’s [_Manage External Authentications_](https://docs.cpanel.net/whm/security-center/manage-external-authentications) interface (_WHM >> Home >> Security Center >> Manage External Authentications_).

##### Index Page

The default page, generally `index.html`, `index.htm`, or `index.php`, that visitors view when they access a website directory. If **no** index page exists for the specified directory, the visitor sees a list of files in that directory, unless you disable indexing in cPanel’s [_Indexes_](https://docs.cpanel.net/cpanel/advanced/indexes) interface (_cPanel >> Home >> Advanced >> Indexes_).

##### Internet Message Access Protocol (IMAP)

One of the two most widely-used email transfer methods along with [POP3](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#pop3). IMAP synchronizes email account information with the mail server on a regular basis. If a user logs in to multiple computers to check email, IMAP allows the user to see which messages they have viewed, replied to, or forwarded.

More:

For more information, read our [IMAP vs. POP3](https://docs.cpanel.net/knowledge-base/email/imap-versus-pop3) documentation.

##### Internet Protocol (IP)

The main protocol that relays information across the internet. This protocol uses IP addresses to deliver information from one host to another. cPanel & WHM supports two versions of Internet Protocol:

-   **IPv4** is an older version that uses 32-bit IP addresses. This version has limited availability, but is the more popular and accessible.
    
-   [**IPv6**](https://docs.cpanel.net/knowledge-base/general-systems-administration/guide-to-ipv6) is a newer version that uses 128-bit IP addresses. This version has vast availability of addresses, but requires an IPv6-enabled network and server.
    
    Warning:
    
    Due to networking requirements, you **cannot** run an IPv6-only cPanel & WHM server. You **must** have at least one IPv4 address.
    

##### Internet Protocol (IP) Address

A number that identifies a computer on a network, which makes it possible for other computers to find and communicate with it. You can add new IP addresses to your IP address pool in WHM’s [_Add a New IP Address_](https://docs.cpanel.net/whm/ip-functions/add-a-new-ip-address) interface (_WHM >> Home >> IP Functions >> Add a New IP Address_).

##### Internet Relay Chat (IRC)

An application layer protocol of real-time online communication that allows both group discussion and one-to-one messaging, as well as data transfer. Third-party developers can [create custom modules](https://api.docs.cpanel.net/guides/guide-to-custom-service-notifications/) to send notifications to IRC and other services.

##### IonCube®

A loader that, when enabled, can load PHP for cPanel & WHM.

More:

For more information, visit the [IonCube website](http://www.ioncube.com/).

##### iptables

A user space utility program that allows server administrators to configure the Linux kernel firewall data tables.

More:

For more information, visit the [iptables website](https://www.netfilter.org/projects/iptables/index.html) or our [How to Configure Your Firewall for cPanel & WHM Services](https://docs.cpanel.net/knowledge-base/general-systems-administration/how-to-configure-your-firewall-for-cpanel-services) documentation.

## J

##### Jailed Shell

A [CLI](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#cli) configuration that restricts users’ access rights. The system limits shell sessions to a filesystem that does not contain the home directories of other cPanel users on the system.

-   cPanel & WHM [uses VirtFS](https://docs.cpanel.net/knowledge-base/accounts/virtfs-jailed-shell) to provide jailshell access.
-   You can [create custom jailed shell mounts](https://docs.cpanel.net/knowledge-base/general-systems-administration/how-to-create-custom-jailed-shell-mounts) to grant users additional access.

##### Java

A computer programming language that many web applications use. These small applications, which run within the context of a browser, are called applets.

More:

For more information, read our [How to Deploy Java Applications](https://docs.cpanel.net/knowledge-base/web-services/how-to-deploy-java-applications) documentation.

##### JavaScript Object Notation (JSON)

A file format that uses human-readable text to store and exchange data. JSON contains data objects in attribute-value pairs and array data types.

-   cPanel & WHM uses JSON for API output and some internal data storage.
-   You can use several basic variables to [filter](https://api.docs.cpanel.net/whm/filter-output/) or [sort](https://api.docs.cpanel.net/whm/sort-output/) API output in JSON.

## K

##### Kernel

The central component of a server’s operating system. The kernel manages communications between the user and the server’s resources, such as its processor and the memory.

##### Key

In cryptography, keys encrypt or decrypt information.

-   Keys are an important part of encryption and security, and you should guard them appropriately.
-   Using cPanel & WHM usually includes working with, for example, SSH keys, DNSSEC keys, and various types of cPanel & WHM-specific access keys.

##### Known Netblock

A class C address space that contains an address from which a user has successfully logged in. You can configure settings for known netblocks in WHM’s [_Greylisting_](https://docs.cpanel.net/whm/email/greylisting) interface (_WHM >> Home >> Email >> Greylisting_).

## L

##### LAMP

An acronym for the combination of Linux, Apache, MySQL, and PHP. This is a common combination of software for web servers.

More:

For more information, read our [Installation Guide](https://docs.cpanel.net/installation-guide).

##### Leech

A visitor who uses another person’s password to access a restricted area of a website. cPanel & WHM lets you redirect likely offenders or disable accounts with compromised passwords in order to prevent leeches. To do this, use cPanel’s [_Leech Protection_](https://docs.cpanel.net/cpanel/security/leech-protection) interface (_cPanel >> Home >> Security >> Leech Protection_).

##### Legacy

A term for an old software program or computer system that is still in use, or for a previous version of a cPanel & WHM feature.

##### Linked Node

A node that a server administrator designates to either assign tasks to or receive tasks from another node. For example, a [parent node](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#parent-node) may assign all mail tasks for a cPanel account to a [child node](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#child-node).

##### Linux®

A Unix-based, open-source operating system.

More:

For more information, read our [Installation Guide](https://docs.cpanel.net/installation-guide).

##### Loader

The part of a system that loads a program. Use WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_) to select the loader that cPanel & WHM uses for PHP.

##### Local Host

The computer that you currently work on.

##### Local User

A user who accesses a service on the machine on which the service exists, as opposed to remotely.

##### Log

A file that the server automatically creates, which records activities that specific programs and applications on the server perform. For example, error logs list the errors that visitors have encountered on websites that Apache generates.

##### Log Files

Files that contain status messages, warnings, and other real-time information about your server and its processes. cPanel & WHM includes many [log files](https://docs.cpanel.net/knowledge-base/cpanel-product/the-cpanel-log-files).

##### Long-Term Support (LTS)

One of cPanel & WHM’s [release tiers](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#release-tiers). cPanel, L.L.C. supports this version for a period of one year before designating the next LTS version.

More:

For more information, read our [Product Versions and the Release Process](https://docs.cpanel.net/knowledge-base/cpanel-product/product-versions-and-the-release-process) documentation.

## M

##### Mail Exchanger (MX) Entry

A record that specifies where the system sends email for a domain, because it contains the mail server’s IP address.

-   When you use an email scanning service or custom mail delivery, the server administrator may need to change the MX record for a domain in WHM’s [_Email Routing Configuration_](https://docs.cpanel.net/whm/dns-functions/email-routing-configuration) interface (_WHM >> Home >> DNS Functions >> Email Routing Configuration_).
-   cPanel users can configure MX records in cPanel’s [_Email Routing_](https://docs.cpanel.net/cpanel/email/email-routing) interface (_cPanel >> Home >> Email >> Email Routing_).

##### Mail Server Name Indication (Mail SNI)

Allows clients to request a specific hostname at the beginning of the [handshake](https://en.wikipedia.org/wiki/Handshaking) process. In our documentation, SNI refers to this protocol in relation to Apache, while Mail SNI refers to this protocol in relation to Exim.

More:

For more information, read our [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl) documentation.

##### Mail Transfer Agent (MTA)

A program that sends and receives email messages. [Exim](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#exim) is an MTA.

##### maildir

A format that stores email as individual messages with unique filenames in flat files. You can manage `maildir` with WHM’s [_Mailbox Conversion_](https://docs.cpanel.net/whm/email/mailbox-conversion) interface (_WHM >> Home >> Email >> Mailbox Conversion_).

##### Mailing List

A list of email addresses that mailing list members can use to communicate. Alternatively, you can use a mailing list to send email messages to a large group of people.

-   cPanel & WHM uses the Mailman program for mailing list software.
-   You can use cPanel’s [_Mailing Lists_](https://docs.cpanel.net/cpanel/email/mailing-lists) interface (_cPanel >> Home >> Email >> Mailing Lists_) to create and manage mailing lists.

##### Mailman

[Mailing list](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#mailinglist) software that sends email messages to a group of specified email addresses.

More:

For more information, visit the [Mailman](http://www.list.org/) website.

##### Manage2

A cPanel, L.L.C. website that lets you perform license-related tasks. Hosting providers log in to [Manage2](https://docs.cpanel.net/manage2) to add, update, or remove cPanel product licenses, or to manage and pay invoices from cPanel, L.L.C.

##### MariaDB®

A relational database management tool and server, as well as the type of database it manages. Databases are an integral part of web applications, such as bulletin boards and blogs.

-   cPanel & WHM provides an integrated [MariaDB](https://mariadb.org/) installation and database editing tools.
-   You can upgrade the server’s MariaDB version in WHM’s [_MySQL or MariaDB Upgrade_](https://docs.cpanel.net/whm/sql-services/mysql-or-mariadb-upgrade) interface (_WHM >> Home >> SQL Services >> MySQL or MariaDB Upgrade_).

##### mod\_userdir

An Apache module that allows visitors to enter your hostname, a tilde (`~`), and the website owner’s username in order to view a website (for example, `http://host.example.com/~username`).

Important:

We recommend that you **disable** the `mod_userdir` module in WHM’s [_Apache mod\_userdir Tweak_](https://docs.cpanel.net/whm/security-center/apache-mod_userdir-tweak) interface (_WHM >> Home >> Security Center >> Apache mod\_userdir Tweak_) because the system accounts for bandwidth per-host rather than per-user.

##### Modulus

In encryption algorithms like [RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem)), the modulus is the number that both the private and public keys have in common. You can view a key’s modulus in WHM’s [_SSL Storage Manager_](https://docs.cpanel.net/whm/ssl-tls/ssl-storage-manager) interface (_WHM >> Home >> SSL/TLS >> SSL Storage Manager_).

##### Mount

In general computing, to mount a file system is to make it accessible to users. In a Unix or Linux operating system, you can use the mount command to tell the operating system that a file system or device is ready to use **and** to affix that system or device to a certain directory.

More:

For more information, read our [Installation Guide](https://docs.cpanel.net/installation-guide).

##### Multipurpose Internet Mail Extensions (MIME) Type

A component of a file that identifies the file type, so that browsers handle it correctly.

-   cPanel & WHM lets you specify which application to use to open files with a specific extension.
-   You can add and manage MIME types in cPanel’s [_MIME Types_](https://docs.cpanel.net/cpanel/advanced/mime-types) interface (_cPanel >> Home >> Advanced >> MIME Types_).

##### MySQL®

A relational database management tool and server, as well as the type of database it manages. Databases are an integral part of web applications, such as bulletin boards and blogs.

-   cPanel & WHM provides an integrated MySQL installation and database editing tools.
-   You can upgrade the server’s MySQL version in WHM’s [_MySQL or MariaDB Upgrade_](https://docs.cpanel.net/whm/sql-services/mysql-or-mariadb-upgrade) interface (_WHM >> Home >> SQL Services >> MySQL or MariaDB Upgrade_).

## N

##### Nameserver

A physical computer that contains a list of domain names and their IP addresses. These computers allow visitors to access a domain through its IP address. Nameserver software gathers data about domains over time. Because of this, changes to DNS records may require 48 hours or more to reach all of the nameservers on the internet ([propagate](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#propagation)). Several types of nameserver exist.

-   **Local** — Local nameservers are authoritative nameservers. They reside on the same server that hosts the nameserver’s cPanel accounts.
    
-   **Clustered** — Clustered nameservers exist in a collection of nameservers that all share information and authoritative nameserver status. These nameservers prevent down time. If one server fails, additional servers are available to perform the necessary functions.
    
-   **Private or Custom** — This type of nameserver is a custom-branded or vanity alternative name for the authoritative nameserver.
    
-   **Remote** — Remote nameservers are authoritative nameservers that a separate server hosts.
    

More:

For more information, read our [How to Set Up Nameservers in a cPanel & WHM Environment](https://docs.cpanel.net/knowledge-base/dns/how-to-set-up-nameservers-in-a-cpanel-environment) documentation.

##### Network Address Translation (NAT)

The remapping of one IP address space to another by modifying the network address information of packets’ IP headers while in transit across a router. This method allows for the use of a single IP address on an entire private network.

More:

For more information, read our [1:1 NAT](https://docs.cpanel.net/knowledge-base/general-systems-administration/1-1-nat) documentation.

##### Network File System (NFS)

Allows users to access remote files as though the accessed storage was part of the local machine.

##### nobody

**See also:** [UID](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#uid)

A Unix or Linux system account with the UID of `99`. This system account executes [CGI](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#cgi) and [PHP](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#php) scripts if [suEXEC](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#suexec) is disabled.

## O

##### Open Relay

A mail server configuration that allows anyone to send mail through the server. You can enable or disable this configuration in the _Mail_ section of WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_).

Warning:

For security reasons, we **strongly** recommend that you **don’t** allow your server to operate as an open relay.

##### open\_basedir

A feature that uses PHP to deny users the ability to open files that are outside of their home directories. You can modify this feature in the _Editor Mode_ section of WHM’s [_MultiPHP INI Editor_](https://docs.cpanel.net/whm/software/multiphp-ini-editor) interface (_WHM >> Home >> Software >> MultiPHP INI Editor_).

##### OpenID® Connect (OIDC)

A standard for third-party authentication. cPanel & WHM’s [External Authentication](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#external-authentication) feature uses OpenID Connect to communicate with third-party authentication providers.

-   Third-party developers can use [External Authentication modules](https://api.docs.cpanel.net/guides/guide-to-external-authentication/) to authenticate with OpenID Connect-compliant identity providers.
-   You can configure External Authentication in WHM’s [_Manage External Authentications_](https://docs.cpanel.net/whm/security-center/manage-external-authentications) interface (_WHM >> Home >> Security Center >> Manage External Authentication_).

More:

For more information, visit the [OpenID Connect website](https://openid.net/connect/).

##### Operating System (OS)

The background software that runs all of the other software applications on your system. The OS is a required part of any server or computer. cPanel & WHM supports specific versions of the [CentOS](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#centos), [Red Hat Enterprise Linux (RHEL)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#rhel), [AlmaLinux OS](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#almalinux), and [CloudLinux™](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#cloudlinux) operating systems.

More:

For more information, read our [Installation Guide](https://docs.cpanel.net/installation-guide).

##### Option Module (optmod)

An Apache configuration option that adds features to the [EasyApache](https://docs.cpanel.net/ea4) system.

##### Organizational Validation (OV) Certificate

A digital certificate used for [SSL/TLS](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ssl) verification. The [certificate authority (CA)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ca) verifies that the applicant controls the DNS domain through a vetting process. These certificates enable HTTPS on a user’s web browser address bar and state that the site is secure with a Secure Site Seal.

-   These certificates are more secure than a [DV certificate](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#domain-validated-ssl).
-   You can purchase and install certificates in cPanel’s [_SSL/TLS Wizard_](https://docs.cpanel.net/cpanel/security/ssl-tls-wizard) interface (_cPanel >> Home >> Security >> SSL/TLS Wizard_).

## P

##### Package

A package may refer to:

1.  The set of resource limits that hosting providers assign to a user’s account. System administrators can create, edit, and delete packages in WHM’s [_Packages_](https://docs.cpanel.net/whm/packages) section.
2.  A collection of software that publishers bundle together for distribution and installation. cPanel, L.L.C. provides various third-party software, such as [FTP](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ftp) and [MySQL](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#mysql), as [packages](https://docs.cpanel.net/knowledge-base/rpm-versions) that the `rpm.versions` system manages.

##### Parent Node

An authoritative [linked node](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#linked-node) that assigns tasks to one or more [child nodes](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#child-node).

##### Parked Domain

A second domain that points to a primary domain. For example, both `http://www.cpanel.net/` and `http://www.cpanel.com/` point to the same website, because `cpanel.com` is a parked domain for `cpanel.net`.

-   This makes your website available from another domain name.
    
-   In cPanel, we refer to parked domains as [aliases](https://docs.cpanel.net/cpanel/domains/aliases).
    

##### Passive Mode (PASV)

A mode for FTP connections that initiate connections from the client side. You can use this mode if a user has problems when they attempt to connect to an FTP server through a firewall.

More:

For more information, read our [How to Enable FTP Passive Mode](https://docs.cpanel.net/knowledge-base/ftp/how-to-enable-ftp-passive-mode) documentation.

##### Passive OS Fingerprinting (p0f)

A service that reports the visitor’s operating system and other information for email notifications. This information will help you quickly identify visitors who trigger events that cause alerts.

More:

For more information, read our [The cPanel & WHM Service Daemons](https://docs.cpanel.net/knowledge-base/cpanel-product/the-cpanel-service-daemons) documentation.

##### Perl

A programming language for web applications.

-   Perl applications are commonly `.pl`, `.pm`, and `.cgi` files and may require [Perl modules](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#perl-modules).
-   Third-party developers can [write custom code in Perl](https://api.docs.cpanel.net/guides/guide-to-perl/).

##### Perl Module

A component of software in the Perl programming language that developers commonly reuse. For example, a developer can use a calendar module in a program so that they don’t need to write a new set of functions to display calendars. You can install Perl modules in either of the following interfaces:

-   cPanel’s [_Perl Modules_](https://docs.cpanel.net/cpanel/software/perl-modules) interface (_cPanel >> Home >> Software >> Perl Modules_)
-   WHM’s [_Install a Perl Module_](https://docs.cpanel.net/whm/software/install-a-perl-module) interface (_WHM >> Home >> Software >> Install a Perl Module_)

##### PHP

A computer scripting language that many web-based applications use. Some PHP applications require [PEAR packages](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#pear).

More:

For more information, read our [Introduction to PHP](https://docs.cpanel.net/ea4/php/introduction-to-php) documentation.

##### PHP Extension and Application Repository (PEAR)

A repository of PHP code. cPanel lets you search for and install PEAR packages that consist of PHP programs and which perform useful functions for your website.

Note:

You can install PEAR packages in either of the following interfaces:

-   cPanel’s [_PHP PEAR Packages_](https://docs.cpanel.net/cpanel/software/php-pear-packages) interface (_cPanel >> Home >> Software >> PHP PEAR Packages_)
-   WHM’s [_Module Installers_](https://docs.cpanel.net/whm/software/module-installers) interface (_WHM >> Home >> Software >> Module Installers_).

##### PHP Extension Community Library (PECL)

A repository for C extensions (pieces of software) for use in PHP.

More:

For more information, visit the [PECL website](http://pecl.php.net/).

##### PHP FastCGI Process Manager (PHP-FPM)

An [alternative PHP FastCGI](https://php-fpm.org/) implementation that improves performance of PHP scripts on servers.

More:

For more information, read our [PHP-FPM](https://docs.cpanel.net/knowledge-base/php-fpm/php-fastcgi-process-manager-php-fpm) documentation.

##### phpMyAdmin

A graphical application that allows server administrators to manipulate and manage MySQL databases over the internet. Server administrators can access this feature in WHM’s [_SQL Services_](https://docs.cpanel.net/whm/sql-services) section.

More:

For more information, visit the [phpMyAdmin website](http://www.phpmyadmin.net/).

##### Plugin

A plugin modifies an interface’s features or functionality. You can write plugins for the cPanel, Webmail, or WHM interfaces.

More:

-   For more information about cPanel plugins, read our [Guide to cPanel Plugins](https://api.docs.cpanel.net/guides/guide-to-cpanel-plugins-in-the-jupiter-theme/) documentation.
-   For more information about WHM plugins, read our [Guide to WHM Plugins](https://api.docs.cpanel.net/guides/guide-to-whm-plugins/) documentation.

##### Plus Addressing

Plus addressing (or subaddressing) adds a plus character and string after an email account username. For example, the `john@example.com` email address could use the `john+list@example.com` plus address. The email account would recognize these messages and place them in the `list` mailbox. If the mailbox does not exist, the account sorts this message to the `inbox` mailbox.

More:

For more information, read our [Email Accounts](https://docs.cpanel.net/cpanel/email/email-accounts) documentation.

##### POP Before SMTP

An authentication method for mail servers. This method allows a user who received mail through [POP3](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#pop3) or [IMAP](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#imap) to send mail for 30 minutes without the need to re-authenticate through SMTP. WHM users can enable or disable this via WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_).

More:

For more information, read our [IMAP vs. POP3](https://docs.cpanel.net/knowledge-base/email/imap-versus-pop3) documentation.

##### PostgreSQL®

A database management system, similar to MySQL.

More:

For more information, visit the [PostgreSQL website](http://www.postgresql.org/).

##### Post Office Protocol version 3 (POP3)

A widely-used email transfer method, like [IMAP](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#imap). POP3 copies every message in an email account to a local computer and then deletes these messages from the mail server. The system does not send information back to the email account about message replies or forwarding.

More:

For more information, read our [IMAP vs. POP3](https://docs.cpanel.net/knowledge-base/email/imap-versus-pop3) documentation.

##### Private Key

A string of characters that a computer uses to encode or decode the encrypted messages that it receives.

-   Encryption schemes use a pair of keys (one [public key](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#public-key) and one private key) to create a secret code.
-   When you use an encryption scheme, anyone who looks at messages that your computer sent or received cannot determine the contents of those messages without access to the private key. A private key protects your confidential information, and you should store it safely.

##### Process ID (PID)

A unique number that your server assigns to each process that runs. You can view a list of running processes with PIDs in WHM’s [_Show Current Running Processes_](https://docs.cpanel.net/whm/system-health/show-current-running-processes) interface (_WHM >> Home >> System Health >> Show Current Running Processes_).

##### ProFTPD

One of cPanel & WHM’s included FTP servers. You can select an FTP server in WHM’s [_FTP Server Selection_](https://docs.cpanel.net/whm/service-configuration/ftp-server-selection) interface (_WHM >> Home >> Service Configuration >> FTP Server Selection_).

More:

For more information, visit the [ProFTPD website](http://www.proftpd.org/).

##### Propagation

In the context of web hosting, the spread of a domain’s DNS information across the internet.

##### Proxy Server

A server that receives requests from users and forwards those requests to other servers.

##### Public Key

**See also:** [Private Key](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#private-key)

A string of characters that a computer uses to encode or decode the encrypted messages it receives. Typically, you place a public key on a server so that you can establish an encrypted connection to that server.

##### public\_ftp

A subdirectory, inside of your home directory, that contains files that are publicly accessible through FTP.

-   FTP users may also upload files to this directory.
-   This is the default directory that users access when they connect to your site through anonymous FTP.

##### public\_html

A subdirectory inside a user’s home directory. It contains files that are publicly-accessible through the HTTP protocol.

-   The `www` directory is a link to the `public_html` directory.
-   Visitors can view any files and folders in the `public_html` directory over the internet, unless the website owner specifically protects them with [password protection](https://docs.cpanel.net/cpanel/files/directory-privacy) or the `.htaccess` file.

##### Pure-FTPd

One of cPanel & WHM’s included FTP servers. You can select an FTP server in WHM’s [_FTP Server Selection_](https://docs.cpanel.net/whm/service-configuration/ftp-server-selection) interface (_WHM >> Home >> Service Configuration >> FTP Server Selection_).

More:

For more information, visit the [Pure-FTPd website](http://www.pureftpd.org/).

##### Python

A popular programming language. You can install the [Python](http://www.python.org/) interpreter, which allows your system to run Python programs, in WHM’s [_Update Preferences_](https://docs.cpanel.net/whm/server-configuration/update-preferences) interface (_WHM >> Home >> Server Configuration >> Update Preferences_).

## Q

##### Quotas

Limits to the amount of system resources, like bandwidth or disk space, that a user may use.

-   To set up quotas, use WHM’s [_Initial Quota Setup_](https://docs.cpanel.net/whm/server-configuration/initial-quota-setup) interface (_WHM >> Home >> Server Configuration >> Initial Quota Setup_).
-   To modify a user’s disk space quota, use WHM’s [_Quota Modification_](https://docs.cpanel.net/whm/account-functions/quota-modification) interface (_WHM >> Home >> Account Functions >> Quota Modification_).

## R

##### Raw Opts (Custom Configuration Flags)

Lines of data that advanced users can add to a specific file on the server in order to customize Apache’s configuration.

More:

For more information, read our [EasyApache](https://docs.cpanel.net/ea4) documentation.

##### Realtime Blackhole List (RBL)

A list of mail servers that send spam. You can subscribe to the RBL, blocking incoming mail from those mail servers, in WHM’s [_Exim Configuration Manager_](https://docs.cpanel.net/whm/service-configuration/exim-configuration-manager) interface (_WHM >> Home >> Service Configuration >> Exim Configuration Manager_).

##### Red Hat® Enterprise Linux® (RHEL)

A commercial Linux operating system distribution. [CentOS](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#centos) is functionally compatible with this operating system.

More:

For more information, read our [Installation Guide](https://docs.cpanel.net/installation-guide).

##### Redirect

**See also:** [Domain Forwarding](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#domain-forwarding)

A feature that sends users to a different domain than the one that they attempted to access. For example, a user may reach `example.com` when they type `example2.com`.

-   Website owners to set up either temporary or permanent redirects.
-   Users can manage their redirects with cPanel’s [_Redirects_](https://docs.cpanel.net/cpanel/domains/redirects) interface (_cPanel >> Home >> Domains >> Redirects_).

##### Referer (HTTP Referer)

A web page that links to a site. This spelling is the industry standard term, though it is a misspelling of the word in other uses.

##### Regular Expressions

Often seen as regex or regexp. Regular expressions allow you to format text so that a specified program can process it and use it to search in a prescribed way. A wildcard character such as an asterisk (`*`) is an example of a regular expression.

##### Relayer

A user who forwards email to a secondary destination. WHM’s [_View Relayers_](https://docs.cpanel.net/whm/email/view-relayers) interface (_WHM >> Home >> Email >> View Relayers_) lets you view users on your server who have relayed mail.

##### RELEASE

One of cPanel & WHM’s [release tiers](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#release-tiers). Versions on this tier are feature-complete and well-tested.

More:

For more information, read our [Product Versions and the Release Process](https://docs.cpanel.net/knowledge-base/cpanel-product/product-versions-and-the-release-process) documentation.

##### Release Tiers

cPanel & WHM’s release tiers are, in order from least to most stable, EDGE, CURRENT, RELEASE, STABLE, and LTS.

More:

For more information, read our [Product Versions and the Release Process](https://docs.cpanel.net/knowledge-base/cpanel-product/product-versions-and-the-release-process) documentation.

##### Reseller

In the hosting industry, resellers use server resources (bandwidth and disk space) and sell those resources in smaller packages to individual cPanel & WHM users.

-   You can create reseller accounts in WHM’s [_Create a New Account_](https://docs.cpanel.net/whm/account-functions/create-a-new-account) interface (_WHM >> Home >> Account Functions >> Create a New Account_).
-   You can manage resellers and their accounts in WHM’s [_Reseller Center_](https://docs.cpanel.net/whm/resellers/reseller-center) interface (_WHM >> Home >> Resellers >> Reseller Center_).

##### Resolver

The client side of the DNS system. Resolvers are programs that process DNS queries and work to obtain an IP address from a human-recognizable URL.

-   In Unix and Linux, the `/etc/resolv.conf` file usually points to a server’s resolvers.
-   You can update resolvers in WHM’s [_Resolver Configuration_](https://docs.cpanel.net/whm/networking-setup/resolver-configuration) interface (_WHM >> Home >> Networking Setup >> Resolver Configuration_).

##### Restoration

In web hosting, a process that uses backup files to replicate an account on a server.

-   This functionality is useful, for example, to recover damaged files or data or in the case of a full hardware failure.
-   You can manage account restoration in WHM’s [_Transfer or Restore a cPanel Account_](https://docs.cpanel.net/whm/transfers/transfer-or-restore-a-cpanel-account) interface (_WHM >> Home >> Transfers >> Transfer or Restore a cPanel Account_).

##### Restricted Restore

**See also:** [Restoration](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#restoration)

A feature in WHM that performs additional security checks on backup files, and then restores them to the server. You can manage account restoration in WHM’s [_Transfer or Restore a cPanel Account_](https://docs.cpanel.net/whm/transfers/transfer-or-restore-a-cpanel-account) interface (_WHM >> Home >> Transfers >> Transfer or Restore a cPanel Account_).

##### Reverse DNS lookup (rDNS)

A process that uses pointer records (PTR) to convert IP addresses (for example, `192.0.2.0`) to domain names (for example, `www.example.com`).

More:

For more information about rDNS, read our [How to Configure Reverse DNS in WHM](https://docs.cpanel.net/knowledge-base/dns/how-to-configure-reverse-dns-in-whm) documentation.

##### Rollback

In computing, a rollback involves the restoration of any part of a system to a previous configuration.

##### Root

This may refer to:

1.  Specific to Unix and Unix-based systems, the system account. The system administrator uses this account, and it carries full privileges to configure a computer system. See [UID](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#uid).
2.  The highest-level directory in a Unix or Unix-based system. Generally, we notate this directory with a forward slash (`/`).

##### Roundcube Webmail

A webmail client that allows users to check email through an browser rather than a mail client.

More:

For more information, visit the [Roundcube website](https://roundcube.net/).

##### RPM Package Manager (RPM)

In our documentation, this term may refer to the packaged `.rpm` file, the software that that file contains, or the package manager itself.

More:

For more information, visit the [RPM website](http://rpm.org/).

##### RSA

An algorithm that generates public and private keys to send encrypted data between a local machine and a remote machine. The name of this method is not an abbreviation; it is named after its three inventors.

##### Ruby

An object-oriented programming language. System administrators can install the `ea-ruby24-mod_passenger` or `ea-ruby27-mod_passenger` [Apache module](https://docs.cpanel.net/ea4/apache/introduction-to-apache/#apache-modules) to create Ruby applications on cPanel & WHM servers.

More:

For more information, read our [How to Create Ruby Web Applications](https://docs.cpanel.net/knowledge-base/web-services/how-to-create-ruby-web-applications) documentation.

##### RubyGems

Warning:

In cPanel & WHM version 66, we [**deprecated** the legacy Ruby codebase](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-deprecation-plan/) and plan to remove it in a future release. This legacy Ruby codebase includes RubyGems applications.

A package manager for the Ruby programming language. Developers can use RubyGems as a self-contained format for Ruby programs and libraries. You can install and manage RubyGems in cPanel’s [_RubyGems_](https://docs.cpanel.net/cpanel/software/rubygems) interface (_cPanel >> Software >> RubyGems_).

##### Ruby on Rails® (RoR)

Warning:

In cPanel & WHM version 66, we [**deprecated** the legacy Ruby codebase](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-deprecation-plan/) and plan to remove it in a future release. This legacy Ruby codebase includes Ruby on Rails applications.

An open-source framework that runs on the Ruby programming language.

More:

For more information, read our [Ruby on Rails](https://docs.cpanel.net/cpanel/software/ruby-on-rails) documentation.

## S

##### Script Hooks

A program that an event triggers.

-   WHM’s [_EasyApache (Apache Update)_](https://docs.cpanel.net/ea4) interface (_WHM >> Home >> Software >> EasyApache (Apache Update)_) lets you embed custom hook scripts into the Apache configuration process.
-   You can create [create custom script hooks](https://api.docs.cpanel.net/guides/guide-to-standardized-hooks/) for other cPanel & WHM actions.

##### Secure Shell (SSH)

A network protocol that allows a user to log in to a remote machine securely. cPanel & WHM can create keys to authenticate a user’s identity during SSH login, and allows users to manage SSH keys.

More:

For more information, read our [How to Secure SSH](https://docs.cpanel.net/knowledge-base/security/how-to-secure-ssh) documentation.

##### Secure Sockets Layer/Transport Layer Security (SSL/TLS)

A newer version of SSL. Both are cryptographic schemes that allow for secure interaction between a browser and a web server.

-   SSL/TLS should protect all sensitive data (for example, credit card numbers) that you transmit over the internet.
-   Website owners can install an SSL certificate on a website in WHM’s [_Install an SSL Certificate on a Domain_](https://docs.cpanel.net/whm/ssl-tls/install-an-ssl-certificate-on-a-domain) interface (_WHM >> Home >> SSL/TLS >> Install a SSL Certificate on a Domain_) to allow SSL/TLS to protect the site.

Warning:

We strongly recommend that you enable [Transport Layer Security (TLS) protocol version 1.2](https://tools.ietf.org/html/rfc5246) on your server.

-   Some clients don’t support [Transport Layer Security (TLS) protocol version 1.3](https://tools.ietf.org/html/rfc8446), which requires OpenSSL 1.1.1 or higher.
-   We only support TLSv1.3 on systems that run cPanel & WHM version 86 or higher.

##### Self-Signed Certificate

An SSL certificate that **doesn’t** verify the identity of the server. It doesn’t do this because the same entity whose identity it certifies signed it.

-   Browsers generally warn users about the authenticity of self-signed certificates.
-   You can create a self-signed SSL certificate in WHM’s [_Generate an SSL Certificate and Signing Requests_](https://docs.cpanel.net/whm/ssl-tls/generate-an-ssl-certificate-and-signing-request) interface (_WHM >> Home >> SSL/TLS >> Generate an SSL Certificate and Signing Request_).

##### Sender Policy Framework (SPF)

A feature that allows a recipient server to verify that the domain specified in the `From:` field really sent the email message.

-   Enable SPF to prevent your server from replying to spam that forged your domain name as part of the sender’s address.
-   SPF **only** functions if both the sending and receiving mail servers use SPF.

Note:

On servers that run the CentOS 7 or AlmaLinux OS 8 operating systems, you may see a `named` warning about the absence of SPF resource records on DNS.

-   This warning is not relevant on CentOS 7 and AlmaLinux OS 8 servers because [RFC 7208 deprecated SPF records](https://tools.ietf.org/html/rfc7208). CentOS 7 and AlmaLinux OS 8 servers use TXT records instead of SPF records.
    
-   Red Hat Enterprise Linux 7.1 and CentOS 7.1 both contain `bind-9.9.4-23.el7`, which is an updated version of BIND that complies with RFC 7208. To resolve this issue, update your operating system to a version that contains the updated version of BIND. For more information, read the [Red Hat Bugzilla case about SPF record errors](https://bugzilla.redhat.com/show_bug.cgi?id=1215164).
    

##### Server Name Indication (SNI)

Allows clients to request a specific hostname at the beginning of the [handshake process](https://en.wikipedia.org/wiki/Handshaking). In our documentation, SNI refers to this protocol in relation to Apache, while Mail SNI refers to this protocol in relation to Exim.

##### Server Profile

A collection of [server roles](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#server-roles) that allow you to optimize a server to perform a specific task or function.

-   For example, the _Mail Node_ profile lets you provide only the services and cPanel & WHM features that allow the system to serve mail.
-   You can select a server profile in WHM’s [_Server Profile_](https://docs.cpanel.net/whm/server-configuration/server-profile) interface (_WHM >> Home >> Server Configuration >> Server Profile_).

##### Server Roles

A collection of services that provide specific server functionality. For example, the _DNS_ role allows users to create and edit DNS zone files. This role consists of the `bind`, `named`, `nds`, `pdns`, and `powerdns` services.

More:

For more information, read our [How to Use Server Profiles](https://docs.cpanel.net/knowledge-base/general-systems-administration/how-to-use-server-profiles) documentation.

##### Service Manager

In computing, a piece of software that monitors the processes and services on a machine. You can enable and disable services with WHM’s [_Service Manager_](https://docs.cpanel.net/whm/service-configuration/service-manager) interface (_WHM >> Home >> Service Configuration >> Service Manager_).

##### Service Proxying

Service proxying configures local services to proxy requests for a cPanel account’s domains to a remote server. For more information, read our [Service Proxying](https://docs.cpanel.net/knowledge-base/general-systems-administration/service-proxying) documentation.

##### Session (Login Session)

The period of activity between when you log in to and log out of an account or service. Each cPanel & WHM session generates a new security token that is **only** valid during that session.

##### Shell Fork Bomb

A malicious process that creates a cascade of new processes in order to use a server’s system resources, which, in effect, crashes the server. WHM’s [_Shell Fork Bomb Protection_](https://docs.cpanel.net/whm/security-center/shell-fork-bomb-protection) interface (_WHM >> Home >> Security Center >> Shell Fork Bomb Protection_) offers a protective service from shell fork bombs.

##### Simple Mail Transfer Protocol (SMTP)

This protocol is the standard by which you transmit email messages across the internet. Use SMTP to send mail to a mail server’s [Mail Transfer Agent (MTA)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#mta).

##### Skeleton Directory

A directory that defines which files and subdirectories new accounts own by default.

-   When you create an account, the new user’s account contains an exact copy of the skeleton directory.
-   You can create these directories in WHM’s [_Skeleton Directory_](https://docs.cpanel.net/whm/account-functions/skeleton-directory) interface (_WHM >> Home >> Account Functions >> Skeleton Directory_).

##### Smart Host

A type of email relay server. A smart host permits an SMTP server to send emails to an intermediate mail server before it sends messages to their final destination.

##### SolusVM

A GUI-based virtual private server (VPS) management system.

More:

For more information, read the [SolusVM](https://solusvm.com/) documentation.

##### SourceGuardian

PHP loaders that utilize a binary byte code and, sometimes, multiple levels of encryption. You can select a PHP loader in WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_).

More:

For more information, visit the [SourceGuardian website](http://www.sourceguardian.com/).

##### Spam

Unsolicited email that an automated system sends in bulk. Because recipients consider spam to be a costly nuisance, cPanel & WHM includes features like Apache SpamAssassin and BoxTrapper that can reduce the amount of spam that you receive.

##### Spam Box

The directory in which Apache SpamAssassin stores spam messages when you enable the [_Spam Box_](https://docs.cpanel.net/cpanel/email/spam-filters) feature. Generally, the system stores these messages in the spam folder for the email account.

##### Spam Score

A value that Apache SpamAssassin assigns to every email message, based on the number of spam-related traits within the message. The higher a message’s spam score, the more likely it is to be spam. [Spam filters](https://docs.cpanel.net/cpanel/email/spam-filters) let you specify what the system does with these messages.

##### Spoof

An attack in which attackers appear as another user through the falsification of data, in order to conceal their identities. Enable [SPF](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#spf) to make it more difficult for spammers to spoof a domain.

##### Sprite

A type of file that can incorporate several different images. The cPanel interface uses sprites to decrease load time. When you [add an icon](https://api.docs.cpanel.net/guides/guide-to-cpanel-interface-customization-and-branding-in-the-jupiter-theme/guide-to-cpanel-interface-customization-appkeys/), cPanel adds it to the appropriate sprite file.

##### SQL Database

A type of relational database management system.

##### SSL Certificate

An electronic document that binds a public key to an identity that consists of an email address, company, and location. This electronic document is a key piece in an authentication process.

More:

For more information, read our [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl) documentation.

##### STABLE

One of cPanel & WHM’s [release tiers](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#release-tiers). Versions on this tier have received considerable public exposure, testing, and verification.

More:

For more information, read our [Product Versions and the Release Process](https://docs.cpanel.net/knowledge-base/cpanel-product/product-versions-and-the-release-process) documentation.

##### Subaccount

cPanel account users can create subaccounts that use the same login and password information for email, FTP, and [Web Disk](https://docs.cpanel.net/cpanel/files/web-disk) services.

-   The system maintains password synchronization between each of the subaccount’s allowed services.
-   Users can manage subaccounts with cPanel’s [_User Manager_](https://docs.cpanel.net/cpanel/preferences/user-manager) interface (_cPanel >> Home >> Preferences >> User Manager_).

##### Subdomain

A subsection of a website that exists as a subdirectory in the website owner’s home folder. For example, for the `example.com` domain, the subdomain URL could appear as `subdomain.example.com`. You can add and manage subdomains in cPanel’s [_Domains_](https://docs.cpanel.net/cpanel/domains/domains) interface (_cPanel >> Home >> Domains >> Domains_).

##### suEXEC

An Apache feature that allows users to run CGI and SSI applications on the system as themselves. By default, the system account (the `nobody` account with a [UID](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#uid) of `99`) executes CGI and SSI.

## T

##### Tar

A program that collates files for transfer or distribution. The system usually compresses files that this program processes into [tarballs](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#tarball).

##### Tarball

A file that the `tar` program collates and, usually, compresses.

##### Telnet

A network protocol that allows a user to log in to a remote machine user account remotely. Telnet is similar to [SSH](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ssl), but is **less** secure. **Don’t** use Telnet to connect to your website except for testing purposes. Telnet sends login information as plain text, which others can easily intercept.

##### Template Toolkit (Perl Template Toolkit)

A Perl library template processing system that we use to create templates for all of the cPanel and WHM interfaces.

More:

For more information, read our [Guide to Template Toolkit](https://api.docs.cpanel.net/guides/guide-to-template-toolkit/) documentation or visit the [Template Toolkit](http://template-toolkit.org/) website.

##### Terabyte or Tebibyte (TB or TiB)

A unit of measure for digital memory storage. Generally, for the purposes of this documentation, one terabyte is a tebibyte, equal to 1,024 gigabytes.

##### Theme

A skeletal framework of interfaces, over which the system applies one of that theme’s styles.

-   cPanel & WHM currently ships with one default cPanel theme and one default WHM theme, as well as Webmail and login themes.
-   You can manage your themes, except the Jupiter theme for the cPanel interface, with WHM’s [_Theme Manager_](https://docs.cpanel.net/whm/themes/theme-manager) interface (_WHM >> Home >> Themes >> Theme Manager_). To make [Jupiter](https://docs.cpanel.net/cpanel/the-cpanel-interface/the-cpanel-interface-jupiter) your default theme, read our [_How to Change the Default Theme in cPanel_](https://docs.cpanel.net/knowledge-base/general-systems-administration/how-to-change-the-default-theme-in-cpanel) documentation.

##### Thumbnail

A smaller version of an image file that lets you easily view multiple images.

##### Time to Live (TTL)

A value that specifies how long clients will cache DNS zone data. You can view this information in WHM’s [_Edit DNS Zone_](https://docs.cpanel.net/whm/dns-functions/edit-dns-zone) interface (_WHM >> Home >> DNS Functions >> Edit DNS Zone_).

##### Trojan Horse (Trojan)

Software that claims to perform one function but secretly performs malicious functions.

##### Trust Key Relationship

A cryptographic scheme that involves a public and private key pair.

##### Two-Factor Authentication (2FA)

An improved security measure that requires two forms of user identification: a password and a generated security code. When you enable 2FA, an application on your smartphone will supply a generated security code for authorization.

-   Users can configure 2FA in cPanel’s [_Two-Factor Authentication_](https://docs.cpanel.net/cpanel/security/two-factor-authentication-for-cpanel) interface (_cPanel >> Home >> Security >> Two-Factor Authentication_).
-   Server administrators can manage 2FA in WHM’s [_Two-Factor Authentication_](https://docs.cpanel.net/whm/security-center/two-factor-authentication-for-whm) interface (_WHM >> Home >> Security Center >> Two-Factor Authentication_).

## U

##### Ubuntu

An open-source Linux operating system distribution based on [Debian](https://www.debian.org/). [Ubuntu](https://www.ubuntu.com) is one of [cPanel & WHM’s supported operating systems](https://docs.cpanel.net/installation-guide/system-requirements-ubuntu/).

##### User Datagram Protocol (UDP)

A connectionless transport protocol that works in conjunction with the Internet Protocol (IP). UDP transfers small units of data that require little reassembly, because it does not transmit data packets in a sequential order. It primarily broadcasts messages over a network. DNS lookups use UDP.

##### User ID (UID)

The unique user number that the system assigns to each user during a session. Notable UIDs include:

-   `0` — `root`, the top-level system user. To find all of the users with this UID, run the `grep :x:0: /etc/passwd` command.
    
-   `99` — `nobody`, the default executor of [CGI](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#cgi) scripts, if [suEXEC](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#suexec) is disabled. The system reserves UIDs `0` through `100` for system accounts like `admin` and `root`.
    

##### Unbound

A [DNS resolver](https://nlnetlabs.nl/) that performs caching and DNSSEC validation. This uses the `libunbound` library, which runs separately and can convert hostnames to IP addresses and perform other tasks using DNS information.

##### Uniform Resource Identifier (URI)

A string of characters that identifies a website. Some information uses URI synonymously with the terms URL and web address, though technical differences exist between the three terms.

##### Uniform Resource Locator (URL)

A string of characters that identifies the location of a website. Some information uses URL synonymously with the terms URI and web address, though technical differences exist between the three terms.

##### Unix Time

Unix time measures the number of seconds that have passed since the January 1, 1970 in UTC.

##### URI Encoding

Encodes information within a [Uniform Resource Identifier (URI)](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#uri). In URI encoding, you must convert characters that browsers reserve for URL formatting into percent-encoded characters (for example, encode the forward slash (`/`) as `%2F`).

More:

For more information, visit [URL Encoding at W3Schools](http://www.w3schools.com/tags/ref_urlencode.asp).

##### User

A person who uses a computer to accomplish some purpose.

##### UUID (Universally Unique Identifier)

A value that the system uses to identify a resource, similar to [GUID](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#guid). UUID is the more common identifier while Microsoft products are the main users of GUID.

## V

##### Virtual Private Server (VPS)

A virtualized server. A single physical server can host multiple VPSs, each of which run their own instances of an operating system. This allows each VPS to have a separate `root` or superuser account, and to operate independently.

##### VirtualHost

A method to host multiple domains on a single server and sometimes on a single IP address.

More:

For more information, read the [Wikipedia VirtualHost article](http://en.wikipedia.org/wiki/Virtual_host).

##### Visitor

A person who views a website.

## W

##### Web Browser

An application that visitors use to view and interact with sites and pages on the World Wide Web. Examples include Firefox®, Chrome, and Safari®.

##### Webcall

A [capability URL](https://www.w3.org/TR/capability-urls/) that allows unauthenticated access to a protected resource on a cPanel server.

**See also:** [Dynamic DNS (DDNS) Domain](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#ddns).

##### Web Disk

A cPanel feature that allows website owners to drag and drop files to manipulate them through cPanel’s [_Web Disk_](https://docs.cpanel.net/cpanel/files/web-disk) interface (_cPanel >> Home >> Files >> Web Disk_).

##### Web Server

A program, such as [Apache](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#apache), which receives requests from clients (browsers), retrieves the requested webpages, and serves them.

##### Webalizer

A program that displays various statistics for a website in tables and graphs.

More:

For more information, visit the [Webalizer website](http://www.webalizer.com/).

##### WebHost Manager (WHM)

Companion software to [cPanel](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#cpanel), which we design for hosting providers, resellers, and system administrators.

##### Webmail

Any application that allows website owners to access email through a browser. The main advantage to webmail is the ability to access the email account from any computer on the internet without the need to install or configure a specific mail program.

More:

For more information, read our [Webmail](https://docs.cpanel.net/webmail) documentation.

##### Wheel Group

A group of users who can execute the `su` and `sudo` commands on a Unix-based system, which allows them to become the `root` user. The `su` command requires the password for the `root` user, while the `sudo` command requires the user’s account password.

##### Whitelist

**See also:** [Blacklist](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#blacklist), [Greylisting](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#greylisting).

This may refer to:

-   In [BoxTrapper](https://docs.cpanel.net/cpanel/email/boxtrapper), a list of approved email senders. BoxTrapper automatically delivers messages from senders who are on the whitelist directly to the inbox.
-   In [cPHulk](https://docs.cpanel.net/whm/security-center/cphulk-brute-force-protection), a list of approved IP addresses. cPHulk **always** allows logins to your server from IP addresses on the whitelist.

##### whmconf

This module creates a backup configuration containing WHM’s common settings that aren’t user-specific. For example, the settings from WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_) and WHM’s [_Basic WebHost Manager Setup_](https://docs.cpanel.net/whm/server-configuration/basic-webhost-manager-setup) interface (_WHM >> Home >> Server Configuration >> Basic WebHost Manager Setup_). The [`cpconftool` script](https://docs.cpanel.net/whm/scripts/the-cpconftool-script) creates this configuration.

When you create a server backup file, the system creates a tarball that contains this data. The `whmconf` module creates the tarball in the `whm-config-backup-cpanel__system__whmconf-11.86.0.9999-1577581839.tar.gz` format, where `11.86.0.9999` is the cPanel & WHM version and `1577581839` is a [Unix epoch timestamp](https://en.wikipedia.org/wiki/Unix_time).

##### whois

A Unix or Linux command that you can run on the command line to find out who owns a domain. For example, `whois cpanel.net` returns the ownership information for cPanel, L.L.C.’s website.

##### Wildcard Certificate

A certificate that lets you secure a domain with an unlimited number of subdomains, but each subdomain **requires** a dedicated IP address.

##### www

A symlink to the directory that holds the files for a website (`~/public_html`).

## X

##### X-source Headers

Pieces of information that the system adds to email messages from a PHP script on your server, which detail the script’s location.

-   Enable these headers to help you locate insecure email scripts that spammers have abused.
-   You can enable these headers in WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_).

##### Xen®

An open-source microkernel-designed hypervisor that allows for many instances of an operating system or different operating systems to run on a single host at the same time.

More:

For more information, visit the [Xen website](https://www.xenproject.org/).

##### XFS®

A high-performance filesystem for 64-bit servers. Servers that run the [CentOS](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#centos) 7, AlmaLinux OS 8, or Ubuntu operating systems can use the XFS filesystem with cPanel & WHM.

## Y

##### YAML Ain’t Markup Language or Yet Another Markup Language (YAML)

A markup language that allows developers to create documents that are both human- and machine-readable. Many of cPanel & WHM’s configuration files use this format.

## Z

##### Zone (DNS Zone)

An administrative space or portion of the [Domain Name System](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary//#dns). This space directs internet traffic to the correct location. For example, `example.com` is a DNS zone whose servers direct its internet traffic.

##### Zone File (DNS Zone File)

A file on your server that primarily maps IP addresses to domain names. A correctly-configured zone file **must** exist in order for visitors to access your server from the internet.
