---
tags:: notes
created: 2022-07-16T20:57:31 (UTC -04:00)
tags: []
source: https://che-adrian.medium.com/apply-necessary-fixes-to-the-nextcloud-configuration-282e57d42642
author: Chelaru Adrian
---

# Apply Necessary Fixes to the Nextcloud Configuration | by Chelaru Adrian | Medium

 You might find that you need to fix some little things for the Nextcloud instance you just installed. Some apps and parts of Nextcloud require running in the background. AJAX might not be the ideal…

---

# *Apply Necessary Fixes to the Nextcloud configuration*

You might find that you need to fix some little things for the Nextcloud instance you just installed.

## Run Background Jobs Using CRON instead AJAX

Some apps and parts of Nextcloud require running in the background. AJAX might not be the ideal solution.

1.  From 🟩 green box “Settings” go to the 🟧 orange box “Administration”, “Basic settings” then select “Cron” as in the 🟥 red box:

![](https://miro.medium.com/max/2952/1*XMq1MKm0Z45U80bWPdKBBg.png)

![](https://miro.medium.com/max/1550/1*2ggJ84qTcDjW7ghv-JdnyA.png)

Change Nextcloud background jobs to CRON

2\. Add cron for the Nextcloud in the crontab:

```
(2>/dev/null sudo -u www-data crontab -l ; echo "*/5  *  *  *  * php -f /var/www/nextcloud/cron.php") | sudo -u www-data crontab -
```

This should run every 5 minutes. You should see in the 🟪 purple box that it’s running correctly after the first 5 minutes.

## Check the Nextcloud Auto-diagnose Overview

To check if you need to take further actions, go to Nextcloud auto-diagnose from the 🟩 green box “Settings” then “Overview” 🟨 yellow box and check what’s inside of “Security & setup warnings” from the 🟦 blue box:

![](https://miro.medium.com/max/1400/1*1tYA1oNSaKJdPJCpEe_5tA.png)

Check if you need to fix something after setup Nextcloud

You can see there is a list of things Nextcloud recommends to fix:

1️⃣ The “Strict-Transport-Security” HTTP header is not set to at least “15552000” seconds. For enhanced security, it is recommended to enable HSTS as described in the [security tips ↗](https://docs.nextcloud.com/server/23/go.php?to=admin-security).

2️⃣ Your installation has no default phone region set. This is required to validate phone numbers in the profile settings without a country code. To allow numbers without a country code, please add “default\_phone\_region” with the respective [ISO 3166–1 code ↗](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements) of the region to your config file.

3️⃣ Module php-imagick in this instance has no SVG support. For better compatibility, it is recommended to install it.

## Apply Recommendations and Fix Warnings

In order to fix the 1️⃣ first one which requires increasing HTTP header time for SSL you need to edit the site configuration from Apache:

1\. Start using Terminal by editing the SSL version of the Nextcloud site configuration:

```
sudo nano /etc/apache2/sites-enabled/nextcloud-le-ssl.conf
```

Append the necessary string in order to fix HSTS time, like in the 🟪 purple box:

```
<IfModule mod_headers.c>  Header always set Strict-Transport-Security "max-age=15552000; includeSubDomains"</IfModule>
```

To save the file press CTRL + X then Y and ***enter***.

![](https://miro.medium.com/max/1400/1*CaXz62IgwYQCAyToYbPbEA.png)

Append HSTS configuration to Nextcloud Apache

2\. Reload Apache to load settings:

```
sudo systemctl apache2 reload
```

To fix the 2️⃣ you can add the “default\_phone\_region” to your config.php file:

Open the configuration file of Nextcloud:

```
sudo nano /var/www/nextcloud/config/config.php
```

Append the default phone region you chose like in the 🟥 red box:

```
'default_phone_region' => 'GB',
```

Replace ***GB*** with [your country code](https://en.wikipedia.org/wiki/ISO_3166-1), e.g.: RO, DE, US.

To save the file press CTRL + X then Y and ***enter***.

![](https://miro.medium.com/max/1400/1*2OMVH1SZIBe9LiOqVX-dnQ.png)

Change the default phone region of Nextcloud

To fix point 3️⃣ three, you just need to install that module:

```
sudo apt-get install libmagickcore-6.q16-6-extra
```

## Check if Everything is Done

After you did fix everything you saw here, you should get an “All checks passed.” message, like in the 🟫 brown box. Alternatively, you should also check your cloud security using the [Nextcloud scanner](https://scan.nextcloud.com/).

![](https://miro.medium.com/max/1754/1*BgtVMO5mvkQBczaz9OKAcw.png)

![](https://miro.medium.com/max/2306/1*2kNbTYdSp7G5dHYsmTJIiw.png)

After fixing everything your Nextcloud should show you it is secure

## Good

Now you know your cloud is working properly and it is secure 🔒.

It should be nice to keep it update also to the latest Nextcloud version as it comes with many security fixes from update to update.

Check out more:

-   Part 1: [Create a cloud using NextCloud, Raspberry Pi, and a USB HDD from scratch](https://che-adrian.medium.com/create-a-cloud-using-nextcloud-raspberry-pi-and-a-usb-hdd-from-scratch-f7235a325619#90b8)
-   Part 2: [Make your Nextcloud ready for accessing over the internet](https://che-adrian.medium.com/make-your-nextcloud-ready-for-accessing-over-the-internet-9a17116a44ce)
-   Part 3: [Optimize the speed of Nextcloud over the Raspberry Pi](https://che-adrian.medium.com/optimize-speed-of-nextcloud-over-the-raspberry-pi-52c0dd2ea67f)
-   Part 4: [Sync your files, photos, and passwords using your Nextcloud instance](https://che-adrian.medium.com/sync-your-files-photos-and-passwords-using-your-nextcloud-instance-6a8cc61efad5)
-   Part 5: This article
-   ***Part 6:*** [**_Add an SMTP account to make your Nextcloud send emails_**](https://che-adrian.medium.com/add-an-smtp-account-to-make-your-nextcloud-send-emails-f636e6f34d8)
-   Optional 7: [Activate Two-Factor authentication for Nextcloud](https://che-adrian.medium.com/activate-two-factor-authentication-for-nextcloud-3bd5a7f046e0)
-   Optional 8: [Configure OnlyOffice document server for Nextcloud on Raspberry Pi ARM64](https://che-adrian.medium.com/configure-onlyoffice-document-server-for-nextcloud-on-raspberry-pi-arm64-f7114f872357)
