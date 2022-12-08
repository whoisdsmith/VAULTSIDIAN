---
tags:: cron
created: 2022-07-16T02:10:07 (UTC -04:00)
tags: []
source: https://cloudkid.fr/nextcloud-cron-setup/
author: Cloudkid
---

# Nextcloud Cron Setup

> ## Excerpt
> You may have encountered the following warning after a Nextcloud install or you
may even never seen it but Nextcloud need to execute some background tasks
regularly to insure it's good working condition. Some cleanups need to be
executed on a daily basis.

> If you don't know what I'm talking about, check your Nextcloud application
settings : Open your Nextcloud instance with a privileged account > click on
your icon > Settings > Basic settings.
You can learn more in the official Nextcloud docum

---
# Nextcloud Cron Setup

Aug 20, 2021 3 min read [Nextcloud](https://cloudkid.fr/tag/nextcloud/ "Nextcloud")[Linux](https://cloudkid.fr/tag/linux/ "Linux")[Docker](https://cloudkid.fr/tag/docker/ "Docker")[HomeLab](https://cloudkid.fr/tag/homelab/ "HomeLab")

[![Nextcloud Cron Setup](https://images.unsplash.com/photo-1563861826100-9cb868fdbe1c?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwxMTc3M3wwfDF8c2VhcmNofDV8fGNsb2NrfGVufDB8fHx8MTYyOTQ1NDA1OA&ixlib=rb-1.2.1&q=80&w=2000)](https://cloudkid.fr/nextcloud-cron-setup/)

Photo by [Ocean Ng](https://unsplash.com/@oceanng?utm_source=ghost&utm_medium=referral&utm_campaign=api-credit) / [Unsplash](https://unsplash.com/?utm_source=ghost&utm_medium=referral&utm_campaign=api-credit)

You may have encountered the following warning after a Nextcloud install or you may even never seen it but Nextcloud need to execute some background tasks regularly to insure it's good working condition. Some cleanups need to be executed on a daily basis.

> If you don't know what I'm talking about, check your Nextcloud application settings : **Open your Nextcloud instance with a privileged account > click on your icon > Settings > Basic settings.**

You can learn more [in the official Nextcloud documentation](https://docs.nextcloud.com/server/stable/admin_manual/configuration_server/background_jobs_configuration.html).

![](https://cloudkid.fr/content/images/2021/08/Cron_Nextcloud.png)

Nextcloud Background Jobs Tab

There is 3 different ways of executing these scheduled tasks :

-   **AJAX**
-   **Webcron**
-   **Cron**

The AJAX is the default one but it's the less reliable because this technique only execute one task per page reloaded by an user, it requires many visits to be efficient.

The Webcron can be an good choice depending on your setup, but it rely on an external source to execute your Cron. You can use a service like [easyCron](https://www.easycron.com/) to load your [http\[s\]://<domain-of-your-server>/nextcloud/cron.php](https://cloudkid.fr/nextcloud-cron-setup//http[s]://<domain-of-your-server>/nextcloud/cron.php) URL, that will trigger the execution of the jobs.

The Cron method is, to me, the most reliable, you just have to enter how often you want your background tasks to run. As long your server is running, the task will execute, it's that simple.

___

### Setup

Two ways are gonna be covered, the classic way or the Docker way, depending of your install type.

### Classic installation :

You just have to set a Cron task, it's that easy ! To check your active Cron jobs just execute the following command in a terminal.

```Shell
crontab -l
```

This will list (-l) your active Cron tasks.

To edit (-e) you Cron file you will need to edit it as the user www-data (The nextcloud user).

```
crontab -e -u www-data
```

Here you can insert a new line at the end of the document with the following.

```Shell
*/5  *  *  *  * php -f /var/www/nextcloud/cron.php
```

This will trigger the Cronjob execution every 5 Minutes (Time used in the Nextcloud Doc)

> On some systems it might be required to call ****php-cli**** instead of ****php****.

If you want to force the execution of Cronjobs, you can enter the command manually :

```Shell
sudo -u www-data php -f /var/www/html/nextcloud/cron.php
```

### Docker Installation :

In Docker the idea is pretty munch the same, but the process must be executed in the host system instead of the container itself. By editing the host Crontab file you can specify the container and the user you want to use.

First we need to identify the Nextcloud container name.

```Shell
docker ps
```

With this command, you can list every running containers. Find the name of your nextcloud one and get to the next step. In our case the container will be named "_Nextcloud_".

Next, we are gonna try the command manually and check if it's triggered in the container. In the host terminal type :

```Shell
docker exec -u www-data nextcloud php cron.php
```

If the background jobs tab now show a green dot after a page refresh, the command is working, we just need to make it run every 5 Minutes.

![](https://cloudkid.fr/content/images/2021/08/Cron_OK-1.png)

Successful Background Jobs Execution 

On your Docker host system, edit the Cron file by typing :

```Shell
crontab -e
```

Add the following line at the end to execute it every five minutes :

```Shell
*/5 * * * * docker exec -u www-data nextcloud php cron.php
```

### Bonus : Non persistant Cron OS

Some OS, have non persistant Cron settings after reboot (e.g [Unraid](https://unraid.net/)), to counter that we can edit the starting script of the OS to insert the Nextcloud Cronjob line after startup.

In Unraid, the startup script is located under _**/boot/config/go**_, by editing this file, we can execute actions after the initial startup.

```Shell
nano /boot/config/go
```

In the "_**go**_" file add the following script at the end :

```Shell
# Add the Nexctloud Cron at startup
crontab -l > /tmp/temp
echo \ >> /tmp/temp
echo "*/5 * * * * docker exec -u www-data nextcloud php cron.php" >> /tmp/temp
crontab /tmp/temp
```

This script will backup the preconfigured Cronjobs in a file, add the Nextcloud entry & define this file as the new Cronjob.
