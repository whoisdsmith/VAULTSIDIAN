---
created: 2022-07-16T02:27:02 (UTC -04:00)
tags: []
source: https://forum.cloudron.io/topic/4498/are-cron-jobs-setup-to-run-for-email-notifications-from-nextcloud
author: 
---

# Are cron jobs setup to run for email notifications from Nextcloud? | Cloudron Forum

> ## Excerpt
> I'm testing settings for getting an email when a file is uploaded to a dropbox.  Test emails work fine. User has email filled in Settings > Personal > Activity > “A file or folder has been changed” is ticked. Push notifications are working.  This thread s...

---
# Are cron jobs setup to run for email notifications from Nextcloud?

This topic has been deleted. Only users with topic management privileges can see it.


I'm testing settings for getting an email when a file is uploaded to a dropbox.

-   Test emails work fine.
-   User has email filled in
-   Settings > Personal > Activity > “A file or folder has been changed” is ticked.
-   Push notifications are working.

This thread seems to suggest it was a fixed issue a while ago but relies on the cron setup:

[https://github.com/nextcloud/activity/issues/244](https://github.com/nextcloud/activity/issues/244)

Maybe I'm missing something or all install don't have this setup?

Do you see a log line "==> Run cron job" ? It should run every 5 mins.



Oh it seems the app does not used nextcloud's cron but needs it's own cron via 

`occ activity:send-mails`

So that definitely won't work since nobody is running that periodically.

Makes sense, yeah `=> Run cron job` is there.

Yeah, I think there's some decisions to make on what's the best settings. The last comment and link in that GitHub thread would seem like the best option to me:

[https://www.schilljs.com/2017/05/09/better-scheduling-of-activity-emails.html](https://www.schilljs.com/2017/05/09/better-scheduling-of-activity-emails.html)

```
	# crontab -u www-data -e
	0  *  *  *  *    php -f /var/www/nextcloud/occ activity:send-mails hourly
	30  7  *  *  *    php -f /var/www/nextcloud/occ activity:send-mails daily
	30  7  *  *  MON  php -f /var/www/nextcloud/occ activity:send-mails weekly
```

   
Then this looks best for real-time/instant email notifications but I'm not sure if that would create log-litter or what's best-practice in thinking about how it might scale:

```  
	 * * * * * www-data php /var/www/html/nextcloud/occ activity:send-mails
```


Correction, only the in-app/browser notification works, the native Push iOS notification doesn't, so I guess triggered by the same script as the emails would be.

Nextcloud is super-handy as a files dropbox with a non-guessable shared link - just knowing when something's been uploaded to then go and look would be useful, and I'm sure to others now you know it's possible when running.



Usually, for "flexible" things like this, we just have the user setup a crontab in the app. These cron timings tend to be fairly opinionated. I wonder why this is needed though, does nextcloud have no way for apps to integrate with the built-in cron they have (like wordpress plugins do?).





Actually, says apps can register to cron.php. Is this an upstream app issue?





Yeah, I read that, and it seems to you setup Cron by default with the email settings anyway at:

`/settings/admin` 

where the Test email button seems to work, so that part seems good.

 Notifications is a core/default App as I understand at: 
 
 `/settings/apps/installed/notifications`

This is what I have set here:

`/settings/user/activity`



And the folders are just the default and this extra shared folder:

