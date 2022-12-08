---
created: 2022-07-04T22:18:17 (UTC -04:00)
tags: troubleshooting
source: https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer/134007/37
author: 
---

# Nextcloud 23.02 OPcache interned strings buffer

---


Hello,

I just updated from 23.0 to 23.02 and starting getting this warning:

The OPcache interned strings buffer is nearly full. To assure that repeating strings can be effectively cached, it is recommended to apply `opcache.interned_strings_buffer` to your PHP configuration with a value higher than \`8’

I saw in the 10-opcache.ini file that the line was commented out so I guess 8 is the default. I uncommented the line and set the value to 16. After restarting php-fpm, the warning message went away but after a while it complained about 16 not being enough. In the mean time I have set it to 32 but can anyone advise on what a sensible value would be and the logic behind it. Thanks Bill


-   [Nextcloud 23.02 OPcache interned strings buffer "8"29](https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer-8/134290/2)
-   [The PHP OPcache module is not properly configured15](https://help.nextcloud.com/t/the-php-opcache-module-is-not-properly-configured/135870/5)
-   [Sicherheits- & Einrichtungswarnungen nach Update auf 23.0.23](https://help.nextcloud.com/t/sicherheits-einrichtungswarnungen-nach-update-auf-23-0-2/134013/12)
-  https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer/134007/37
    
    [](https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer/134007/37)![](https://help.nextcloud.com/letter_avatar_proxy/v4/letter/k/85f322/20.png "konki")1d

---

Hi [@BillTNZ](https://help.nextcloud.com/u/billtnz)

I found this: [https://gist.github.com/rohankhudedev/1a9c0a3c7fb375f295f9fc11aeb116fe 1.1k](https://gist.github.com/rohankhudedev/1a9c0a3c7fb375f295f9fc11aeb116fe)  
and took it.

But I think an answer in the nextcloud docs would be good too.

Best, Bernd

---

Hi [@BillTNZ](https://help.nextcloud.com/u/billtnz)

I think 8 is fine. And there is no reason to increase the value without need, as long as there are no problems with your Nextcloud.

I have it set to 8 in my php.ini and the warning disappeared after a reboot of my test server. On my production server with identical configuartion it never appeared in the first place. Also someone else here on the forum reported that the message disappeared when he or she restarted the PHP-FPM service, but it reappeared at a later time. All this and the fact that you already tried higher values than 8 and you still receiving the warning, tells me that this is most likely a bug in Nextcloud.

So as long as there are no “real” issues with your instance, I would recommend to ignore the warning for the time beeing, instead of blindly increasing the value. Maybe you could also create a GitHub issue, if none exists yet, so that the Nextcloud devs are aware about the issue and they can check what is causing this warning.

---

[MichaIng](https://help.nextcloud.com/u/MichaIng)

[Feb 18](https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer/134007/5 "Post date")

Hey guys, this recommendation is not a bug but a new way how OPcache related recommendations are obtained since Nextcloud v23.0.1:

-   [https://github.com/nextcloud/server/pull/27403 143](https://github.com/nextcloud/server/pull/27403)
-   [https://github.com/nextcloud/server/issues/31223 99](https://github.com/nextcloud/server/issues/31223)

Previously a fixed set of settings was recommended, basically matching the PHP default values. Now the actual OPcache usage is obtained, and when one limit is reached by >90%, a recommendation is shown to increase that particular setting. That way the recommendations have become much more accurate, serving the actual intention.

E.g. Nextcloud uses ~32-64 MiB overall OPcache memory, based on used apps, but the recommendation was to apply 128 MiB, being wrong, not providing any performance benefit. Same with the maximum stored keys/scripts, where 10,000 was recommended while Nextcloud usually uses 3,000 - 4,000.

The default 8 MiB interned strings buffer applied by PHP (when not set differently) is usually sufficient as well, e.g. my Nextcloud instance uses 3.5 MiB, but this seems to highly depend on used apps. 16 MiB was observed to cover more cases, but obviously not all of them. I’m not sure whether some apps make much use of large strings, or even temporary scripts (PHP files) which are then not evicted properly, but generally, when the system’s RAM allows, it makes sense to follow the recommendation to maximise performance, since otherwise, when the buffer is full, new requests may need to first evict strings before new ones can be cached, and the evicted ones need to be cached again when requested later.

While this new behaviour allows to reduce OPcache limits to what Nextcloud actually uses, more importantly it better covers cases where Nextcloud is not the only web application served by the same webserver and PHP (OPcache) instance. E.g. I administrate another server where phpBB, Wordpress and Matomo run on. And it uses ~350 - 400 MiB overall OPcache and up to 150 MiB for internal strings, caused by indeed temporary large PHP scripts created, used and cached during website usage. The defaults (and previously recommended) 128/8 MiB would break the performance benefit provided by OPcache for these websites. An accurate recommendation can only be done based on actual usage.


> So as long as there are no “real” issues with your instance

Indeed, like all warnings on the admin panel, those are not mandatory to follow, but recommendations based on what Nextcloud is able to measure. Not following these won’t break your Nextcloud, OPcache is a pure performance buffer. There are other warnings you can safely ignore, like `imagick` PHP module, `bcmath` and `gmp` modules if you do not use WebAuthn based passwordless authentication anyway, the `X-Download-Options` header warning if none of your users access Nextcloud via Internet Explorer, and more.

Since more than 16 MiB are a bit unexpected to be ever used, if Nextcloud is the only web application served by your webserver/PHP instance, and the admin panel shows a recommendation to apply >16 MiB, it would be interesting to see your apps list. Probably we can find similarities or identify the app which allocates that much interned strings. Maybe there is indeed an issue with cache eviction in one of these apps, or it simply contains a large number of strings/text shown in its interfaces.

---

> it would be interesting to see your apps list

```
root@lebernd-oc:/var/www/nextcloud# occ app:list
Enabled:
  - accessibility: 1.9.0
  - activity: 2.15.0
  - admin_audit: 1.13.0
  - analytics: 4.0.3
  - announcementcenter: 6.1.1
  - audioplayer: 3.2.4
  - bruteforcesettings: 2.3.0
  - calendar: 3.0.6
  - camerarawpreviews: 0.7.15
  - circles: 23.0.1
  - cloud_federation_api: 1.6.0
  - comments: 1.13.0
  - contacts: 4.0.8
  - contactsinteraction: 1.4.0
  - cookbook: 0.9.9
  - dashboard: 7.3.0
  - dav: 1.21.0
  - deck: 1.6.0
  - dicomviewer: 1.2.3
  - duplicatefinder: 0.0.13
  - epubreader: 1.4.7
  - federatedfilesharing: 1.13.0
  - federation: 1.13.0
  - files: 1.18.0
  - files_accesscontrol: 1.13.0
  - files_downloadactivity: 1.12.0
  - files_external: 1.15.0
  - files_pdfviewer: 2.4.0
  - files_rightclick: 1.2.0
  - files_sharing: 1.15.0
  - files_trashbin: 1.13.0
  - files_versions: 1.16.0
  - files_videoplayer: 1.12.0
  - firstrunwizard: 2.12.0
  - groupfolders: 11.1.2
  - imageconverter: 1.3.2
  - integration_discourse: 1.0.2
  - integration_github: 1.0.2
  - integration_gitlab: 1.0.3
  - integration_reddit: 1.0.3
  - integration_twitter: 1.0.2
  - logreader: 2.8.0
  - lookup_server_connector: 1.11.0
  - mail: 1.11.6
  - maps: 0.1.10
  - music: 1.5.1
  - news: 17.0.1
  - nextcloud_announcements: 1.12.0
  - notes: 4.3.0
  - notifications: 2.11.1
  - notify_push: 0.3.0
  - oauth2: 1.11.0
  - password_policy: 1.13.0
  - phonetrack: 0.7.0
  - photos: 1.5.0
  - previewgenerator: 4.0.0
  - privacy: 1.7.0
  - provisioning_api: 1.13.0
  - recommendations: 1.2.0
  - richdocuments: 5.0.2
  - serverinfo: 1.13.0
  - settings: 1.5.0
  - sharebymail: 1.13.0
  - socialsharing_email: 2.4.0
  - support: 1.6.0
  - survey_client: 1.11.0
  - systemtags: 1.13.0
  - tasks: 0.14.2
  - text: 3.4.0
  - theming: 1.14.0
  - theming_customcss: 1.10.0
  - twofactor_backupcodes: 1.12.0
  - twofactor_totp: 6.2.0
  - updatenotification: 1.13.0
  - user_status: 1.3.1
  - viewer: 1.7.0
  - weather_status: 1.3.0
  - workflowengine: 2.5.0
