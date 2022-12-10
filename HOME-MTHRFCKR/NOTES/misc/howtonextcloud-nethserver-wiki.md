---
tags:: notes
created: 2022-07-16T20:57:00 (UTC -04:00)
tags: [ht v7,cloud]
source: https://wiki.nethserver.org/doku.php?id=howto:nextcloud
author: 
---

# howto:nextcloud [NethServer Wiki]

> ## Excerpt
> Information applies to: NethServer 7.x, Nextcloud >=21.x  (for previous versions check old revisions of this document)

---
# Nextcloud

**Information applies to:** NethServer 7.x, Nextcloud >=21.x (for previous versions check old revisions of this document)  

[Nextcloud](https://nextcloud.com/ "https://nextcloud.com/") provides a safe, secure, and compliant file synchronization and sharing solution on servers that you control. NethServer 7 provides a preconfigured Nextcloud instance integrated with other NethServer services.

**Note:** With the release of Nextcloud 18.0.1, nextcloud rpm was [merged into nethserver-nextcloud](https://github.com/NethServer/nethserver-nextcloud/pull/73 "https://github.com/NethServer/nethserver-nextcloud/pull/73")  
**Note:** With the release of Nextcloud 18.0.4 we switched from PHP 7.2 to PHP 7.3  
**Note:** With the release of Nextcloud 21.0.2 we switched from default mariadb-5.5 database server to rh-mariadb105  

  

## FAQ

**Where is Nextcloud installation located?**  

-   The rpm package puts Nextcloud files under `/usr/share/nextcloud` directory.
    
-   Nextcloud config file is located at `/usr/share/nextcloud/config/config.php`.
    
-   User data is under `/var/lib/nethserver/nextcloud` directory.
    

  
**Can I upgrade Nextcloud via its built-in updater?**  
It is not recommended. NethServer manages updates through RPM packages.  
  
**How can I run Nextcloud's`occ` command?**  
`occ` command should be run as the HTTP user (apache) and with the same php version used by your Nextcloud instance. One method to call `occ` command is:

```
sudo -u apache scl enable rh-php73 -- php -dmemory_limit=512M /usr/share/nextcloud/occ
```

An easier way is to make use of the occ wrapper (`/usr/local/sbin/occ`) provided by NethServer:

```
occ
```

  
**After updating/upgrading Nextcloud, the apps are disabled**  
Nextcloud update/upgrade procedure disables 3rd. party apps to avoid incompatibility problems. Server logs keep track of which apps were disabled. After a successful update/upgrade procedure you can use the _Applications_ page to update and re-enable the apps. Apps can also be enabled from the command line:

```
# example: enabling calendar app
occ app:enable calendar
```

  
**Logged in as admin but don't have access to administration features**  
At first install, NethServer's Nextcloud instance has an internal `admin` account with a default password of `Nethesis,1234` (that _should_ be changed). When an account provider is installed (nethserver-directory: openLDAP; nethserver-dc: Active Directory) users can authenticate into Nextcloud with their LDAP credentials. This can pose some inconvenience, as the account provider might have an account named `admin` as well, and trip you when login in to Nextcloud. This can be alleviated by setting a different password for Nextcloud's admin account.  

  

## Troubleshooting

### Internal Server Error

When accessing to Nextcloud's URL, the apache httpd web server can return the following error message when any of the related services Nextcloud relies on is not working:

```
Internal Server Error

The server encountered an internal error and was unable to complete your request.
Please contact the server administrator if this error reappears multiple times, please include the technical details below in your report.
More details can be found in the server log.
```

Check the status of mysqld/mariadb and rh-php73-php-fpm services:

```
systemctl -l status rh-php73-php-fpm rh-mariadb105-mariadb@nextcloud.service  # mysqld on Nextcloud < 21.x
```

  

### How to reset Nextcloud's admin password

```
occ user:resetpassword admin
```

  

### Nextcloud remains in maintenance mode after an upgrade

```
occ maintenance:mode --off
```

  

### "Nextcloud will be updated to version xx.x.x" message is shown after an upgrade

This could be due to a partial upgrade done by the rpm packages. The specific issue might have been reflected on server logs. By running `occ upgrade` command you'll either finish the upgrade process or get some errors showing the problem:  

```
occ upgrade
```

  

### Warning: "There were problems with the code integrity check"

Some files have not passed the integrity check. These could be custom files, or leftovers from a previous update or installation.

-   Find the problematic files using the “List of invalid files…” shown on Nextcloud's admin interface
    
-   Determine the type of issue (`INVALID_HASH`, `MISSING_FILE`, `EXTRA_FILE`, `EXCEPTION`…) for each file
    
-   Act accordingly to the self-explanatory issue type and the solutions provided in the Nextcloud documentation
    
-   Trigger a “Rescan…” to verify the issues have been solved
    

  

### Background jobs: Last job execution ran X weeks/months ago. Something seems wrong

If cron is the selected job scheduler for Nextcloud, make sure a cron job for `/usr/share/nextcloud/cron.php` is in place, and it is called by `apache` user using the right php version. Since Nextcloud 14.0.3 release, NethServer takes care of this.  

  

### Your installation has no default phone region set

> Your installation has no default phone region set. This is required to validate phone numbers in the profile settings without a country code. To allow numbers without a country code, please add “default\_phone\_region” with the respective ISO 3166-1 code ↗ of the region to your config file.

This advice is not important. If you want to, you can follow as advised, editing \`/usr/share/nextcloud/config/config.php\` file to add your country's “default\_phone\_region”. Here's an example for Italy:

```
  'default_phone_region' => 'IT',
```

  

### Warning: "The database is missing some optional columns"

> The database is missing some optional columns. Due to the fact that adding columns on big tables could take some time they were not added automatically when they can be optional. By running “occ db:add-missing-columns” those missing columns could be added manually while the instance keeps running. Once the columns are added some features might improve responsiveness or usability.

Fix it as instructed by the warning message:

```
  occ db:add-missing-columns
```

  

### Warning: "The database is missing some primary keys"

> The database is missing some primary keys. Due to the fact that adding primary keys on big tables could take some time they were not added automatically. By running “occ db:add-missing-primary-keys” those missing primary keys could be added manually while the instance keeps running.

Fix it as instructed by the warning message:

```
  occ db:add-missing-primary-keys
```

  

### "File is locked"

Nextcloud implements a file locking mechanism to avoid file corruption. By default, Nextcloud uses the database locking backend.

Under some circumstances, a file could remain inaccessible due to an unreleased lock. To manually release the locks:

```
  occ maintenance:mode --on
  
  /opt/rh/rh-mariadb105/root/bin/mysql --socket="/var/run/rh-mariadb105-mariadb/nextcloud-mysql.sock" nextcloud    # `mysql nextcloud` on previous versions
  
  DELETE FROM oc_file_locks WHERE 1;
  \q
  
  occ maintenance:mode --off
```

If it does not work, a user reported that a temporary workaround was to disable file locking (\`'filelocking.enabled' ⇒ false,\`) from the config.php file. Consult Nextcloud's documentation.

  

### Nextcloud stuck at "update in process" after using the built-in updater

Please, avoid using the built-in updater. Stick to the update methods supported by your GNU/Linux distribution. If you need a newer version ask to the package maintainer.

  
To revert the changes:

```
  # mysqldump nextcloud > nextcloud-$(date +%F-%T).sql    # optional (For Nextcloud < 21.x)
  mysqldump --socket /run/rh-mariadb105-mariadb/nextcloud-mysql.sock --databases nextcloud --default-character-set=utf8mb4 -r nextcloud-$(date +%F-%T).sql  # optional
  cp -aR /usr/share/nextcloud /usr/share/nextcloud.bad  # optional (as a backup)
```

  
Restore Nextcloud's config.php file form a backup. If no backup present, edit Nextcloud's config file (e.g. `/usr/share/nextcloud/config/config.php`) removing the lines referring to `maintenance` and `updater.secret`.

```
  yum reinstall nethserver-nextcloud
```

  
Check Nextcloud is working as expected. If all is good you can get rid of the backup files:

```
  rm nextcloud-*.sql
  rm -r /usr/share/nextcloud.bad/    # use -rf to force removal without confirmation
```

  

### Exception: Updates between multiple major versions are unsupported

Problem arises if some major release update was skipped. Nextcloud manual says:

> It is best to keep your Nextcloud server upgraded regularly, and to install all point releases and major releases. Major releases are 11, 12, and 13. Point releases are intermediate releases for each major release. For example, 13.0.4 and 12.0.9 are point releases. Skipping major releases is not supported.

Some users reported the following solutions (having a backup of Nextcloud's files, configuration and user data is advisable before proceeding; examples are unrelated between them and therefore can refer to older or different Nextcloud versions):

Have into account that the transition to Nextcloud 21.x required a major change on the underlying mysql/mariadb database engine version. The described downgrade procedures have not been tested with those circumstances.

**a)** Package downgrade:

Notice rpm and yum command's may not list nextcloud package, since Nextcloud 18.0.1 release nextcloud package was obsoleted and merged with nethserver-nextcloud.

1\. Find out the previously installed major release (checking logs, yum history…):  

```
[root@server ~]# grep "'version'" /usr/share/nextcloud/config/config.php

[root@server ~]# yum history packages *nextcloud
ID     | Action(s)      | Package                                              
-------------------------------------------------------------------------------
    23 | Updated        | nethserver-nextcloud-1.1.7-1.ns7.noarch            EE
    23 | Update         |                      1.2.7-1.ns7.noarch            EE
    23 | Updated        | nextcloud-12.0.2-2.el7.noarch                      EE
    23 | Update         |           14.0.3-1.el7.noarch                      EE
```

2\. Find out installed and available `nethserver-nextcloud` and `nextcloud` packages:  

```
[root@server ~]# yum --showduplicates list *nextcloud
```

3\. Downgrade _\*nextcloud_ packages to the latest next major release that follows to the previously installed release (in this example, the previously installed major release was nextcloud-12 so the next major release that follows is nextcloud-13):  

```
[root@server ~]# yum downgrade nethserver-nextcloud-1.2.4-1.ns7 nextcloud-13.0.6-1.el7
```

4\. Keep updating _\*nextcloud_ packages to the latest next major release until reaching the current release (if there is any other major release in-between, do the update specifying the packages' version):  

```
[root@server ~]# yum update \*nextcloud
```

  

**b)** Migration scripts to latest version (experimental procedure):  
Get installed version:

```
occ --version
```

Enable debug mode:

```
vi /usr/share/nextcloud/config/config.php
  'debug' => true,
```

Get migration status:

```
occ migrations:status core
```

Migrate Nextcloud to latest version (migration scripts):

```
occ migrations:migrate core
```

Edit Nextcloud's `config.php` file, replacing the old version number and setting the current (installed) Nextcloud version number. Also remember to disable debug mode by removing the debug line previously added:

```
vi /usr/share/nextcloud/config/config.php
 'version' => '22.0.2',
```

Upgrade Nextcloud and disable maintenance mode:

```
occ upgrade
occ maintenance:mode --off
```

Check Nextcloud's `config.php` file to make sure the upgrade set the current (and correct) version.

  

## Apps and 3rd. party integrations

-   [Collabora CODE](https://wiki.nethserver.org/doku.php?id=collabora "collabora")
    
-   [OnlyOffice Document Server](https://wiki.nethserver.org/doku.php?id=onlyoffice "onlyoffice")
    
-   OnlyOffice Community Document Server (built-in support through Nextcloud apps, since Nextcloud 18)
    
-   [WebTop5](https://wiki.nethserver.org/doku.php?id=userguide:webtop5_nextcloud_itegration "userguide:webtop5_nextcloud_itegration")
    
-   Bookmarks app
    
    -   If Bookmarks app fails to install due to gmp library not being available, install the library for the php version being used:
        

```
yum install rh-php73-php-gmp
systemctl reload rh-php73-php-fpm
```
