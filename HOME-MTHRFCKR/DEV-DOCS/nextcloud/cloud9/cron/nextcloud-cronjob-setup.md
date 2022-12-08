---
tags:: cron
---
---
created: 2022-07-16T02:20:11 (UTC -04:00)
tags: []
source: https://iammdnor.com/2019/11/07/nextcloud-cronjob-setup/
author: Author: mno
---

# NextCloud – Cronjob Setup

> ## Excerpt
> This cron job setup you can use for file retention policy, trashbin cleanup etc. To check existing cronjob for user www-data: To edit for add new cronjob: Add this script at the bottom of line: Ver…

---
# NextCloud – Cronjob Setup


![](https://komputergeek.files.wordpress.com/2019/11/cron11.png?w=335&h=38 "NextCloud – Cronjob Setup")


This cron job setup you can use for file retention policy, trashbin cleanup etc.

To check existing cronjob for user www-data:

<table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="plain plain">crontab -u www-data -l</code></div></div></td></tr></tbody></table>

![cron11](https://komputergeek.files.wordpress.com/2019/11/cron11.png?w=616)

To edit for add new cronjob:

<table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="plain plain">crontab -u www-data -e</code></div></div></td></tr></tbody></table>

![cron2](https://komputergeek.files.wordpress.com/2019/11/cron2.png?w=616)

Add this script at the bottom of line:

<table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="plain plain">*/5 * * * * php -f /var/www/nextcloud/cron.php</code></div></div></td></tr></tbody></table>

![cron3](https://komputergeek.files.wordpress.com/2019/11/cron3.png?w=616)

Verify if the cron job has been added and scheduled:

<table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="plain plain">crontab -u www-data -l</code></div></div></td></tr></tbody></table>
