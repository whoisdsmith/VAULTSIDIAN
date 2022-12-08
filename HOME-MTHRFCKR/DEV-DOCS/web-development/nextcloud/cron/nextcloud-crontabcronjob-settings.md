---
created: 2022-07-16T02:09:33 (UTC -04:00)
tags: []
source: https://kenfavors.com/code/nextcloud-crontab-cronjob-settings/
author: 
---

# Nextcloud Crontab/Cronjob Settings – Ken Favors . com

> ## Excerpt
> The best/clearest info I have seen for using a cronjob with the preview generator app:
https://help.nextcloud.com/t/clarity-on-the-crontab-settings-for-the-preview-generator-app/6144/8

---
# Nextcloud Crontab/Cronjob Settings

The best/clearest info I have seen for using a cronjob with the preview generator app:  
[https://help.nextcloud.com/t/clarity-on-the-crontab-settings-for-the-preview-generator-app/6144/8](https://help.nextcloud.com/t/clarity-on-the-crontab-settings-for-the-preview-generator-app/6144/8)

[https://docs.nextcloud.com/server/stable/admin\_manual/configuration\_server/background\_jobs\_configuration.html](https://docs.nextcloud.com/server/stable/admin_manual/configuration_server/background_jobs_configuration.html)

```
$ sudo crontab -e -u www-data
```

then enter the code below at the bottom (runs every 15 minutes):

```
*/15  *  *  *  * php -f /var/www/nextcloud/cron.php
```

How to run a cron manually (the example below is for nextcloud):

```
$ sudo -u www-data php -f /var/www/html/nextcloud/cron.php
```

___

## Setup Cron (or systemd timers) for the Nextcloud Preview Generator

[https://nextcloud.com/blog/setup-cron-or-systemd-timers-for-the-nextcloud-preview-generator/](https://nextcloud.com/blog/setup-cron-or-systemd-timers-for-the-nextcloud-preview-generator/)

## Cron

Add or create a new cronjob for the Nextcloud user:

```
$ sudo crontab -e -u www-data
```

Using your favorite editor, add something like this, which will run the job at 04:00 (make sure to point to the correct directory of the ‘occ' file):

```
0 4 * * * /usr/bin/php -f /var/www/html/nextcloud/occ preview:pre-generate
```

## Or using systemd timers

Systemd also has the possibility to run specific tasks at specific times or events. called Timers. You need to create 2 unit files:

File 1:

```
$ sudo nano /etc/systemd/system/nextcloud-preview-generator.service
```

and add this to the File 1:

```
[Unit]
Description=Nextcloud Preview Generator

[Service]
Type=oneshot
User=www-data
ExecStart=/usr/bin/php -f /var/www/html/nextcloud/occ preview:pre-generate

[Install]
WantedBy=basic.target
```

File 2:

```
$ sudo nano /etc/systemd/system/nextcloud-preview-generator.timer
```

and add this to File 2:

```
[Unit]
Description=Run Nextcloud Preview Generator daily at 04:00

[Timer]
OnCalendar=*-*-* 4:00:00
Persistent=true

[Install]
WantedBy=timers.target
```

systemd reload:

```
$ systemctl daemon-reload
```

activate the timer:

```
$ systemctl enable nextcloud-preview-generator.timer
```

start the timer:

```
$ systemctl start nextcloud-preview-generator.timer
```

___
