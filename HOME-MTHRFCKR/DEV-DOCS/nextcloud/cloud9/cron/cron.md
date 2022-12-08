---
tags:: cron
---
# Cron

php occ background:cron --help
Description:
  Use cron to run background jobs

Usage:
  background:cron

Options:
  -h, --help            Display this help message
  -q, --quiet           Do not output any message
  -V, --version         Display this application version
      --ansi            Force ANSI output
      --no-ansi         Disable ANSI output
  -n, --no-interaction  Do not ask any interactive question
      --no-warnings     Skip global warnings, show command output only
  -v|vv|vvv, --verbose  Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

---

crontab
usage:  crontab file
  crontab [ -e | -l | -r ]
  -e  (edit user's crontab)
  -l  (list user's crontab)
  -r  (delete user's crontab)

crontab -u -l

MAILTO="admin@cloud9.ctrlaltback.space"
SHELL="/usr/local/cpanel/bin/jailshell"
*/15 * * * * /usr/local/bin/ea-php81 php -f /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/cron.php

crontab -u elnulqmy -e
crontab: installing new crontab

crontab -u -l

MAILTO="admin@cloud9.ctrlaltback.space"
SHELL="/usr/local/cpanel/bin/jailshell"
*/15 * * * * /usr/local/bin/ea-php81 php -f /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/cron.php

MAILTO="admin@cloud9.ctrlaltback.space"
SHELL="/usr/local/cpanel/bin/jailshell"
*/5 * * * * php -f /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/cron.php

---

