---
created: 2022-08-05T00:33:01 (UTC -04:00)
tags: []
source: https://gnu.my.id/nextcloud
author: 
---

# Nextcloud - CLI Cheatsheet 

Nextcloud is an open source, self-hosted file share and communication platform. Access & sync your files, contacts, calendars & communicate and collaborate across your devices.

---
Nextcloud

Nextcloud is an open source, self-hosted file share and communication platform. Access & sync your files, contacts, calendars & communicate and collaborate across your devices.

![](https://2011130545-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MDFqdjVoIfBPACeWTan%2F-MFU8VggJ7adnVHdOrv-%2F-MFUFXtuCSA5tXkUQj-a%2Fhead_nextcloud.jpg?alt=media&token=bf8c75ae-5bd4-4cae-98fa-007c8df82a66)

Live demo: [https://try.nextcloud.com/](https://try.nextcloud.com/)

---
# General Command

## Execute OCC command

Run the command below in the Nextcloud directory.

/opt/rh/{PHP\_VERSION}/root/bin/php occ {OCC\_COMMMAND}

---

# Troubleshooting

## Some files have not passed the integrity check

The complete message of the problem is,`Some files have not passed the integrity check. Further information on how to resolve this issue can be found in the documentation.`

How to solve it,

-   1.
    
    Open the link `List of invalid files…`and see what files/folders are displayed.
    

-   2.
    
    Verify the existence of the file, and delete it.
    

---
## MySQL is used as database but does not support 4-byte characters

The complete message of the problem is,`MySQL is used as database but does not support 4-byte characters. To be able to handle 4-byte characters (like emojis) without issues in filenames or comments for example it is recommended to enable the 4-byte support in MySQL. For further details read the documentation page about this.`

How to solve it,

-   1.
    
    Login to `mysql`(don't use `root`).
    

-   2.
    
    Type `show variables like 'innodb_file_format';`and check whether the Value column is = `Barracuda`. If so, continue to step number `5`.
    

-   3.
    
    If Value turns out to be = `Antelope`, edit the configuration file `/etc/mysql/conf.d/mysql.cnf`, add the code below.
    
    \[mysqld\]
    
    innodb\_large\_prefix=true
    
    innodb\_file\_format=barracuda
    
    innodb\_file\_per\_table=1
    

-   4.
    
    Login to `mysql`and check again if it has changed.
    

-   5.
    
    If so, run the following command.
    
    ALTER DATABASE {DB\_NAME} CHARACTER SET utf8mb4 COLLATE utf8mb4\_general\_ci;
    

-   6.
    
    Exit from `mysql`, run the commands below sequentially from within the Nextcloud path.
    
    sudo -u {USERNAME} /opt/rh/{PVP\_VERSION}/root/bin/php occ config:system:set mysql.utf8mb4 --type boolean --value="true"
    
    sudo -u {USERNAME} /opt/rh/{PVP\_VERSION}/root/bin/php occ maintenance:repair
    

---
## The “X-Content-Type-Options” HTTP header is not set to “nosniff”

The complete message of the problem is,`The "X-Content-Type-Options" HTTP header is not set to "nosniff". This is a potential security or privacy risk, as it is recommended to adjust this setting accordingly.`

How to solve it,

-   1.
    
    From the terminal, run the following command.
    
    curl -vvv https://URL\_NEXTCLOUD
    

-   2.
    
    Make sure the entry `X-Content-Type-Options: nosniff`is there.
    

-   3.
    
    If you find that the entry appears multiple times, check the `/etc/httpd/conf/httpd.conf`. It's possible that this entry existed as part of the settings of an older version. Delete if it's there.
    

---
## The “X-Robots-Tag” HTTP header is not set to “none”

The complete message of the problem is,`The "X-Robots-Tag" HTTP header is not set to "none". This is a potential security or privacy risk, as it is recommended to adjust this setting accordingly.`

How to solve it,

-   1.
    
    From the terminal, run the following command.
    
    curl -vvv https://URL\_NEXTCLOUD
    

-   2.
    
    Make sure the entry `X-Robots-Tag: none`is there.
    

-   3.
    
    If you find that the entry appears multiple times, check the `/etc/httpd/conf/httpd.conf`. It's possible that this entry existed as part of the settings of an older version. Delete if it's there.
    

---
## SQLite is currently being used as the backend database

The complete message of the problem is,`SQLite is currently being used as the backend database. For larger installations we recommend that you switch to a different database backend. This is particularly recommended when using the desktop client for file synchronisation. To migrate to another database use the command line tool: 'occ db:convert-type', or see the documentation ↗.`

How to solve it,

-   1.
    
    Create a new mysql db.
    

-   2.
    
    Run the following command on the installed Nextcloud folder.
    
    sudo -u {USERNAME} /opt/rh/{PVP\_VERSION}/root/bin/php occ db:convert-type --all-apps mysql {DB\_USERNAME} localhost {DB\_NAME}
    

-   3.
    
    Enter the db pass if prompted.
    

---

## Some columns in the database are missing a conversion to big int.

The complete message of the problem is,`Some columns in the database are missing a conversion to big int. Due to the fact that changing column types on big tables could take some time they were not changed automatically. By running 'occ db:convert-filecache-bigint' those pending changes could be applied manually. This operation needs to be made while the instance is offline. For further details read the documentation page about this.`

How to solve it,

Run the following command on the installed Nextcloud folder.

sudo -u {USERNAME} /opt/rh/{PVP\_VERSION}/root/bin/php occ db:convert-filecache-bigint

---

## The PHP OPcache is not properly configured.

The complete message of the problem is,`The PHP OPcache is not properly configured. For better performance we recommend to use following settings in the php.ini:`

How to solve it,

-   1.
    
    Edit the file `/etc/opt/rh/{PHP_VERSION}/php.d/10-opcache.ini`according to the suggested configuration on the Nextcloud admin page.
    

-   2.
    
    Don't forget to activate `opcache.enable_cli=1`it too.
    

-   3.
    
    Save, and restart with `systemctl restart httpd`.
    

---

## The database is missing some indexes.

The complete message of the problem is,`The database is missing some indexes. Due to the fact that adding indexes on big tables could take some time they were not added automatically. By running "occ db:add-missing-indices" those missing indexes could be added manually while the instance keeps running. Once the indexes are added queries to those tables are usually much faster.`

How to solve it,

Run the following command on the installed Nextcloud folder.

sudo -u {USERNAME} /opt/rh/{PVP\_VERSION}/root/bin/php occ db:add-missing-indices

---

## The database is missing some optional columns.

The complete message of the problem is, `The database is missing some optional columns. Due to the fact that adding columns on big tables could take some time they were not added automatically when they can be optional. By running "occ db:add-missing-columns" those missing columns could be added manually while the instance keeps running. Once the columns are added some features might improve responsiveness or usability.`

How to solve it,

Run the following command on the Nextcloud installation folder.

sudo -u {USERNAME} /opt/rh/{PVP\_VERSION}/root/bin/php occ db:add-missing-columns

---

## This instance is missing some recommended PHP modules.

The complete message of the problem is, `This instance is missing some recommended PHP modules. For improved performance and better compatibility it is highly recommended to install them.`

How to solve it,

-   1.
    
    Install the requested PHP module. Example,
    
    sudo yum install -y php7.0-gmp
    
    
    

-   2.
    
    Find out the location of the file `php.ini`in the server with the command,
    
    php --ini
    

-   3.
    
    Then add to the file `php.ini`the line below, in the **Dynamic Extension section** .
    
    extension\=php\_gmp.so
    

-   4.
    
    The last step, restart `httpd`with the following command.
    
    systemctl restart httpd
