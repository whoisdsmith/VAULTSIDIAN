---
created: 2022-07-14T13:17:00 (UTC -04:00)
tags: []
source: https://cloud9.ctrlaltback.space/index.php/apps/occweb/
author: 
---

# OCCWeb - CLOUD9

> ## Excerpt

> CLOUD9 24.0.1

---
CLOUD9 24.0.1

\=============

\* \[\`check\`\](#check)

\* \[\`help\`\](#help)

\* \[\`list\`\](#list)

\* \[\`status\`\](#status)

\* \[\`upgrade\`\](#upgrade)

\*\*app:\*\*

\* \[\`app:check-code\`\](#appcheck-code)

\* \[\`app:disable\`\](#appdisable)

\* \[\`app:enable\`\](#appenable)

\* \[\`app:getpath\`\](#appgetpath)

\* \[\`app:install\`\](#appinstall)

\* \[\`app:list\`\](#applist)

\* \[\`app:remove\`\](#appremove)

\* \[\`app:update\`\](#appupdate)

\*\*audioplayer:\*\*

\* \[\`audioplayer:reset\`\](#audioplayerreset)

\* \[\`audioplayer:scan\`\](#audioplayerscan)

\*\*background:\*\*

\* \[\`background:ajax\`\](#backgroundajax)

\* \[\`background:cron\`\](#backgroundcron)

\* \[\`background:webcron\`\](#backgroundwebcron)

\*\*background-job:\*\*

\* \[\`background-job:execute\`\](#background-jobexecute)

\*\*broadcast:\*\*

\* \[\`broadcast:test\`\](#broadcasttest)

\*\*config:\*\*

\* \[\`config:app:delete\`\](#configappdelete)

\* \[\`config:app:get\`\](#configappget)

\* \[\`config:app:set\`\](#configappset)

\* \[\`config:import\`\](#configimport)

\* \[\`config:list\`\](#configlist)

\* \[\`config:system:delete\`\](#configsystemdelete)

\* \[\`config:system:get\`\](#configsystemget)

\* \[\`config:system:set\`\](#configsystemset)

\*\*dav:\*\*

\* \[\`dav:create-addressbook\`\](#davcreate-addressbook)

\* \[\`dav:create-calendar\`\](#davcreate-calendar)

\* \[\`dav:delete-calendar\`\](#davdelete-calendar)

\* \[\`dav:list-calendars\`\](#davlist-calendars)

\* \[\`dav:move-calendar\`\](#davmove-calendar)

\* \[\`dav:remove-invalid-shares\`\](#davremove-invalid-shares)

\* \[\`dav:retention:clean-up\`\](#davretentionclean-up)

\* \[\`dav:send-event-reminders\`\](#davsend-event-reminders)

\* \[\`dav:sync-birthday-calendar\`\](#davsync-birthday-calendar)

\* \[\`dav:sync-system-addressbook\`\](#davsync-system-addressbook)

\*\*db:\*\*

\* \[\`db:add-missing-columns\`\](#dbadd-missing-columns)

\* \[\`db:add-missing-indices\`\](#dbadd-missing-indices)

\* \[\`db:add-missing-primary-keys\`\](#dbadd-missing-primary-keys)

\* \[\`db:convert-filecache-bigint\`\](#dbconvert-filecache-bigint)

\* \[\`db:convert-mysql-charset\`\](#dbconvert-mysql-charset)

\* \[\`db:convert-type\`\](#dbconvert-type)

\*\*duplicates:\*\*

\* \[\`duplicates:clear\`\](#duplicatesclear)

\* \[\`duplicates:find-all\`\](#duplicatesfind-all)

\* \[\`duplicates:list\`\](#duplicateslist)

\*\*encryption:\*\*

\* \[\`encryption:change-key-storage-root\`\](#encryptionchange-key-storage-root)

\* \[\`encryption:decrypt-all\`\](#encryptiondecrypt-all)

\* \[\`encryption:disable\`\](#encryptiondisable)

\* \[\`encryption:enable\`\](#encryptionenable)

\* \[\`encryption:encrypt-all\`\](#encryptionencrypt-all)

\* \[\`encryption:list-modules\`\](#encryptionlist-modules)

\* \[\`encryption:migrate-key-storage-format\`\](#encryptionmigrate-key-storage-format)

\* \[\`encryption:set-default-module\`\](#encryptionset-default-module)

\* \[\`encryption:show-key-storage-root\`\](#encryptionshow-key-storage-root)

\* \[\`encryption:status\`\](#encryptionstatus)

\*\*files:\*\*

\* \[\`files:cleanup\`\](#filescleanup)

\* \[\`files:repair-tree\`\](#filesrepair-tree)

\* \[\`files:scan\`\](#filesscan)

\* \[\`files:scan-app-data\`\](#filesscan-app-data)

\* \[\`files:transfer-ownership\`\](#filestransfer-ownership)

\*\*group:\*\*

\* \[\`group:add\`\](#groupadd)

\* \[\`group:adduser\`\](#groupadduser)

\* \[\`group:delete\`\](#groupdelete)

\* \[\`group:info\`\](#groupinfo)

\* \[\`group:list\`\](#grouplist)

\* \[\`group:removeuser\`\](#groupremoveuser)

\*\*groupfolders:\*\*

\* \[\`groupfolders:create\`\](#groupfolderscreate)

\* \[\`groupfolders:delete\`\](#groupfoldersdelete)

\* \[\`groupfolders:expire\`\](#groupfoldersexpire)

\* \[\`groupfolders:group\`\](#groupfoldersgroup)

\* \[\`groupfolders:list\`\](#groupfolderslist)

\* \[\`groupfolders:permissions\`\](#groupfolderspermissions)

\* \[\`groupfolders:quota\`\](#groupfoldersquota)

\* \[\`groupfolders:rename\`\](#groupfoldersrename)

\* \[\`groupfolders:scan\`\](#groupfoldersscan)

\* \[\`groupfolders:trashbin:cleanup\`\](#groupfolderstrashbincleanup)

\*\*integrity:\*\*

\* \[\`integrity:check-app\`\](#integritycheck-app)

\* \[\`integrity:check-core\`\](#integritycheck-core)

\* \[\`integrity:sign-app\`\](#integritysign-app)

\* \[\`integrity:sign-core\`\](#integritysign-core)

\*\*l10n:\*\*

\* \[\`l10n:createjs\`\](#l10ncreatejs)

\*\*log:\*\*

\* \[\`log:file\`\](#logfile)

\* \[\`log:manage\`\](#logmanage)

\* \[\`log:tail\`\](#logtail)

\* \[\`log:watch\`\](#logwatch)

\*\*maintenance:\*\*

\* \[\`maintenance:data-fingerprint\`\](#maintenancedata-fingerprint)

\* \[\`maintenance:mimetype:update-db\`\](#maintenancemimetypeupdate-db)

\* \[\`maintenance:mimetype:update-js\`\](#maintenancemimetypeupdate-js)

\* \[\`maintenance:mode\`\](#maintenancemode)

\* \[\`maintenance:repair\`\](#maintenancerepair)

\* \[\`maintenance:theme:update\`\](#maintenancethemeupdate)

\* \[\`maintenance:update:htaccess\`\](#maintenanceupdatehtaccess)

\*\*music:\*\*

\* \[\`music:cleanup\`\](#musiccleanup)

\* \[\`music:playlist-export\`\](#musicplaylist-export)

\* \[\`music:playlist-import\`\](#musicplaylist-import)

\* \[\`music:podcast-add\`\](#musicpodcast-add)

\* \[\`music:podcast-reset\`\](#musicpodcast-reset)

\* \[\`music:podcast-update\`\](#musicpodcast-update)

\* \[\`music:reset-cache\`\](#musicreset-cache)

\* \[\`music:reset-database\`\](#musicreset-database)

\* \[\`music:scan\`\](#musicscan)

\*\*notification:\*\*

\* \[\`notification:generate\`\](#notificationgenerate)

\* \[\`notification:test-push\`\](#notificationtest-push)

\*\*preview:\*\*

\* \[\`preview:generate-all\`\](#previewgenerate-all)

\* \[\`preview:pre-generate\`\](#previewpre-generate)

\* \[\`preview:repair\`\](#previewrepair)

\* \[\`preview:reset-rendered-texts\`\](#previewreset-rendered-texts)

\*\*security:\*\*

\* \[\`security:bruteforce:reset\`\](#securitybruteforcereset)

\* \[\`security:certificates\`\](#securitycertificates)

\* \[\`security:certificates:import\`\](#securitycertificatesimport)

\* \[\`security:certificates:remove\`\](#securitycertificatesremove)

\*\*serverinfo:\*\*

\* \[\`serverinfo:update-storage-statistics\`\](#serverinfoupdate-storage-statistics)

\*\*sharing:\*\*

\* \[\`sharing:cleanup-remote-storages\`\](#sharingcleanup-remote-storages)

\* \[\`sharing:expiration-notification\`\](#sharingexpiration-notification)

\*\*tag:\*\*

\* \[\`tag:add\`\](#tagadd)

\* \[\`tag:delete\`\](#tagdelete)

\* \[\`tag:edit\`\](#tagedit)

\* \[\`tag:list\`\](#taglist)

\*\*text:\*\*

\* \[\`text:reset\`\](#textreset)

\*\*theming:\*\*

\* \[\`theming:config\`\](#themingconfig)

\*\*trashbin:\*\*

\* \[\`trashbin:cleanup\`\](#trashbincleanup)

\* \[\`trashbin:expire\`\](#trashbinexpire)

\* \[\`trashbin:restore\`\](#trashbinrestore)

\* \[\`trashbin:size\`\](#trashbinsize)

\*\*twofactorauth:\*\*

\* \[\`twofactorauth:cleanup\`\](#twofactorauthcleanup)

\* \[\`twofactorauth:disable\`\](#twofactorauthdisable)

\* \[\`twofactorauth:enable\`\](#twofactorauthenable)

\* \[\`twofactorauth:enforce\`\](#twofactorauthenforce)

\* \[\`twofactorauth:state\`\](#twofactorauthstate)

\*\*update:\*\*

\* \[\`update:check\`\](#updatecheck)

\*\*usage-report:\*\*

\* \[\`usage-report:generate\`\](#usage-reportgenerate)

\*\*user:\*\*

\* \[\`user:add\`\](#useradd)

\* \[\`user:add-app-password\`\](#useradd-app-password)

\* \[\`user:delete\`\](#userdelete)

\* \[\`user:disable\`\](#userdisable)

\* \[\`user:enable\`\](#userenable)

\* \[\`user:export\`\](#userexport)

\* \[\`user:import\`\](#userimport)

\* \[\`user:info\`\](#userinfo)

\* \[\`user:lastseen\`\](#userlastseen)

\* \[\`user:list\`\](#userlist)

\* \[\`user:report\`\](#userreport)

\* \[\`user:resetpassword\`\](#userresetpassword)

\* \[\`user:setting\`\](#usersetting)

\*\*versions:\*\*

\* \[\`versions:cleanup\`\](#versionscleanup)

\* \[\`versions:expire\`\](#versionsexpire)

\*\*workflows:\*\*

\* \[\`workflows:list\`\](#workflowslist)

\`check\`

\-------

check dependencies of the server environment

###  Usage

\* \`check \[--output \[OUTPUT\]\]\`

check dependencies of the server environment

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`help\`

\------

Display help for a command

###  Usage

\* \`help \[--format FORMAT\] \[--raw\] \[--\] \[<command\_name>\]\`

The help command displays help for a given command:

  php /index.php help list

You can also output the help in other formats by using the --format option:

  php /index.php help --format=xml list

To display the list of available commands, please use the list command.

###  Arguments

####  \`command\_name\`

The command name

\* Is required: no

\* Is array: no

\* Default: \`'help'\`

###  Options

####  \`--format\`

The output format (txt, xml, json, or md)

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`'txt'\`

####  \`--raw\`

To output raw command help

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`list\`

\------

List commands

###  Usage

\* \`list \[--raw\] \[--format FORMAT\] \[--\] \[<namespace>\]\`

The list command lists all commands:

  php /index.php list

You can also display the commands for a specific namespace:

  php /index.php list test

You can also output the information in other formats by using the --format option:

  php /index.php list --format=xml

It's also possible to get raw list of commands (useful for embedding command runner):

  php /index.php list --raw

###  Arguments

####  \`namespace\`

The namespace name

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--raw\`

To output raw command list

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--format\`

The output format (txt, xml, json, or md)

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`'txt'\`

\`status\`

\--------

show some status information

###  Usage

\* \`status \[--output \[OUTPUT\]\]\`

show some status information

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`upgrade\`

\---------

run upgrade routines after installation of a new release. The release has to be installed before.

###  Usage

\* \`upgrade\`

run upgrade routines after installation of a new release. The release has to be installed before.

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`app:check-code\`

\----------------

check code to be compliant

###  Usage

\* \`app:check-code \[-c|--checker CHECKER\] \[--skip-checkers\] \[--skip-validate-info\] \[--\] <app-id>\`

check code to be compliant

###  Arguments

####  \`app-id\`

check the specified app

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--checker|-c\`

enable the specified checker(s)

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array (  0 => 'private',  1 => 'deprecation',  2 => 'strong-comparison',)\`

####  \`--skip-checkers\`

skips the the code checkers to only check info.xml, language and database schema

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--skip-validate-info\`

skips the info.xml/version check

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`app:disable\`

\-------------

disable an app

###  Usage

\* \`app:disable <app-id>...\`

disable an app

###  Arguments

####  \`app-id\`

disable the specified app

\* Is required: yes

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`app:enable\`

\------------

enable an app

###  Usage

\* \`app:enable \[-g|--groups GROUPS\] \[-f|--force\] \[--\] <app-id>...\`

enable an app

###  Arguments

####  \`app-id\`

enable the specified app

\* Is required: yes

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--groups|-g\`

enable the app only for a list of groups

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--force|-f\`

enable the app regardless of the Nextcloud version requirement

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`app:getpath\`

\-------------

Get an absolute path to the app directory

###  Usage

\* \`app:getpath \[--output \[OUTPUT\]\] \[--\] <app>\`

Get an absolute path to the app directory

###  Arguments

####  \`app\`

Name of the app

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`app:install\`

\-------------

install an app

###  Usage

\* \`app:install \[--keep-disabled\] \[-f|--force\] \[--allow-unstable\] \[--\] <app-id>\`

install an app

###  Arguments

####  \`app-id\`

install the specified app

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--keep-disabled\`

don't enable the app afterwards

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--force|-f\`

install the app regardless of the Nextcloud version requirement

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--allow-unstable\`

allow installing an unstable releases

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`app:list\`

\----------

List all available apps

###  Usage

\* \`app:list \[--output \[OUTPUT\]\] \[--shipped SHIPPED\]\`

List all available apps

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--shipped\`

true - limit to shipped apps only, false - limit to non-shipped apps only

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`app:remove\`

\------------

remove an app

###  Usage

\* \`app:remove \[--keep-data\] \[--\] <app-id>\`

remove an app

###  Arguments

####  \`app-id\`

remove the specified app

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--keep-data\`

keep app data and do not remove them

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`app:update\`

\------------

update an app or all apps

###  Usage

\* \`app:update \[--all\] \[--showonly\] \[--allow-unstable\] \[--\] \[<app-id>\]\`

update an app or all apps

###  Arguments

####  \`app-id\`

update the specified app

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--all\`

update all updatable apps

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--showonly\`

show update(s) without updating

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--allow-unstable\`

allow updating to unstable releases

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`audioplayer:reset\`

\-------------------

reset audio player library

###  Usage

\* \`audioplayer:reset \[--all\] \[--\] \[<user\_id>...\]\`

reset audio player library

###  Arguments

####  \`user\_id\`

reset the whole library of the given user(s)

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

reset the whole library of all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`audioplayer:scan\`

\------------------

scan for new audio files; use -v for debugging

###  Usage

\* \`audioplayer:scan \[--all\] \[--\] \[<user\_id>...\]\`

scan for new audio files; use -v for debugging

###  Arguments

####  \`user\_id\`

scan all audio files of the given user(s)

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

scan all audio files of all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`background:ajax\`

\-----------------

Use ajax to run background jobs

###  Usage

\* \`background:ajax\`

Use ajax to run background jobs

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`background:cron\`

\-----------------

Use cron to run background jobs

###  Usage

\* \`background:cron\`

Use cron to run background jobs

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`background:webcron\`

\--------------------

Use webcron to run background jobs

###  Usage

\* \`background:webcron\`

Use webcron to run background jobs

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`background-job:execute\`

\------------------------

Execute a single background job manually

###  Usage

\* \`background-job:execute \[--force-execute\] \[--\] <job-id>\`

Execute a single background job manually

###  Arguments

####  \`job-id\`

The ID of the job in the database

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--force-execute\`

Force execute the background job, independent from last run and being reserved

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`broadcast:test\`

\----------------

test the SSE broadcaster

###  Usage

\* \`broadcast:test <uid> \[<name>\]\`

test the SSE broadcaster

###  Arguments

####  \`uid\`

the UID of the users to receive the event

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`name\`

the event name

\* Is required: no

\* Is array: no

\* Default: \`'test'\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`config:app:delete\`

\-------------------

Delete an app config value

###  Usage

\* \`config:app:delete \[--output \[OUTPUT\]\] \[--error-if-not-exists\] \[--\] <app> <name>\`

Delete an app config value

###  Arguments

####  \`app\`

Name of the app

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`name\`

Name of the config to delete

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--error-if-not-exists\`

Checks whether the config exists before deleting it

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`config:app:get\`

\----------------

Get an app config value

###  Usage

\* \`config:app:get \[--output \[OUTPUT\]\] \[--default-value \[DEFAULT-VALUE\]\] \[--\] <app> <name>\`

Get an app config value

###  Arguments

####  \`app\`

Name of the app

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`name\`

Name of the config to get

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--default-value\`

If no default value is set and the config does not exist, the command will exit with 1

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`config:app:set\`

\----------------

Set an app config value

###  Usage

\* \`config:app:set \[--output \[OUTPUT\]\] \[--value VALUE\] \[--update-only\] \[--\] <app> <name>\`

Set an app config value

###  Arguments

####  \`app\`

Name of the app

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`name\`

Name of the config to set

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--value\`

The new value of the config

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--update-only\`

Only updates the value, if it is not set before, it is not being added

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`config:import\`

\---------------

Import a list of configs

###  Usage

\* \`config:import \[<file>\]\`

Import a list of configs

###  Arguments

####  \`file\`

File with the json array to import

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`config:list\`

\-------------

List all configs

###  Usage

\* \`config:list \[--output \[OUTPUT\]\] \[--private\] \[--\] \[<app>\]\`

List all configs

###  Arguments

####  \`app\`

Name of the app ("system" to get the config.php values, "all" for all apps and system)

\* Is required: no

\* Is array: no

\* Default: \`'all'\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'json\_pretty'\`

####  \`--private\`

Use this option when you want to include sensitive configs like passwords, salts, ...

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`config:system:delete\`

\----------------------

Delete a system config value

###  Usage

\* \`config:system:delete \[--output \[OUTPUT\]\] \[--error-if-not-exists\] \[--\] <name>...\`

Delete a system config value

###  Arguments

####  \`name\`

Name of the config to delete, specify multiple for array parameter

\* Is required: yes

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--error-if-not-exists\`

Checks whether the config exists before deleting it

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`config:system:get\`

\-------------------

Get a system config value

###  Usage

\* \`config:system:get \[--output \[OUTPUT\]\] \[--default-value \[DEFAULT-VALUE\]\] \[--\] <name>...\`

Get a system config value

###  Arguments

####  \`name\`

Name of the config to get, specify multiple for array parameter

\* Is required: yes

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--default-value\`

If no default value is set and the config does not exist, the command will exit with 1

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`config:system:set\`

\-------------------

Set a system config value

###  Usage

\* \`config:system:set \[--output \[OUTPUT\]\] \[--type TYPE\] \[--value VALUE\] \[--update-only\] \[--\] <name>...\`

Set a system config value

###  Arguments

####  \`name\`

Name of the config parameter, specify multiple for array parameter

\* Is required: yes

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--type\`

Value type \[string, integer, double, boolean\]

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`'string'\`

####  \`--value\`

The new value of the config

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--update-only\`

Only updates the value, if it is not set before, it is not being added

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:create-addressbook\`

\------------------------

Create a dav addressbook

###  Usage

\* \`dav:create-addressbook <user> <name>\`

Create a dav addressbook

###  Arguments

####  \`user\`

User for whom the addressbook will be created

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`name\`

Name of the addressbook

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:create-calendar\`

\---------------------

Create a dav calendar

###  Usage

\* \`dav:create-calendar <user> <name>\`

Create a dav calendar

###  Arguments

####  \`user\`

User for whom the calendar will be created

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`name\`

Name of the calendar

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:delete-calendar\`

\---------------------

Delete a dav calendar

###  Usage

\* \`dav:delete-calendar \[--birthday\] \[-f|--force\] \[--\] <uid> \[<name>\]\`

Delete a dav calendar

###  Arguments

####  \`uid\`

User who owns the calendar

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`name\`

Name of the calendar to delete

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--birthday\`

Delete the birthday calendar

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--force|-f\`

Force delete skipping trashbin

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:list-calendars\`

\--------------------

List all calendars of a user

###  Usage

\* \`dav:list-calendars <uid>\`

List all calendars of a user

###  Arguments

####  \`uid\`

User for whom all calendars will be listed

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:move-calendar\`

\-------------------

Move a calendar from an user to another

###  Usage

\* \`dav:move-calendar \[-f|--force\] \[--\] <name> <sourceuid> <destinationuid>\`

Move a calendar from an user to another

###  Arguments

####  \`name\`

Name of the calendar to move

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`sourceuid\`

User who currently owns the calendar

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`destinationuid\`

User who will receive the calendar

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--force|-f\`

Force the migration by removing existing shares and renaming calendars in case of conflicts

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:remove-invalid-shares\`

\---------------------------

Remove invalid dav shares

###  Usage

\* \`dav:remove-invalid-shares\`

Remove invalid dav shares

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:retention:clean-up\`

\------------------------

###  Usage

\* \`dav:retention:clean-up\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:send-event-reminders\`

\--------------------------

Sends event reminders

###  Usage

\* \`dav:send-event-reminders\`

Sends event reminders

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:sync-birthday-calendar\`

\----------------------------

Synchronizes the birthday calendar

###  Usage

\* \`dav:sync-birthday-calendar \[<user>\]\`

Synchronizes the birthday calendar

###  Arguments

####  \`user\`

User for whom the birthday calendar will be synchronized

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`dav:sync-system-addressbook\`

\-----------------------------

Synchronizes users to the system addressbook

###  Usage

\* \`dav:sync-system-addressbook\`

Synchronizes users to the system addressbook

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`db:add-missing-columns\`

\------------------------

Add missing optional columns to the database tables

###  Usage

\* \`db:add-missing-columns \[--dry-run\]\`

Add missing optional columns to the database tables

###  Options

####  \`--dry-run\`

Output the SQL queries instead of running them.

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`db:add-missing-indices\`

\------------------------

Add missing indices to the database tables

###  Usage

\* \`db:add-missing-indices \[--dry-run\]\`

Add missing indices to the database tables

###  Options

####  \`--dry-run\`

Output the SQL queries instead of running them.

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`db:add-missing-primary-keys\`

\-----------------------------

Add missing primary keys to the database tables

###  Usage

\* \`db:add-missing-primary-keys \[--dry-run\]\`

Add missing primary keys to the database tables

###  Options

####  \`--dry-run\`

Output the SQL queries instead of running them.

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`db:convert-filecache-bigint\`

\-----------------------------

Convert the ID columns of the filecache to BigInt

###  Usage

\* \`db:convert-filecache-bigint\`

Convert the ID columns of the filecache to BigInt

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`db:convert-mysql-charset\`

\--------------------------

Convert charset of MySQL/MariaDB to use utf8mb4

###  Usage

\* \`db:convert-mysql-charset\`

Convert charset of MySQL/MariaDB to use utf8mb4

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`db:convert-type\`

\-----------------

Convert the Nextcloud database to the newly configured one

###  Usage

\* \`db:convert-type \[--port PORT\] \[--password PASSWORD\] \[--clear-schema\] \[--all-apps\] \[--chunk-size CHUNK-SIZE\] \[--\] <type> <username> <hostname> <

database>\`

Convert the Nextcloud database to the newly configured one

###  Arguments

####  \`type\`

the type of the database to convert to

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`username\`

the username of the database to convert to

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`hostname\`

the hostname of the database to convert to

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`database\`

the name of the database to convert to

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--port\`

the port of the database to convert to

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--password\`

the password of the database to convert to. Will be asked when not specified. Can also be passed via stdin.

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--clear-schema\`

remove all tables from the destination database

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--all-apps\`

whether to create schema for all apps instead of only installed apps

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--chunk-size\`

the maximum number of database rows to handle in a single query, bigger tables will be handled in chunks of this size. Lower this if the process r

uns out of memory during conversion.

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`'1000'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`duplicates:clear\`

\------------------

Clear all duplicates and information for discovery

###  Usage

\* \`duplicates:clear \[-f|--force\] \[--output \[OUTPUT\]\]\`

Remove links to interactively recognized duplicate files from the database of your Nextcloud instance.

This action doesn't remove the files from your file system.

###  Options

####  \`--force|-f\`

don't ask any questions

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`duplicates:find-all\`

\---------------------

Find all duplicates files

###  Usage

\* \`duplicates:find-all \[-u|--user USER\] \[-p|--path PATH\] \[--output \[OUTPUT\]\]\`

Find all duplicates files

###  Options

####  \`--user|-u\`

scan files of the specified user

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--path|-p\`

limit scan to this path, eg. --path="./Photos"

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`duplicates:list\`

\-----------------

List all duplicates files

###  Usage

\* \`duplicates:list \[-u|--user USER\] \[--output \[OUTPUT\]\]\`

List all duplicates files

###  Options

####  \`--user|-u\`

scan files of the specified user

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:change-key-storage-root\`

\------------------------------------

Change key storage root

###  Usage

\* \`encryption:change-key-storage-root \[<newRoot>\]\`

Change key storage root

###  Arguments

####  \`newRoot\`

new root of the key storage relative to the data folder

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:decrypt-all\`

\------------------------

Disable server-side encryption and decrypt all files

###  Usage

\* \`encryption:decrypt-all \[<user>\]\`

This will disable server-side encryption and decrypt all files for all users if it is supported by your encryption module. Please make sure that n

o user access his files during this process!

###  Arguments

####  \`user\`

user for which you want to decrypt all files (optional)

\* Is required: no

\* Is array: no

\* Default: \`''\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:disable\`

\--------------------

Disable encryption

###  Usage

\* \`encryption:disable\`

Disable encryption

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:enable\`

\-------------------

Enable encryption

###  Usage

\* \`encryption:enable\`

Enable encryption

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:encrypt-all\`

\------------------------

Encrypt all files for all users

###  Usage

\* \`encryption:encrypt-all\`

This will encrypt all files for all users. Please make sure that no user access his files during this process!

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:list-modules\`

\-------------------------

List all available encryption modules

###  Usage

\* \`encryption:list-modules \[--output \[OUTPUT\]\]\`

List all available encryption modules

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:migrate-key-storage-format\`

\---------------------------------------

Migrate the format of the keystorage to a newer format

###  Usage

\* \`encryption:migrate-key-storage-format\`

Migrate the format of the keystorage to a newer format

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:set-default-module\`

\-------------------------------

Set the encryption default module

###  Usage

\* \`encryption:set-default-module <module>\`

Set the encryption default module

###  Arguments

####  \`module\`

ID of the encryption module that should be used

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:show-key-storage-root\`

\----------------------------------

Show current key storage root

###  Usage

\* \`encryption:show-key-storage-root\`

Show current key storage root

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`encryption:status\`

\-------------------

Lists the current status of encryption

###  Usage

\* \`encryption:status \[--output \[OUTPUT\]\]\`

Lists the current status of encryption

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`files:cleanup\`

\---------------

cleanup filecache

###  Usage

\* \`files:cleanup\`

cleanup filecache

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`files:repair-tree\`

\-------------------

Try and repair malformed filesystem tree structures

###  Usage

\* \`files:repair-tree \[--dry-run\]\`

Try and repair malformed filesystem tree structures

###  Options

####  \`--dry-run\`

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`files:scan\`

\------------

rescan filesystem

###  Usage

\* \`files:scan \[--output \[OUTPUT\]\] \[-p|--path PATH\] \[--all\] \[--unscanned\] \[--shallow\] \[--home-only\] \[--\] \[<user\_id>...\]\`

rescan filesystem

###  Arguments

####  \`user\_id\`

will rescan all files of the given user(s)

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--path|-p\`

limit rescan to this path, eg. --path="/alice/files/Music", the user\_id is determined by the path and the user\_id parameter and --all are ignored

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--all\`

will rescan all files of all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--unscanned\`

only scan files which are marked as not fully scanned

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--shallow\`

do not scan folders recursively

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--home-only\`

only scan the home storage, ignoring any mounted external storage or share

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`files:scan-app-data\`

\---------------------

rescan the AppData folder

###  Usage

\* \`files:scan-app-data \[--output \[OUTPUT\]\] \[--\] \[<folder>\]\`

rescan the AppData folder

###  Arguments

####  \`folder\`

The appdata subfolder to scan

\* Is required: no

\* Is array: no

\* Default: \`''\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`files:transfer-ownership\`

\--------------------------

All files and folders are moved to another user - outgoing shares and incoming user file shares (optionally) are moved as well.

###  Usage

\* \`files:transfer-ownership \[--path PATH\] \[--move\] \[--transfer-incoming-shares \[TRANSFER-INCOMING-SHARES\]\] \[--\] <source-user> <destination-user>\`

All files and folders are moved to another user - outgoing shares and incoming user file shares (optionally) are moved as well.

###  Arguments

####  \`source-user\`

owner of files which shall be moved

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`destination-user\`

user who will be the new owner of the files

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--path\`

selectively provide the path to transfer. For example --path="folder\_name"

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`''\`

####  \`--move\`

move data from source user to root directory of destination user, which must be empty

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--transfer-incoming-shares\`

transfer incoming user file shares to destination user. Usage: --transfer-incoming-shares=1 (value required)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'2'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`group:add\`

\-----------

Add a group

###  Usage

\* \`group:add \[--display-name DISPLAY-NAME\] \[--\] <groupid>\`

Add a group

###  Arguments

####  \`groupid\`

Group id

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--display-name\`

Group name used in the web UI (can contain any characters)

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`group:adduser\`

\---------------

add a user to a group

###  Usage

\* \`group:adduser <group> <user>\`

add a user to a group

###  Arguments

####  \`group\`

group to add the user to

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`user\`

user to add to the group

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`group:delete\`

\--------------

Remove a group

###  Usage

\* \`group:delete <groupid>\`

Remove a group

###  Arguments

####  \`groupid\`

Group name

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`group:info\`

\------------

Show information about a group

###  Usage

\* \`group:info \[--output \[OUTPUT\]\] \[--\] <groupid>\`

Show information about a group

###  Arguments

####  \`groupid\`

Group id

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`group:list\`

\------------

list configured groups

###  Usage

\* \`group:list \[-l|--limit \[LIMIT\]\] \[-o|--offset \[OFFSET\]\] \[-i|--info\] \[--output \[OUTPUT\]\]\`

list configured groups

###  Options

####  \`--limit|-l\`

Number of groups to retrieve

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'500'\`

####  \`--offset|-o\`

Offset for retrieving groups

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'0'\`

####  \`--info|-i\`

Show additional info (backend)

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`group:removeuser\`

\------------------

remove a user from a group

###  Usage

\* \`group:removeuser <group> <user>\`

remove a user from a group

###  Arguments

####  \`group\`

group to remove the user from

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`user\`

user to remove from the group

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:create\`

\---------------------

Create a new group folder

###  Usage

\* \`groupfolders:create \[--output \[OUTPUT\]\] \[--\] <name>\`

Create a new group folder

###  Arguments

####  \`name\`

Name of the new folder

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:delete\`

\---------------------

Delete group folder

###  Usage

\* \`groupfolders:delete \[-f|--force\] \[--output \[OUTPUT\]\] \[--\] <folder\_id>\`

Delete group folder

###  Arguments

####  \`folder\_id\`

Id of the folder to rename

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--force|-f\`

Skip confirmation

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:expire\`

\---------------------

Trigger expiry of versions and trashbin for files stored in group folders

###  Usage

\* \`groupfolders:expire \[--output \[OUTPUT\]\]\`

Trigger expiry of versions and trashbin for files stored in group folders

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:group\`

\--------------------

Edit the groups that have access to a group folder

###  Usage

\* \`groupfolders:group \[-d|--delete\] \[--output \[OUTPUT\]\] \[--\] <folder\_id> <group> \[<permissions>...\]\`

Edit the groups that have access to a group folder

###  Arguments

####  \`folder\_id\`

Id of the folder to configure

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`group\`

The group to configure

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`permissions\`

The permissions to set for the group, leave empty for read only

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--delete|-d\`

Remove access for the group

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:list\`

\-------------------

List the configured group folders

###  Usage

\* \`groupfolders:list \[--output \[OUTPUT\]\]\`

List the configured group folders

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:permissions\`

\--------------------------

Configure advanced permissions for a configured group folder

###  Usage

\* \`groupfolders:permissions \[-e|--enable\] \[-d|--disable\] \[-m|--manage-add\] \[-r|--manage-remove\] \[-u|--user USER\] \[-g|--group GROUP\] \[-t|--test\] \[-

\-output \[OUTPUT\]\] \[--\] <folder\_id> \[<path> \[<permissions>...\]\]\`

Configure advanced permissions for a configured group folder

###  Arguments

####  \`folder\_id\`

Id of the folder to configure

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`path\`

The path within the folder to set permissions for

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

####  \`permissions\`

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--enable|-e\`

Enable advanced permissions for the folder

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--disable|-d\`

Disable advanced permissions for the folder

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--manage-add|-m\`

Add manage permission for user or group

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--manage-remove|-r\`

Remove manage permission for user or group

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--user|-u\`

The user to configure the permissions for

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--group|-g\`

The group to configure the permissions for

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--test|-t\`

Test the permissions for the set path

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:quota\`

\--------------------

Edit the quota of a configured group folder

###  Usage

\* \`groupfolders:quota \[--output \[OUTPUT\]\] \[--\] <folder\_id> <quota>\`

Edit the quota of a configured group folder

###  Arguments

####  \`folder\_id\`

Id of the folder to configure

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`quota\`

New value for the quota of the folder

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:rename\`

\---------------------

Rename group folder

###  Usage

\* \`groupfolders:rename \[--output \[OUTPUT\]\] \[--\] <folder\_id> <name>\`

Rename group folder

###  Arguments

####  \`folder\_id\`

Id of the folder to rename

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`name\`

New value name of the folder

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:scan\`

\-------------------

Scan a group folder for outside changes

###  Usage

\* \`groupfolders:scan \[--output \[OUTPUT\]\] \[--\] <folder\_id>\`

Scan a group folder for outside changes

###  Arguments

####  \`folder\_id\`

Id of the folder to configure

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`groupfolders:trashbin:cleanup\`

\-------------------------------

Empty the groupfolder trashbin

###  Usage

\* \`groupfolders:trashbin:cleanup \[-f|--force\] \[--output \[OUTPUT\]\] \[--\] \[<folder\_id>\]\`

Empty the groupfolder trashbin

###  Arguments

####  \`folder\_id\`

Id of the groupfolder

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--force|-f\`

Skip confirmation

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`integrity:check-app\`

\---------------------

Check integrity of an app using a signature.

###  Usage

\* \`integrity:check-app \[--output \[OUTPUT\]\] \[--path \[PATH\]\] \[--\] <appid>\`

Check integrity of an app using a signature.

###  Arguments

####  \`appid\`

Application to check

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--path\`

Path to application. If none is given it will be guessed.

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`integrity:check-core\`

\----------------------

Check integrity of core code using a signature.

###  Usage

\* \`integrity:check-core \[--output \[OUTPUT\]\]\`

Check integrity of core code using a signature.

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`integrity:sign-app\`

\--------------------

Signs an app using a private key.

###  Usage

\* \`integrity:sign-app \[--path PATH\] \[--privateKey PRIVATEKEY\] \[--certificate CERTIFICATE\]\`

Signs an app using a private key.

###  Options

####  \`--path\`

Application to sign

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--privateKey\`

Path to private key to use for signing

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--certificate\`

Path to certificate to use for signing

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`integrity:sign-core\`

\---------------------

Sign core using a private key.

###  Usage

\* \`integrity:sign-core \[--privateKey PRIVATEKEY\] \[--certificate CERTIFICATE\] \[--path PATH\]\`

Sign core using a private key.

###  Options

####  \`--privateKey\`

Path to private key to use for signing

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--certificate\`

Path to certificate to use for signing

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--path\`

Path of core to sign

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`l10n:createjs\`

\---------------

Create javascript translation files for a given app

###  Usage

\* \`l10n:createjs \[<app> \[<lang>...\]\]\`

Create javascript translation files for a given app

###  Arguments

####  \`app\`

name of the app

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

####  \`lang\`

name of the language

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`log:file\`

\----------

manipulate logging backend

###  Usage

\* \`log:file \[--enable\] \[--file FILE\] \[--rotate-size ROTATE-SIZE\]\`

manipulate logging backend

###  Options

####  \`--enable\`

enable this logging backend

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--file\`

set the log file path

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--rotate-size\`

set the file size for log rotation, 0 = disabled

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`log:manage\`

\------------

manage logging configuration

###  Usage

\* \`log:manage \[--backend BACKEND\] \[--level LEVEL\] \[--timezone TIMEZONE\]\`

manage logging configuration

###  Options

####  \`--backend\`

set the logging backend \[file, syslog, errorlog, systemd\]

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--level\`

set the log level \[debug, info, warning, error, fatal\]

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--timezone\`

set the logging timezone

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`log:tail\`

\----------

Tail the nextcloud logfile

###  Usage

\* \`log:tail \[-f|--follow\] \[--output \[OUTPUT\]\] \[--\] \[<lines>\]\`

Tail the nextcloud logfile

###  Arguments

####  \`lines\`

The number of log entries to print

\* Is required: no

\* Is array: no

\* Default: \`'10'\`

###  Options

####  \`--follow|-f\`

Output new log entries as they appear

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`log:watch\`

\-----------

Watch the nextcloud logfile

###  Usage

\* \`log:watch \[--output \[OUTPUT\]\]\`

Watch the nextcloud logfile

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`maintenance:data-fingerprint\`

\------------------------------

update the systems data-fingerprint after a backup is restored

###  Usage

\* \`maintenance:data-fingerprint\`

update the systems data-fingerprint after a backup is restored

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`maintenance:mimetype:update-db\`

\--------------------------------

Update database mimetypes and update filecache

###  Usage

\* \`maintenance:mimetype:update-db \[--repair-filecache\]\`

Update database mimetypes and update filecache

###  Options

####  \`--repair-filecache\`

Repair filecache for all mimetypes, not just new ones

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`maintenance:mimetype:update-js\`

\--------------------------------

Update mimetypelist.js

###  Usage

\* \`maintenance:mimetype:update-js\`

Update mimetypelist.js

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`maintenance:mode\`

\------------------

set maintenance mode

###  Usage

\* \`maintenance:mode \[--on\] \[--off\]\`

set maintenance mode

###  Options

####  \`--on\`

enable maintenance mode

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--off\`

disable maintenance mode

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`maintenance:repair\`

\--------------------

repair this installation

###  Usage

\* \`maintenance:repair \[--include-expensive\]\`

repair this installation

###  Options

####  \`--include-expensive\`

Use this option when you want to include resource and load expensive tasks

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`maintenance:theme:update\`

\--------------------------

Apply custom theme changes

###  Usage

\* \`maintenance:theme:update\`

Apply custom theme changes

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`maintenance:update:htaccess\`

\-----------------------------

Updates the .htaccess file

###  Usage

\* \`maintenance:update:htaccess\`

Updates the .htaccess file

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:cleanup\`

\---------------

clean up orphaned DB entries (this happens also periodically on the background)

###  Usage

\* \`music:cleanup\`

clean up orphaned DB entries (this happens also periodically on the background)

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:playlist-export\`

\-----------------------

export user playlist(s) to file(s)

###  Usage

\* \`music:playlist-export \[--all\] \[--group GROUP\] \[--list-id LIST-ID\] \[--list-name LIST-NAME\] \[--all-lists\] \[--dir DIR\] \[--overwrite\] \[--\] \[<user\_i

d>...\]\`

export user playlist(s) to file(s)

###  Arguments

####  \`user\_id\`

specify one or more targeted users

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

target all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

specify a targeted group to include all users of that group

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--list-id\`

ID of the playlist to export

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--list-name\`

name of the playlist to export

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--all-lists\`

export all playlists of the user

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--dir\`

target directory, relative to the user home folder (the dir must exist)

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`''\`

####  \`--overwrite\`

overwrite the target file if it already exists

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:playlist-import\`

\-----------------------

import user playlist(s) from file(s)

###  Usage

\* \`music:playlist-import \[--all\] \[--group GROUP\] \[--file FILE\] \[--overwrite\] \[--append\] \[--\] \[<user\_id>...\]\`

import user playlist(s) from file(s)

###  Arguments

####  \`user\_id\`

specify one or more targeted users

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

target all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

specify a targeted group to include all users of that group

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--file\`

path of the playlist file, relative to the user home folder; \* and ? are treated as wildcards within the file name but not on the directory name

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--overwrite\`

overwrite the target playlist if it already exists

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--append\`

append imported tracks to an existing playlist if found

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:podcast-add\`

\-------------------

add a podcast channel from an RSS feed

###  Usage

\* \`music:podcast-add \[--all\] \[--group GROUP\] \[--rss RSS\] \[--\] \[<user\_id>...\]\`

add a podcast channel from an RSS feed

###  Arguments

####  \`user\_id\`

specify one or more targeted users

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

target all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

specify a targeted group to include all users of that group

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--rss\`

URL to an RSS feed

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:podcast-reset\`

\---------------------

remove all podcast channels of one or more users

###  Usage

\* \`music:podcast-reset \[--all\] \[--group GROUP\] \[--\] \[<user\_id>...\]\`

remove all podcast channels of one or more users

###  Arguments

####  \`user\_id\`

specify one or more targeted users

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

target all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

specify a targeted group to include all users of that group

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:podcast-update\`

\----------------------

update podcast channels of one or more users from their sources

###  Usage

\* \`music:podcast-update \[--all\] \[--group GROUP\] \[--older-than OLDER-THAN\] \[--force\] \[--\] \[<user\_id>...\]\`

update podcast channels of one or more users from their sources

###  Arguments

####  \`user\_id\`

specify one or more targeted users

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

target all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

specify a targeted group to include all users of that group

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--older-than\`

check updates only for channels which have not been checked for this many hours (sub-hour resolution supported with decimals)

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--force\`

update episodes even if there doesn't appear to be any changes

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:reset-cache\`

\-------------------

drop data cached by the music app for performance reasons

###  Usage

\* \`music:reset-cache \[--all\] \[--group GROUP\] \[--\] \[<user\_id>...\]\`

drop data cached by the music app for performance reasons

###  Arguments

####  \`user\_id\`

specify one or more targeted users

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

target all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

specify a targeted group to include all users of that group

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:reset-database\`

\----------------------

drop metadata indexed by the music app (artists, albums, tracks, playlists)

###  Usage

\* \`music:reset-database \[--all\] \[--group GROUP\] \[--\] \[<user\_id>...\]\`

drop metadata indexed by the music app (artists, albums, tracks, playlists)

###  Arguments

####  \`user\_id\`

specify one or more targeted users

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

target all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

specify a targeted group to include all users of that group

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`music:scan\`

\------------

scan and index any unindexed audio files

###  Usage

\* \`music:scan \[--all\] \[--group GROUP\] \[--debug\] \[--clean-obsolete\] \[--rescan\] \[--rescan-modified\] \[--folder \[FOLDER\]\] \[--\] \[<user\_id>...\]\`

scan and index any unindexed audio files

###  Arguments

####  \`user\_id\`

specify one or more targeted users

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all\`

target all known users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

specify a targeted group to include all users of that group

\* Accept value: yes

\* Is value required: yes

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--debug\`

will run the scan in debug mode (memory usage)

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--clean-obsolete\`

also check availability of any previously scanned tracks, removing obsolete entries

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--rescan\`

rescan also any previously scanned tracks

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--rescan-modified\`

rescan files which have mofication time later than the previous scan time (new files not scanned)

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--folder\`

scan only files within this folder (path is relative to the user home folder)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`notification:generate\`

\-----------------------

Generate a notification for the given user

###  Usage

\* \`notification:generate \[-l|--long-message LONG-MESSAGE\] \[--\] <user-id> <short-message>\`

Generate a notification for the given user

###  Arguments

####  \`user-id\`

User ID of the user to notify

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`short-message\`

Short message to be sent to the user (max. 255 characters)

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--long-message|-l\`

Long mesage to be sent to the user (max. 4000 characters)

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`''\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`notification:test-push\`

\------------------------

Generate a notification for the given user

###  Usage

\* \`notification:test-push \[--talk\] \[--\] <user-id>\`

Generate a notification for the given user

###  Arguments

####  \`user-id\`

User ID of the user to notify

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--talk\`

Test talk devices

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`preview:generate-all\`

\----------------------

Generate previews

###  Usage

\* \`preview:generate-all \[-p|--path \[PATH\]\] \[--\] \[<user\_id>...\]\`

Generate previews

###  Arguments

####  \`user\_id\`

Generate previews for the given user(s)

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--path|-p\`

limit scan to this path, eg. --path="/alice/files/Photos", the user\_id is determined by the path and all user\_id arguments are ignored, multiple u

sages allowed

\* Accept value: yes

\* Is value required: no

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`preview:pre-generate\`

\----------------------

Pre generate previews

###  Usage

\* \`preview:pre-generate\`

Pre generate previews

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`preview:repair\`

\----------------

distributes the existing previews into subfolders

###  Usage

\* \`preview:repair \[-b|--batch\] \[-d|--dry\] \[--delete\]\`

distributes the existing previews into subfolders

###  Options

####  \`--batch|-b\`

Batch mode - will not ask to start the migration and start it right away.

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--dry|-d\`

Dry mode - will not create, move or delete any files - in combination with the verbose mode one could check the operations.

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--delete\`

Delete instead of migrating them. Usefull if too many entries to migrate.

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`preview:reset-rendered-texts\`

\------------------------------

Deletes all generated avatars and previews of text and md files

###  Usage

\* \`preview:reset-rendered-texts \[-d|--dry\]\`

Deletes all generated avatars and previews of text and md files

###  Options

####  \`--dry|-d\`

Dry mode - will not delete any files - in combination with the verbose mode one could check the operations.

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`security:bruteforce:reset\`

\---------------------------

resets bruteforce attemps for given IP address

###  Usage

\* \`security:bruteforce:reset <ipaddress>\`

resets bruteforce attemps for given IP address

###  Arguments

####  \`ipaddress\`

IP address for which the attempts are to be reset

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`security:certificates\`

\-----------------------

list trusted certificates

###  Usage

\* \`security:certificates \[--output \[OUTPUT\]\]\`

list trusted certificates

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`security:certificates:import\`

\------------------------------

import trusted certificate in PEM format

###  Usage

\* \`security:certificates:import <path>\`

import trusted certificate in PEM format

###  Arguments

####  \`path\`

path to the PEM certificate to import

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`security:certificates:remove\`

\------------------------------

remove trusted certificate

###  Usage

\* \`security:certificates:remove <name>\`

remove trusted certificate

###  Arguments

####  \`name\`

the file name of the certificate to remove

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`serverinfo:update-storage-statistics\`

\--------------------------------------

Triggers an update of the counts related to storages used in serverinfo

###  Usage

\* \`serverinfo:update-storage-statistics \[--output \[OUTPUT\]\]\`

Triggers an update of the counts related to storages used in serverinfo

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`sharing:cleanup-remote-storages\`

\---------------------------------

Cleanup shared storage entries that have no matching entry in the shares\_external table

###  Usage

\* \`sharing:cleanup-remote-storages \[--dry-run\]\`

Cleanup shared storage entries that have no matching entry in the shares\_external table

###  Options

####  \`--dry-run\`

only show which storages would be deleted

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`sharing:expiration-notification\`

\---------------------------------

Notify share initiators when a share will expire the next day.

###  Usage

\* \`sharing:expiration-notification\`

Notify share initiators when a share will expire the next day.

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`tag:add\`

\---------

Add new tag

###  Usage

\* \`tag:add \[--output \[OUTPUT\]\] \[--\] <name> <access>\`

Add new tag

###  Arguments

####  \`name\`

name of the tag

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`access\`

access level of the tag (public, restricted or invisible)

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`tag:delete\`

\------------

delete a tag

###  Usage

\* \`tag:delete \[<id>\]\`

delete a tag

###  Arguments

####  \`id\`

The ID of the tag that should be deleted

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`tag:edit\`

\----------

edit tag attributes

###  Usage

\* \`tag:edit \[--name \[NAME\]\] \[--access \[ACCESS\]\] \[--\] \[<id>\]\`

edit tag attributes

###  Arguments

####  \`id\`

The ID of the tag that should be deleted

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--name\`

sets the 'name' parameter

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--access\`

sets the access control level (public, restricted, invisible)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`tag:list\`

\----------

list tags

###  Usage

\* \`tag:list \[--visibilityFilter \[VISIBILITYFILTER\]\] \[--nameSearchPattern \[NAMESEARCHPATTERN\]\] \[--output \[OUTPUT\]\]\`

list tags

###  Options

####  \`--visibilityFilter\`

filter by visibility (1,0)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--nameSearchPattern\`

optional search pattern for the tag name (infix)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`text:reset\`

\------------

Reset a text document

###  Usage

\* \`text:reset \[-f|--full\] \[--\] <file-id>\`

Reset a text document

###  Arguments

####  \`file-id\`

File id of the document to rest

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--full|-f\`

Drop all existing steps and use the currently saved version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`theming:config\`

\----------------

Set theming app config values

###  Usage

\* \`theming:config \[-r|--reset\] \[--\] \[<key> \[<value>\]\]\`

Set theming app config values

###  Arguments

####  \`key\`

Key to update the theming app configuration (leave empty to get a list of all configured values)

One of: name, url, imprintUrl, privacyUrl, slogan, color

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

####  \`value\`

Value to set (leave empty to obtain the current value)

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--reset|-r\`

Reset the given config key to default

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`trashbin:cleanup\`

\------------------

Remove deleted files

###  Usage

\* \`trashbin:cleanup \[--all-users\] \[--\] \[<user\_id>...\]\`

Remove deleted files

###  Arguments

####  \`user\_id\`

remove deleted files of the given user(s)

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--all-users\`

run action on all users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`trashbin:expire\`

\-----------------

Expires the users trashbin

###  Usage

\* \`trashbin:expire \[<user\_id>...\]\`

Expires the users trashbin

###  Arguments

####  \`user\_id\`

expires the trashbin of the given user(s), if no user is given the trash for all users will be expired

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`trashbin:restore\`

\------------------

Restore all deleted files

###  Usage

\* \`trashbin:restore \[--output \[OUTPUT\]\] \[--all-users\] \[--\] \[<user\_id>...\]\`

Restore all deleted files

###  Arguments

####  \`user\_id\`

restore all deleted files of the given user(s)

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--all-users\`

run action on all users

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`trashbin:size\`

\---------------

Configure the target trashbin size

###  Usage

\* \`trashbin:size \[--output \[OUTPUT\]\] \[-u|--user USER\] \[--\] \[<size>\]\`

Configure the target trashbin size

###  Arguments

####  \`size\`

the target size for the trashbin, if not provided the current trashbin size will be returned

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--user|-u\`

configure the target size for the provided user, if no user is given the default size is configured

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`twofactorauth:cleanup\`

\-----------------------

Clean up the two-factor user-provider association of an uninstalled/removed provider

###  Usage

\* \`twofactorauth:cleanup \[--output \[OUTPUT\]\] \[--\] <provider-id>\`

Clean up the two-factor user-provider association of an uninstalled/removed provider

###  Arguments

####  \`provider-id\`

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`twofactorauth:disable\`

\-----------------------

Disable two-factor authentication for a user

###  Usage

\* \`twofactorauth:disable \[--output \[OUTPUT\]\] \[--\] <uid> <provider\_id>\`

Disable two-factor authentication for a user

###  Arguments

####  \`uid\`

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`provider\_id\`

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`twofactorauth:enable\`

\----------------------

Enable two-factor authentication for a user

###  Usage

\* \`twofactorauth:enable \[--output \[OUTPUT\]\] \[--\] <uid> <provider\_id>\`

Enable two-factor authentication for a user

###  Arguments

####  \`uid\`

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`provider\_id\`

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`twofactorauth:enforce\`

\-----------------------

Enabled/disable enforced two-factor authentication

###  Usage

\* \`twofactorauth:enforce \[--on\] \[--off\] \[--group \[GROUP\]\] \[--exclude \[EXCLUDE\]\]\`

Enabled/disable enforced two-factor authentication

###  Options

####  \`--on\`

enforce two-factor authentication

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--off\`

don't enforce two-factor authenticaton

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--group\`

enforce only for the given group(s)

\* Accept value: yes

\* Is value required: no

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--exclude\`

exclude mandatory two-factor auth for the given group(s)

\* Accept value: yes

\* Is value required: no

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`twofactorauth:state\`

\---------------------

Get the two-factor authentication (2FA) state of a user

###  Usage

\* \`twofactorauth:state \[--output \[OUTPUT\]\] \[--\] <uid>\`

Get the two-factor authentication (2FA) state of a user

###  Arguments

####  \`uid\`

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`update:check\`

\--------------

Check for server and app updates

###  Usage

\* \`update:check\`

Check for server and app updates

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`usage-report:generate\`

\-----------------------

Prints a CSV entry with some usage information of the user:

userId,date,assignedQuota,usedQuota,numFiles,numShares,numUploads,numDownloads

"admin","2017-09-18T09:00:01+00:00",5368709120,786432000,1024,23,1400,5678

###  Usage

\* \`usage-report:generate \[--field-separator FIELD-SEPARATOR\] \[--date-format DATE-FORMAT\] \[--last-login\] \[--display-name\] \[--\] \[<user-id>\]\`

Prints a CSV entry with some usage information of the user:

userId,date,assignedQuota,usedQuota,numFiles,numShares,numUploads,numDownloads

"admin","2017-09-18T09:00:01+00:00",5368709120,786432000,1024,23,1400,5678

###  Arguments

####  \`user-id\`

User to generate the report for, if none is given the report is generated for all users

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--field-separator\`

Separator for the fields in the list

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`','\`

####  \`--date-format\`

Date format of the entries (see [http://php.net/manual/en/function.date.php](http://php.net/manual/en/function.date.php) for more information)

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`'c'\`

####  \`--last-login\`

Should the last login date be included in the report

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--display-name\`

Should the display name be included in the report

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:add\`

\----------

adds a user

###  Usage

\* \`user:add \[--password-from-env\] \[--display-name \[DISPLAY-NAME\]\] \[-g|--group \[GROUP\]\] \[--\] <uid>\`

adds a user

###  Arguments

####  \`uid\`

User ID used to login (must only contain a-z, A-Z, 0-9, -, \_ and @)

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--password-from-env\`

read password from environment variable OC\_PASS

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--display-name\`

User name used in the web UI (can contain any characters)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`NULL\`

####  \`--group|-g\`

groups the user should be added to (The group will be created if it does not exist)

\* Accept value: yes

\* Is value required: no

\* Is multiple: yes

\* Default: \`array ()\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:add-app-password\`

\-----------------------

Add app password for the named user

###  Usage

\* \`user:add-app-password \[--password-from-env\] \[--\] <user>\`

Add app password for the named user

###  Arguments

####  \`user\`

Username to add app password for

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--password-from-env\`

Read password from environment variable NC\_PASS/OC\_PASS. Alternatively it will be asked for interactively or an app password without the login pas

sword will be created.

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:delete\`

\-------------

deletes the specified user

###  Usage

\* \`user:delete <uid>\`

deletes the specified user

###  Arguments

####  \`uid\`

the username

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:disable\`

\--------------

disables the specified user

###  Usage

\* \`user:disable <uid>\`

disables the specified user

###  Arguments

####  \`uid\`

the username

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:enable\`

\-------------

enables the specified user

###  Usage

\* \`user:enable <uid>\`

enables the specified user

###  Arguments

####  \`uid\`

the username

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:export\`

\-------------

Export a user.

###  Usage

\* \`user:export <user> <folder>\`

Export a user.

###  Arguments

####  \`user\`

user to export

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`folder\`

local folder to export into

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:import\`

\-------------

Import a user.

###  Usage

\* \`user:import \[--user USER\] \[--\] <archive>\`

Import a user.

###  Arguments

####  \`archive\`

local path of the export archive to import

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--user\`

uid of user to overwrite with the imported data

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:info\`

\-----------

show user info

###  Usage

\* \`user:info \[--output \[OUTPUT\]\] \[--\] <user>\`

show user info

###  Arguments

####  \`user\`

user to show

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:lastseen\`

\---------------

shows when the user was logged in last time

###  Usage

\* \`user:lastseen <uid>\`

shows when the user was logged in last time

###  Arguments

####  \`uid\`

the username

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:list\`

\-----------

list configured users

###  Usage

\* \`user:list \[-l|--limit \[LIMIT\]\] \[-o|--offset \[OFFSET\]\] \[--output \[OUTPUT\]\] \[-i|--info\]\`

list configured users

###  Options

####  \`--limit|-l\`

Number of users to retrieve

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'500'\`

####  \`--offset|-o\`

Offset for retrieving users

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'0'\`

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--info|-i\`

Show detailed info

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:report\`

\-------------

shows how many users have access

###  Usage

\* \`user:report \[--count-dirs\]\`

shows how many users have access

###  Options

####  \`--count-dirs\`

Also count the number of user directories in the database (could time out on huge installations, therefore defaults to no with 500+ users)

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:resetpassword\`

\--------------------

Resets the password of the named user

###  Usage

\* \`user:resetpassword \[--password-from-env\] \[--\] <user>\`

Resets the password of the named user

###  Arguments

####  \`user\`

Username to reset password

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--password-from-env\`

read password from environment variable OC\_PASS

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`user:setting\`

\--------------

Read and modify user settings

###  Usage

\* \`user:setting \[--output \[OUTPUT\]\] \[--ignore-missing-user\] \[--default-value DEFAULT-VALUE\] \[--update-only\] \[--delete\] \[--error-if-not-exists\] \[--

\] <uid> \[<app> \[<key> \[<value>\]\]\]\`

Read and modify user settings

###  Arguments

####  \`uid\`

User ID used to login

\* Is required: yes

\* Is array: no

\* Default: \`NULL\`

####  \`app\`

Restrict the settings to a given app

\* Is required: no

\* Is array: no

\* Default: \`''\`

####  \`key\`

Setting key to set, get or delete

\* Is required: no

\* Is array: no

\* Default: \`''\`

####  \`value\`

The new value of the setting

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--output\`

Output format (plain, json or json\_pretty, default is plain)

\* Accept value: yes

\* Is value required: no

\* Is multiple: no

\* Default: \`'plain'\`

####  \`--ignore-missing-user\`

Use this option to ignore errors when the user does not exist

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--default-value\`

(Only applicable on get) If no default value is set and the config does not exist, the command will exit with 1

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--update-only\`

Only updates the value, if it is not set before, it is not being added

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--delete\`

Specify this option to delete the config

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--error-if-not-exists\`

Checks whether the setting exists before deleting it

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`versions:cleanup\`

\------------------

Delete versions

###  Usage

\* \`versions:cleanup \[-p|--path PATH\] \[--\] \[<user\_id>...\]\`

Delete versions

###  Arguments

####  \`user\_id\`

delete versions of the given user(s), if no user is given all versions will be deleted

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--path|-p\`

only delete versions of this path, e.g. --path="/alice/files/Music"

\* Accept value: yes

\* Is value required: yes

\* Is multiple: no

\* Default: \`NULL\`

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`versions:expire\`

\-----------------

Expires the users file versions

###  Usage

\* \`versions:expire \[<user\_id>...\]\`

Expires the users file versions

###  Arguments

####  \`user\_id\`

expire file versions of the given user(s), if no user is given file versions for all users will be expired.

\* Is required: no

\* Is array: yes

\* Default: \`array ()\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

\`workflows:list\`

\----------------

Lists configured workflows

###  Usage

\* \`workflows:list \[<scope> \[<scopeId>\]\]\`

Lists configured workflows

###  Arguments

####  \`scope\`

Lists workflows for "admin", "user"

\* Is required: no

\* Is array: no

\* Default: \`'admin'\`

####  \`scopeId\`

User IDs when the scope is "user"

\* Is required: no

\* Is array: no

\* Default: \`NULL\`

###  Options

####  \`--help|-h\`

Display this help message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--quiet|-q\`

Do not output any message

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--verbose|-v|-vv|-vvv\`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--version|-V\`

Display this application version

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--ansi\`

Force ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-ansi\`

Disable ANSI output

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-interaction|-n\`

Do not ask any interactive question

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`

####  \`--no-warnings\`

Skip global warnings, show command output only

\* Accept value: no

\* Is value required: no

\* Is multiple: no

\* Default: \`false\`
