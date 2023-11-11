---
tags:: notes
created: 2022-07-16T21:00:50 (UTC -04:00)
tags: []
source: https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html
author: 
---

# ownCloud Server Tuning :: ownCloud Documentation

> ## Excerpt
> ownCloud Server Tuning

---

# ownCloud Server Tuning

Table of Contents

-   [Using Cron to Perform Background Jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#using-cron-to-perform-background-jobs)
-   [Enable Memory Caching](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#enable-memory-caching)
-   [Use Redis-based Transactional File Locking](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#use-redis-based-transactional-file-locking)
-   [Redis Tuning](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#redis-tuning)
    -   [TCP-Backlog](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#tcp-backlog)
    -   [Transparent Huge Pages (THP)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#transparent-huge-pages-thp)
    -   [Redis Latency Problems](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#redis-latency-problems)
-   [Database Tuning](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#database-tuning)
    -   [Using MariaDB/MySQL Instead of SQLite](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#using-mariadbmysql-instead-of-sqlite)
    -   [Tune MariaDB/MySQL](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#tune-mariadbmysql)
    -   [Tune PostgreSQL](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#tune-postgresql)
-   [SSL / Encryption App](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#ssl-encryption-app)
-   [Webserver Tuning](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#webserver-tuning)
    -   [Tune Apache](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#tune-apache)

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#using-cron-to-perform-background-jobs)Using Cron to Perform Background Jobs

See [Background Jobs](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.htmlbackground_jobs_configuration.html) for a description and the benefits.

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#enable-memory-caching)Enable Memory Caching

Caching improves performance by storing data, code, and other objects in memory. Memory cache configuration for ownCloud is no longer automatically available from ownCloud 8.1 but must be installed and configured separately. ownCloud supports [Redis](https://redis.io), [APCu](https://www.php.net/manual/en/intro.apcu.php), and [Memcached](https://memcached.org) as memory caching backends. See [Memory Caching](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.htmlcaching_configuration.html), for further details.

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#use-redis-based-transactional-file-locking)Use Redis-based Transactional File Locking

File locking is enabled by default, using the database locking backend. However, this places a significant load on your database. See the section [Transactional File Locking](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html../files/files_locking_transactional.html) for how to configure ownCloud to use Redis-based Transactional File Locking.

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#redis-tuning)Redis Tuning

Redis tuning improves both file locking (if used) and memory caching (when using Redis). Here is a brief guide for tuning Redis to improve the performance of your ownCloud installation, when working with sizeable instances.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#tcp-backlog)TCP-Backlog

If you raised the TCP-backlog setting, the following warning appears in the Redis logs:

```plaintext
WARNING: The TCP backlog setting of 20480 cannot be enforced because /proc/sys/net/core/somaxconn is set to the lower value of..
```

If so, please consider that newer versions of Redis have their own TCP-backlog value set to `511`, and that you have to increase if you have many connections. In high requests-per-second environments, you need a significant backlog to avoid slow clients connection issues.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">The Linux kernel will silently truncate the TCP-backlog setting to the value of <code>/proc/sys/net/core/somaxconn</code>. So make sure to raise both the value of <code>somaxconn</code> and <code>tcp_max_syn_backlog</code>, to get the desired effect.</td></tr></tbody></table>

To fix this warning, set the value of `net.core.somaxconn` to `65535` in `/etc/rc.local`, so that it persists upon reboot, by running the following command.

```bash
sudo echo sysctl -w net.core.somaxconn=65535 >> /etc/rc.local
```

After the next reboot, 65535 connections will be allowed, instead of the default value.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#transparent-huge-pages-thp)Transparent Huge Pages (THP)

If you are experiencing latency problems with Redis, the following warning may appear in your Redis logs:

```plaintext
WARNING you have Transparent Huge Pages (THP) support enabled in your kernel.
This creates both latency and memory usage issues with Redis.
```

If so, unfortunately, when a Linux kernel has [Transparent Huge Pages](https://www.kernel.org/doc/Documentation/vm/transhuge.txt) enabled, Redis incurs a significant latency penalty after the fork call is used, to persist information to disk. Transparent Huge Pages are the cause of the following issue:

1.  A fork call is made, resulting in two processes with shared huge pages being created.
    
2.  In a busy instance, a few event loops cause commands to target a few thousand pages, causing the copy-on-write of almost the entire process memory.
    
3.  Big latency and memory usage result.

As a result, make sure to disable Transparent Huge Pages using the following command:

```bash
echo never > /sys/kernel/mm/transparent_hugepage/enabled
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#redis-latency-problems)Redis Latency Problems

If you are having issues with Redis latency, please refer to the [official Redis guide](https://redis.io/topics/latency) on how to handle them.

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#database-tuning)Database Tuning

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#using-mariadbmysql-instead-of-sqlite)Using MariaDB/MySQL Instead of SQLite

MySQL or MariaDB are preferred because of the [performance limitations of SQLite with highly concurrent applications](http://www.sqlite.org/whentouse.html), like ownCloud.

See the section [Linux Database Configuration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html../database/linux_database_configuration.html) for how to configure ownCloud for MySQL or MariaDB. If your installation is already running on SQLite then it is possible to convert to MySQL or MariaDB using the steps provided in [database conversion](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html../database/db_conversion.html).

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#tune-mariadbmysql)Tune MariaDB/MySQL

A comprehensive guide to tuning MySQL and MariaDB is outside the scope of the ownCloud documentation. However, here are three links that can help you find further information:

-   [MySQLTuner](https://github.com/major/MySQLTuner-perl/)
    
-   [Percona Tools for MySQL](https://tools.percona.com/wizard)
    
-   [Optimizing and Tuning MariaDB](https://mariadb.com/kb/en/optimization-and-tuning/)

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#tune-postgresql)Tune PostgreSQL

A comprehensive guide to tuning PostgreSQL is outside the scope of the ownCloud documentation. However, here are three links that can help you find further information:

-   [Five Steps to PostgreSQL Performance](http://de.slideshare.net/PGExperts/five-steps-perform2013)
    
-   [Tuning the autovacuum process for tables with huge update workloads (oc\_filecache)](https://grokbase.com/t/postgresql/pgsql-admin/103qcpdrpf/tuning-auto-vacuum-for-highly-active-tables#20100323hfs3jtjuaywwufukoqtexkpjti)

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#ssl-encryption-app)SSL / Encryption App

SSL (HTTPS) and file encryption/decryption can be offloaded to a processor’s AES-NI extension. This can both speed up these operations while lowering processing overhead. This requires a processor with the [AES-NI instruction set](http://wikipedia.org/wiki/AES_instruction_set).

Here are some examples how to check if your CPU / environment supports the AES-NI extension:

-   For each CPU core present: `grep flags /proc/cpuinfo` or as a summary for all cores: `grep -m 1 ^flags /proc/cpuinfo` If the result contains any `aes`, the extension is present.
    
-   Search e.g. on the Intel web if the processor used supports the extension [Intel Processor Feature Filter](http://ark.intel.com/MySearch.aspx?AESTech=true). You may set a filter by `"AES New Instructions"` to get a reduced result set.
    
-   For versions of openssl >= 1.0.1, AES-NI does not work via an engine and will not show up in the `openssl engine` command. It is active by default on the supported hardware. You can check the openssl version via `openssl version -a`
    
-   If your processor supports AES-NI but it does not show up e.g. via grep or coreinfo, it is maybe disabled in the BIOS.
    
-   If your environment runs virtualized, check the virtualization vendor for support.

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#webserver-tuning)Webserver Tuning

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#tune-apache)Tune Apache

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#enable-http2-support)Enable HTTP/2 Support

If you want to improve the speed of an ownCloud installation, while at the same time increasing its security, you can [enable HTTP/2 support for Apache](https://httpd.apache.org/docs/2.4/howto/http2.html). Please be aware that [most browsers require HTTP/2 to be used with SSL enabled](https://caniuse.com/http2).

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#apache-processes)Apache Processes

An Apache process uses around 12MB of RAM. Apache should be configured so that the maximum number of HTTPD processes times 12MB is lower than the amount of RAM. Otherwise the system begins to swap and the performance goes down.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#use-keepalive)Use KeepAlive

The [KeepAlive](https://en.wikipedia.org/wiki/HTTP_persistent_connection) directive enables persistent HTTP connections, allowing multiple requests to be sent over the same TCP connection. Enabling it reduces latency by as much as 50%. We recommend to keep the KeepAliveTimeout between 3 and 5. Higher numbers can block the Server with inactive connections. In combination with the periodic checks of the sync client the following settings are recommended:

```apache
KeepAlive On
KeepAliveTimeout 3
MaxKeepAliveRequests 200
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#hostname-lookups)Hostname Lookups

```bash
cat /etc/httpd/conf/httpd.conf
```

```plaintext
    ...
HostnameLookups off
```

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/oc_server_tuning.html#log-files)Log Files

Log files should be switched off for maximum performance. To do that, comment out the [CustomLog](https://httpd.apache.org/docs/current/mod/mod_log_config.html#customlog) directive. However, keep [ErrorLog](https://httpd.apache.org/docs/2.4/logs.html#errorlog) set, so errors can be tracked down.
