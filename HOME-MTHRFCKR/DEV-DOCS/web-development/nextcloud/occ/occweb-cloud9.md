---
tags:: occ
---
# OCCWeb - CLOUD9

> ## Excerpt
> CLOUD9 24.0.1

---
# CLOUD9 24.0.1

=============

* [`check`](#check)

* [`help`](#help)

* [`list`](#list)

* [`status`](#status)

* [`upgrade`](#upgrade)

## **app:**

* [`app:check-code`](#appcheck-code)

* [`app:disable`](#appdisable)

* [`app:enable`](#appenable)

* [`app:getpath`](#appgetpath)

* [`app:install`](#appinstall)

* [`app:list`](#applist)

* [`app:remove`](#appremove)

* [`app:update`](#appupdate)

## **audioplayer:**

* [`audioplayer:reset`](#audioplayerreset)

* [`audioplayer:scan`](#audioplayerscan)

## **background:**

* [`background:ajax`](#backgroundajax)

* [`background:cron`](#backgroundcron)

* [`background:webcron`](#backgroundwebcron)

## **background-job:**

* [`background-job:execute`](#background-jobexecute)

## **broadcast:**

* [`broadcast:test`](#broadcasttest)

## **config:**

* [`config:app:delete`](#configappdelete)

* [`config:app:get`](#configappget)

* [`config:app:set`](#configappset)

* [`config:import`](#configimport)

* [`config:list`](#configlist)

* [`config:system:delete`](#configsystemdelete)

* [`config:system:get`](#configsystemget)

* [`config:system:set`](#configsystemset)

## **dav:**

* [`dav:create-addressbook`](#davcreate-addressbook)

* [`dav:create-calendar`](#davcreate-calendar)

* [`dav:delete-calendar`](#davdelete-calendar)

* [`dav:list-calendars`](#davlist-calendars)

* [`dav:move-calendar`](#davmove-calendar)

* [`dav:remove-invalid-shares`](#davremove-invalid-shares)

* [`dav:retention:clean-up`](#davretentionclean-up)

* [`dav:send-event-reminders`](#davsend-event-reminders)

* [`dav:sync-birthday-calendar`](#davsync-birthday-calendar)

* [`dav:sync-system-addressbook`](#davsync-system-addressbook)

## **db:**

* [`db:add-missing-columns`](#dbadd-missing-columns)

* [`db:add-missing-indices`](#dbadd-missing-indices)

* [`db:add-missing-primary-keys`](#dbadd-missing-primary-keys)

* [`db:convert-filecache-bigint`](#dbconvert-filecache-bigint)

* [`db:convert-mysql-charset`](#dbconvert-mysql-charset)

* [`db:convert-type`](#dbconvert-type)

## **duplicates:**

* [`duplicates:clear`](#duplicatesclear)

* [`duplicates:find-all`](#duplicatesfind-all)

* [`duplicates:list`](#duplicateslist)

## **encryption:**

* [`encryption:change-key-storage-root`](#encryptionchange-key-storage-root)

* [`encryption:decrypt-all`](#encryptiondecrypt-all)

* [`encryption:disable`](#encryptiondisable)

* [`encryption:enable`](#encryptionenable)

* [`encryption:encrypt-all`](#encryptionencrypt-all)

* [`encryption:list-modules`](#encryptionlist-modules)

* [`encryption:migrate-key-storage-format`](#encryptionmigrate-key-storage-format)

* [`encryption:set-default-module`](#encryptionset-default-module)

* [`encryption:show-key-storage-root`](#encryptionshow-key-storage-root)

* [`encryption:status`](#encryptionstatus)

## **files:**

* [`files:cleanup`](#filescleanup)

* [`files:repair-tree`](#filesrepair-tree)

* [`files:scan`](#filesscan)

* [`files:scan-app-data`](#filesscan-app-data)

* [`files:transfer-ownership`](#filestransfer-ownership)

## **group:**

* [`group:add`](#groupadd)

* [`group:adduser`](#groupadduser)

* [`group:delete`](#groupdelete)

* [`group:info`](#groupinfo)

* [`group:list`](#grouplist)

* [`group:removeuser`](#groupremoveuser)

## **groupfolders:**

* [`groupfolders:create`](#groupfolderscreate)

* [`groupfolders:delete`](#groupfoldersdelete)

* [`groupfolders:expire`](#groupfoldersexpire)

* [`groupfolders:group`](#groupfoldersgroup)

* [`groupfolders:list`](#groupfolderslist)

* [`groupfolders:permissions`](#groupfolderspermissions)

* [`groupfolders:quota`](#groupfoldersquota)

* [`groupfolders:rename`](#groupfoldersrename)

* [`groupfolders:scan`](#groupfoldersscan)

* [`groupfolders:trashbin:cleanup`](#groupfolderstrashbincleanup)

## **integrity:**

* [`integrity:check-app`](#integritycheck-app)

* [`integrity:check-core`](#integritycheck-core)

* [`integrity:sign-app`](#integritysign-app)

* [`integrity:sign-core`](#integritysign-core)

## **l10n:**

* [`l10n:createjs`](#l10ncreatejs)

## **log:**

* [`log:file`](#logfile)

* [`log:manage`](#logmanage)

* [`log:tail`](#logtail)

* [`log:watch`](#logwatch)

## **maintenance:**

* [`maintenance:data-fingerprint`](#maintenancedata-fingerprint)

* [`maintenance:mimetype:update-db`](#maintenancemimetypeupdate-db)

* [`maintenance:mimetype:update-js`](#maintenancemimetypeupdate-js)

* [`maintenance:mode`](#maintenancemode)

* [`maintenance:repair`](#maintenancerepair)

* [`maintenance:theme:update`](#maintenancethemeupdate)

* [`maintenance:update:htaccess`](#maintenanceupdatehtaccess)

## **music:**

* [`music:cleanup`](#musiccleanup)

* [`music:playlist-export`](#musicplaylist-export)

* [`music:playlist-import`](#musicplaylist-import)

* [`music:podcast-add`](#musicpodcast-add)

* [`music:podcast-reset`](#musicpodcast-reset)

* [`music:podcast-update`](#musicpodcast-update)

* [`music:reset-cache`](#musicreset-cache)

* [`music:reset-database`](#musicreset-database)

* [`music:scan`](#musicscan)

## **notification:**

* [`notification:generate`](#notificationgenerate)

* [`notification:test-push`](#notificationtest-push)

## **preview:**

* [`preview:generate-all`](#previewgenerate-all)

* [`preview:pre-generate`](#previewpre-generate)

* [`preview:repair`](#previewrepair)

* [`preview:reset-rendered-texts`](#previewreset-rendered-texts)

## **security:**

* [`security:bruteforce:reset`](#securitybruteforcereset)

* [`security:certificates`](#securitycertificates)

* [`security:certificates:import`](#securitycertificatesimport)

* [`security:certificates:remove`](#securitycertificatesremove)

## **serverinfo:**

* [`serverinfo:update-storage-statistics`](#serverinfoupdate-storage-statistics)

## **sharing:**

* [`sharing:cleanup-remote-storages`](#sharingcleanup-remote-storages)

* [`sharing:expiration-notification`](#sharingexpiration-notification)

## **tag:**

* [`tag:add`](#tagadd)

* [`tag:delete`](#tagdelete)

* [`tag:edit`](#tagedit)

* [`tag:list`](#taglist)

## **text:**

* [`text:reset`](#textreset)

## **theming:**

* [`theming:config`](#themingconfig)

## **trashbin:**

* [`trashbin:cleanup`](#trashbincleanup)

* [`trashbin:expire`](#trashbinexpire)

* [`trashbin:restore`](#trashbinrestore)

* [`trashbin:size`](#trashbinsize)

## **twofactorauth:**

* [`twofactorauth:cleanup`](#twofactorauthcleanup)

* [`twofactorauth:disable`](#twofactorauthdisable)

* [`twofactorauth:enable`](#twofactorauthenable)

* [`twofactorauth:enforce`](#twofactorauthenforce)

* [`twofactorauth:state`](#twofactorauthstate)

## **update:**

* [`update:check`](#updatecheck)

## **usage-report:**

* [`usage-report:generate`](#usage-reportgenerate)

## **user:**

* [`user:add`](#useradd)

* [`user:add-app-password`](#useradd-app-password)

* [`user:delete`](#userdelete)

* [`user:disable`](#userdisable)

* [`user:enable`](#userenable)

* [`user:export`](#userexport)

* [`user:import`](#userimport)

* [`user:info`](#userinfo)

* [`user:lastseen`](#userlastseen)

* [`user:list`](#userlist)

* [`user:report`](#userreport)

* [`user:resetpassword`](#userresetpassword)

* [`user:setting`](#usersetting)

## **versions:**

* [`versions:cleanup`](#versionscleanup)

* [`versions:expire`](#versionsexpire)

## **workflows:**

* [`workflows:list`](#workflowslist)

`check`
