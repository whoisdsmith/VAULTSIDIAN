---
tags:: cron
created: 2022-07-17T20:35:15 (UTC -04:00)
tags: []
source: https://forum.level1techs.com/t/solved-nextcloud-say-that-cron-jobs-are-not-running/183498
author: 
---

# [SOLVED] Nextcloud say that cron Jobs are not Running - Software & Operating Systems / Linux - Level1Techs Forums

> ## Excerpt
> My Nextcloud say:  Last Cron-Job-Run: 15 Days ago. Check the background job settings  I use Nextcloud 23 and PHP version 8.0  The Server logs say that the CRON jobs is running.  Mar 30 12:25:01 homesrv CRON[22343]: (www-data) CMD (php -f /var/www/nextcloud/cron.php --define apc.enable_cli=1)  and in the Nexcloud-Logs there is no Error about the CRON jobs…  I use APCu  https://docs.nextcloud.com/server/21/admin_manual/configuration_server/caching_configuration.html#id1  I have set the  APCu Setti...

---
`Last Cron-Job-Run: 15 Days ago. Check the background job settings`

I use Nextcloud 23 and PHP version 8.0  
The Server logs say that the CRON jobs is running.

```
Mar 30 12:25:01 homesrv CRON[22343]: (www-data) CMD (php -f /var/www/nextcloud/cron.php --define apc.enable_cli=1)
```

and in the Nexcloud-Logs there is no Error about the CRON jobs…

I use APCu  
[https://docs.nextcloud.com/server/21/admin\_manual/configuration\_server/caching\_configuration.html#id1 5](https://docs.nextcloud.com/server/21/admin_manual/configuration_server/caching_configuration.html#id1)

I have set the APCu Settings on ALL php.ini files and on the CRON

```
apc.enable_cli=1
```

—-

---
created: 2022-07-17T20:36:12 (UTC -04:00)
tags: []
source: https://forum.level1techs.com/t/solved-nextcloud-say-that-cron-jobs-are-not-running/183498
author: 
---

# [SOLVED] Nextcloud say that cron Jobs are not Running - Software & Operating Systems / Linux - Level1Techs Forums

> ## Excerpt
> My Nextcloud say:  Last Cron-Job-Run: 15 Days ago. Check the background job settings  I use Nextcloud 23 and PHP version 8.0  The Server logs say that the CRON jobs is running.  Mar 30 12:25:01 homesrv CRON[22343]: (www-data) CMD (php -f /var/www/nextcloud/cron.php --define apc.enable_cli=1)  and in the Nexcloud-Logs there is no Error about the CRON jobs…  I use APCu  https://docs.nextcloud.com/server/21/admin_manual/configuration_server/caching_configuration.html#id1  I have set the  APCu Setti...

---
i had to add: the PHP version **8.0** to CronTab…

```
*/5  *  *  *  * php8.0 -f /var/www/nextcloud/cron.php --define apc.enable_cli=1
```

___

**Edit:**

Now i have everything figured out ![:wink:](https://forum.level1techs.com/images/emoji/twitter/wink.png?v=12 ":wink:")

-   Ubuntu 20.04 LTS
-   Nextcloud 23
-   PHP 8.0
-   APCu (Memmory caching)

The Cronjob _\# crontab -u www-data -e_

```
*/5  *  *  *  * php8.0 -f /var/www/nextcloud/cron.php
```

I added this to _/etc/php/8.0/cli/php.ini_

```
[APCu]
apc.enable_cli=1
```

And with this setup/config my Cronjob is working fine.
