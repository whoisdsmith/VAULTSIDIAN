# Nextcloud - Issuing OCC Commands without installing sudo

created: July 13, 2022 2:15 AM (UTC)
description: There should be no need to install sudo. If you want to run the occ command as an elevated user, simply do the following to run the command as the www-data user. Example using su and www-data user su -c &#34;php /var/www/html/occ maintenance:mode --off&#34; -s /bin/sh www-data Should I be using the www-data user? To confirm that the www-data user is the owner of the configuration you can do the look at the file properties of config.
folder: BOOKMRKS-MTHRFCKR / WEBDEV-MTHRFCKR / Website / Server
tags: server
url: https://blog.lukebtaylor.com/posts/nextcloud-issuing-occ-commands-without-installing-sudo