Disabled:
  - apporder: 0.14.0
  - breezedark: 23.2.0
  - encryption: 2.10.0
  - external: 3.10.2
  - files_markdown: 2.3.5
  - files_mindmap: 0.0.26
  - integration_whiteboard: 0.0.14
  - polls: 3.5.4
  - side_menu: 2.3.3
  - spreed: 13.0.3
  - talk_matterbridge: 1.23.2
  - user_ldap
  - whiteboard: 0.0.3
```

I have installed quite some apps on this server, that’s right.

Thank you for discussing some technical aspects regarding this subject [@MichaIng](https://help.nextcloud.com/u/michaing) .

Best, Bernd


> Since more than 16 MiB are a bit unexpected to be ever used, if Nextcloud is the only web application served by your webserver/PHP instance, and the admin panel shows a recommendation to apply >16 MiB, it would be interesting to see your apps list. Probably we can find similarities or identify the app which allocates that much interned strings. Maybe there is indeed an issue with cache eviction in one of these apps, or it simply contains a large number of strings/text shown in its interfaces.

Ah ok. Does this mean the warning shows recommendations based on the actual usage of the cache? I asumed the test is just checking the values that are set in the configuration, and sometimes fails to do so. 



 ![](https://help.nextcloud.com/user_avatar/help.nextcloud.com/lebernd/25/18927_2.png "lebernd") lebernd

[Feb 19](https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer/134007/8 "Post date")

Thanks [@lebernd](https://help.nextcloud.com/u/lebernd) for sharing your apps list. Hmm, it has not such much in common with the one [here 1](https://github.com/nextcloud/server/issues/31223#issuecomment-1043141816) when ignoring the core apps and those which I use on my own instance. I was hoping for an overlap on large apps, like OnlyOffice. Nasty that there is no way I’m aware of to see the content of the interned strings buffer, which scripts contribute to which string etc. That would be awesome for deeper analysis.

If you find time, could you try to find the interned strings buffer size at which Nextcloud stops recommending more? You could also use [opcache-gui 51](https://github.com/amnuts/opcache-gui) or this little script to see OPcache usage stats:

```
<?php echo '<pre>'; print_r(opcache_get_status(false)); echo '</pre>';
```

_Using `(true)` would add the full list of all cached scripts._

There is also a [CLI tool 9](https://github.com/gordalina/cachetool) but it is more difficult to use correctly, when one wants to check the PHP OPcache instance Nextcloud runs on, instead of a new instance created by the CLI tool itself ![:wink:](https://help.nextcloud.com/images/emoji/twitter/wink.png?v=12 ":wink:").

___

[](https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer/134007/7 "go to the quoted post")

![](https://help.nextcloud.com/letter_avatar_proxy/v4/letter/b/71e660/40.png) bb77:

> Ah ok. Does this mean the warning shows recommendations based on the actual usage of the cache?

Exactly that. Previously it did just compare the set values against fixed values (the PHP defaults in fact), now in compares used vs available buffer sizes, via `opcache_get_status()` PHP function mentioned above.

3 Replies

1

[![](https://help.nextcloud.com/user_avatar/help.nextcloud.com/rubo77/45/10341_2.png)](https://help.nextcloud.com/u/rubo77)

[rubo77](https://help.nextcloud.com/u/rubo77)

[Feb 19](https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer/134007/9 "Post date")

To solve this inside a docker image until the PR [https://github.com/nextcloud/docker/pull/1702 32](https://github.com/nextcloud/docker/pull/1702) is added:

```
docker exec -i -t next_your_domain_app_1 bash -l
sed -i "s/opcache.interned_strings_buffer=8/opcache.interned_strings_buffer=16/g" /usr/local/etc/php/conf.d/opcache-recommended.ini |grep opcache.interned_strings_buffer /usr/local/etc/php/conf.d/opcache-recommended.ini
apache2ctl graceful
```

1

13 days later

25 days later

29 days later

29 days later

21 days later
