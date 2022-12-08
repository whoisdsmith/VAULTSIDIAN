---
created: 2022-08-05T00:01:45 (UTC -04:00)
tags: [ullright ull.at business websolutions workflow management open source]
source: https://www.ullright.org/ullWiki/show/nextcloud-cheatsheet
author: 
---

# Nextcloud Cheatsheet / occ

> ## Excerpt
> ullright is an opensource web framework initiated by ull.at business websolutions

---
# Nextcloud Cheatsheet / occ

News: [https://nextcloud.com/blog/category/release/](https://nextcloud.com/blog/category/release/ "Link opens in a new window")

## Status

-   sudo -u www-data php /var/www/nextcloud/occ status

Reset Admin Password

-   sudo -u www-data php /var/www/nextcloud/occ user:resetpassword admin

## Scan files

-   sudo -u www-data php /var/www/nextcloud/occ files:scan -v --all
-   sudo -u www-data php /var/www/nextcloud/occ files:scan -v myusername
-   sudo -u www-data php /var/www/nextcloud/occ files:scan -v --path="/myusername/files/myfolder/mysubfolder" myusername
-   For external storage one has to use a user, e.g. admin
    -   sudo -u www-data /usr/bin/php /var/www/nextcloud/occ files:scan -v --path="/admin/files/name\_of\_external\_storage"

#### Error while scanning: "Entry path/to/file will not be accessible due to incompatible encoding"

-   German Umlauts with different encoding (OS X normalization form D for UTF-8)
-   Solution:
    -   apt install convmv
    -   convmv -f utf-8 -t utf-8 --nfc -r /srv/nextcloud/
    -   check, then with --notest
    -   convmv -f utf-8 -t utf-8 --nfc -r --notest /srv/nextcloud/
    -   \+ rescan with occ

## Upgrade

-   sudo -u www-data php /var/www/nextcloud/updater/updater.phar --no-interaction
-   sudo -u www-data php /var/www/nextcloud/occ upgrade

Turn maintenance mode on/off

-   sudo -u www-data php /var/www/nextcloud/occ maintenance:mode --on
-   sudo -u www-data php /var/www/nextcloud/occ maintenance:mode --off

Add missing indices

-   sudo -u www-data php /var/www/nextcloud/occ db:add-missing-indices

Convert to bigint

-   sudo -u www-data php /var/www/nextcloud/occ db:convert-filecache-bigint

Add missing columns:

-   sudo -u www-data php /var/www/nextcloud/occ db:add-missing-columns

Add missing primary keys:

-   sudo -u www-data php /var/www/nextcloud/occ db:add-missing-primary-keys

Fix interupted upgrades

-   sudo -u www-data php /var/www/nextcloud/occ maintenance:repair

## Install apps from the command line

[https://docs.nextcloud.com/server/20/admin\_manual/configuration\_server/occ\_command.html#apps-commands-label](https://docs.nextcloud.com/server/20/admin_manual/configuration_server/occ_command.html#apps-commands-label "Link opens in a new window")

-   sudo -u www-data php /var/www/nextcloud/occ app:list
-   sudo -u www-data php /var/www/nextcloud/occ app:install files\_external
-   sudo -u www-data php /var/www/nextcloud/occ app:enable files\_external

Configure

-   sudo -u www-data php /var/www/nextcloud/occ config:list
