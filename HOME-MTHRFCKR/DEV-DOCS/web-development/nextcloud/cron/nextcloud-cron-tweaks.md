---
tags:: cron
---
# Making Nextcloud's Cron Behave
Nextcloud needs frequent background jobs to keep running properly.  
  
Depending on the situation this "cron job" may take a very long time, overlapping with the default 5 minute delay between jobs. Which may end up running several instances of the job.  
  
To mitigate this we have 2 options:
 - Use a `systemd service+timer`
 - Encapsulate the cronjob into a bash script that checks if it is already running

The systemd approach has official support and will (by default) not run on top of a previous run (if still running).  
  
The bash script approach was cooked by me as an option and has no official support, but should work fine.  
  
If you want to be extra careful, you could even use the bash script into the systemd service, instead of the php-cron call. It should work the same, even though this should really not be needed, since systemd timers should not run if still running from a previous call. More info at the end of this article.  
    
**NOTE:** Most my installs are migrated owncloud-to-nextcloud instances, so my paths here are pointing to `/var/www/owncloud`. Adjust accordingly.  

-----
  
## Using Systemd
> [Official reference](https://docs.nextcloud.com/server/latest/admin_manual/configuration_server/background_jobs_configuration.html#systemd)  
  
If systemd is installed on the system, a systemd timer could be an alternative to a cronjob. We will need two files, one for the timer and one for the service.  
  
#### Service file
```
sudo nano /etc/systemd/system/nextcloudcron.service
```
Adjust **user** and **cron.php file location**
```
[Unit]
Description=Nextcloud Cron Job

[Service]
User=www-data
ExecStart=/usr/bin/php -f /var/www/owncloud/cron.php
```

#### Timer file
```
sudo nano /etc/systemd/system/nextcloudcron.timer
```
This should not need any adjustment
```
[Unit]
Description=Run Nextcloud cron.php every minute

[Timer]
OnBootSec=2min
OnUnitActiveSec=1min
Unit=nextcloudcron.service

[Install]
WantedBy=timers.target
```

#### Update systemctl
```
sudo systemctl daemon-reload
```

#### Enable the timer
```
sudo systemctl enable --now nextcloudcron.timer
```
  
That is all. Just disable/remove the old nextcloud cronjob if you already have it.    
  
-----

## Using Bash Script
I am migrating all my Nextcloud installs to systemd services instead of cron jobs. It is cleaner and easier to manage. You can run, enable, disable easily. It also blocks re-execution by default (which is the problem this article tries to solve).  
  
Having said that, I understand there are some situations where a cron job would still be needed.  
  
The idea is simple. We create a bash script that will run the cron job, but also checks if itself is already running.  
  
#### Bash script
Things to check/change:
 - WWW user > `www-data`
 - Nextcloud path > `/var/www/owncloud`
 - Nextcloud data folder > `/var/oc_data`
  
You may want to disable the current cronjob before anything.
```
sudo -u www-data crontab -e
```
Just add a `#` before the cronline to disable it.
```
#*/5 * * * * /usr/bin/php -f /var/www/owncloud/cron.php >/dev/null
```
Now we create the bash script in the current folder to test it.
```
nano nextcloudcron.sh
```
The script content:
```bash
#!/usr/bin/env bash

WEBUSER='www-data'
NCPATH='/var/www/owncloud'
DATAPATH='/var/oc_data'
CRONFILE="$NCPATH/cron.php"
PHPBIN='/usr/bin/php'
WAITTIME=10

(

get_out() {
    >&2 echo "The cronjob is already running. Exiting..."
    exit 11
}

wrong_user() {
    >&2 echo "Your need to run this script as the user: $WEBUSER"$'\n'"Current User: $USER"
    exit 12
}

no_php() {
    >&2 echo "Could not find the PHP executable. Is it installed and in your \$PATH ?"
    exit 14
}

# Wait for lock on /var/lock/.nextcloudcron.exclusivelock (fd 200) for 10 seconds
flock -x -w $WAITTIME 200 || get_out

# Check if we are running as the Web User
[ "$USER" = "$WEBUSER" ] || wrong_user

# Check if we have PHP
[ -x "$PHPBIN" ] || PHPBIN="$(command -v php 2>/dev/null)"
[ -x "$PHPBIN" ] || no_php

cd "$NCPATH"
# run sudo -u www-data /usr/bin/php -f /var/www/owncloud/cron.php
"$PHPBIN" -f "$CRONFILE"

) 200>"$DATAPATH"/.nextcloudcron.exclusivelock

```
**Note:** To avoid permission problems, the lockfile is stored into nextcloud's data folder. You could change it anywhere the web-user `www-data` has write permissions.  
  
Make it executable:
```
sudo chmod +x ./nextcloudcron.sh
```
Test it:
```
./nextcloudcron.sh
```
This should NOT run, since we didn't run it as the user `www-data`. So, let's do that:
```
sudo -u www-data ./nextcloudcron.sh
```
This should run fine. Otherwise we need to debug the problem.  
  
If it is all fine, let's move the bash script to nextcloud's folder (or anywhere you want it to be executed from).  
```
sudo cp ./nextcloudcron.sh /var/oc_data/nextcloudcron.sh
sudo chown www-data:www-data /var/oc_data/nextcloudcron.sh
sudo chmod 775 /var/oc_data/nextcloudcron.sh
```
I would test it again from the final destination
```
sudo -u www-data /var/oc_data/nextcloudcron.sh
```
If all is fine, add the new cronjob
```
sudo -u www-data crontab -e
```
Here is how it looks like with the old cronjob disabled and the new one enabled:
```
#*/5 * * * * /usr/bin/php -f /var/www/owncloud/cron.php >/dev/null # DISABLED
*/1 * * * * /var/oc_data/nextcloudcron.sh >/dev/null
```
This is all. Nextcloud's cron job should NEVER overlap itself again. If it is already running it should abort execution.  
  
#### Systemd timer with the script
If you want to use the bash script into your systemd service, just change the `.service` file to use the script.  
  
```
sudo nano /etc/systemd/system/nextcloudcron.service
```
Adjust **user** and **bash script location**  
```
[Unit]
Description=Nextcloud Cron Job

[Service]
User=www-data
ExecStart=/var/oc_data/nextcloudcron.sh
```
Then just follow the [systemd instructions](https://gist.github.com/tavinus/7bf4f10fe20403051e57f14a83842a4f#using-systemd).
    