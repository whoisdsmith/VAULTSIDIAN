---
tags:: notes
created: 2022-07-04T22:14:59 (UTC -04:00)
tags: []
source: https://gist.github.com/rohankhudedev/1a9c0a3c7fb375f295f9fc11aeb116fe
author: rohankhudedev
---

# Best Zend OpCache Settings / Tuning / Configurations

> ## Excerpt
> Best Zend OpCache Settings / Tuning / Configurations - opcache.ini

---
\[opcache\] ; Determines if Zend OPCache is enabled opcache.enable\=1 ; Determines if Zend OPCache is enabled for the CLI version of PHP ;opcache.enable\_cli=1 ; The OPcache shared memory storage size. opcache.memory\_consumption\=512 ; The amount of memory for interned strings in Mbytes. opcache.interned\_strings\_buffer\=64 ; The maximum number of keys (scripts) in the OPcache hash table. ; Only numbers between 200 and 1000000 are allowed. ;If you have multiple PHP sites on the server then consider the value 130986 ; for magento 2, keep 65406 opcache.max\_accelerated\_files\=50000 ; The maximum percentage of "wasted" memory until a restart is scheduled. opcache.max\_wasted\_percentage\=15 ; When this directive is enabled, the OPcache appends the current working ; directory to the script key, thus eliminating possible collisions between ; files with the same name (basename). Disabling the directive improves ; performance, but may break existing applications. ;opcache.use\_cwd=1 ; When disabled, you must reset the OPcache manually or restart the ; webserver for changes to the filesystem to take effect. ; For Development / testing, keep 1 ; For performance / production, keep 0 opcache.validate\_timestamps\=0 ;opcache.revalidate\_freq How often in seconds should the code ;cache expire and check if your code has changed. 0 means it ;checks your PHP code every single request IF YOU HAVE ;opcache.validate\_timestamps ENABLED. opcache.validate\_timestamps ;should not be enabled by default, as long as it's disabled then any value for opcache. ;revalidate\_freq will basically be ignored. You should really only ever enable ;this during development, you don't really want to enable this setting for a production application. opcache.revalidate\_freq\=0 ; Enables or disables file search in include\_path optimization ;opcache.revalidate\_path=0 ; If disabled, all PHPDoc comments are dropped from the code to reduce the ; size of the optimized code. opcache.save\_comments\=1 ; If enabled, a fast shutdown sequence is used for the accelerated code ; Depending on the used Memory Manager this may cause some incompatibilities. opcache.fast\_shutdown\=1 ; Allow file existence override (file\_exists, etc.) performance feature. ;opcache.enable\_file\_override=0 ; A bitmask, where each bit enables or disables the appropriate OPcache ; passes ;opcache.optimization\_level=0xffffffff ;opcache.inherited\_hack=1 ;opcache.dups\_fix=0 ; The location of the OPcache blacklist file (wildcards allowed). ; Each OPcache blacklist file is a text file that holds the names of files ; that should not be accelerated. The file format is to add each filename ; to a new line. The filename may be a full path or just a file prefix ; (i.e., /var/www/x blacklists all the files and directories in /var/www ; that start with 'x'). Line starting with a ; are ignored (comments). ;opcache.blacklist\_filename= ; Allows exclusion of large files from being cached. By default all files ; are cached. ;opcache.max\_file\_size=0 ; Check the cache checksum each N requests. ; The default value of "0" means that the checks are disabled. ;opcache.consistency\_checks=0 ; How long to wait (in seconds) for a scheduled restart to begin if the cache ; is not being accessed. ;opcache.force\_restart\_timeout=180 ; OPcache error\_log file name. Empty string assumes "stderr". ;opcache.error\_log= ; All OPcache errors go to the Web server log. ; By default, only fatal errors (level 0) or errors (level 1) are logged. ; You can also enable warnings (level 2), info messages (level 3) or ; debug messages (level 4). ;opcache.log\_verbosity\_level=1 ; Preferred Shared Memory back-end. Leave empty and let the system decide. ;opcache.preferred\_memory\_model= ; Protect the shared memory from unexpected writing during script execution. ; Useful for internal debugging only. ;opcache.protect\_memory=0 ; Allows calling OPcache API functions only from PHP scripts which path is ; started from specified string. The default "" means no restriction ;opcache.restrict\_api= ; Mapping base of shared memory segments (for Windows only). All the PHP ; processes have to map shared memory into the same address space. This ; directive allows to manually fix the "Unable to reattach to base address" ; errors. opcache.mmap\_base\=0x20000000 ; Enables and sets the second level cache directory. ; It should improve performance when SHM memory is full, at server restart or ; SHM reset. The default "" disables file based caching. ;opcache.file\_cache= ; Enables or disables opcode caching in shared memory. ;opcache.file\_cache\_only=0 ; Enables or disables checksum validation when script loaded from file cache. ;opcache.file\_cache\_consistency\_checks=1 ; Implies opcache.file\_cache\_only=1 for a certain process that failed to ; reattach to the shared memory (for Windows only). Explicitly enabled file ; cache is required. opcache.file\_cache\_fallback\=1 ; Enables or disables copying of PHP code (text segment) into HUGE PAGES. ; This should improve performance, but requires appropriate OS configuration. ;opcache.huge\_code\_pages=1 ; Validate cached file permissions. ; opcache.validate\_permission=0 ; Prevent name collisions in chroot'ed environment. ; opcache.validate\_root=0