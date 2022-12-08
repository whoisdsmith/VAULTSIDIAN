---
tags:: cron
created: 2022-07-16T02:42:58 (UTC -04:00)
tags: []
source: https://forum.hestiacp.com/t/nextcloud-cron-setup/4045
author: 
---

# Nextcloud - Cron Setup - Hestia Control Panel - Hestia Control Panel - Discourse

> ## Excerpt
> This is really just a note for anyone trying to solve this issue in the future, as I was working through setting up Nextcloud cron.php via HestiaCP - Cron configuration tab, I assumed I had to STATE the “php” entry, and I was incorrect.  Adding this cron job under the HestiaCP user in question works perfectly.  Code that Nextcloud recommends:  php -f /var/www/nextcloud/cron.php  Code that HestiaCP likes:  -f ~/web/(your domain name)/public_html/cron.php  Enjoy, and thanks to all the great work b...

---
This is really just a note for anyone trying to solve this issue in the future, as I was working through setting up Nextcloud cron.php via HestiaCP - Cron configuration tab, I assumed I had to STATE the “php” entry, and I was incorrect.

Adding this cron job under the HestiaCP user in question works perfectly.

Code that Nextcloud recommends:  
php -f /var/www/nextcloud/cron.php

Code that HestiaCP likes:  
\-f ~/web/(your domain name)/public\_html/cron.php

Enjoy, and thanks to all the great work by these devs!

\-Ian

---

/usr/bin/php -f /home/user/web/(your domain name)/public_html/cron.php should also work fine