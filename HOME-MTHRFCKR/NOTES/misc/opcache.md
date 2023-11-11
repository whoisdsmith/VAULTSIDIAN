The PHP OPcache module is not properly configured - ℹ️ Support - Nextcloud community

Are there other PHP apps running on the server or only Nextcloud and which IONS server do you have exactly? 512MB, 2GB or more…?

I’m not an expert and others may be abele to give you a more detailed explenation on how this works. But at the end of the day it depends on your workload and on how much RAM your server has, which values you have to set. So you won’t get around doing some testing. On a server with 2GB of RAM, I would try to double the values and then see if the warnings go away and everything still runs fine. On a server with only 512MB of RAM it’s probably better to increase the values in smaller amounts, maybe by 25% or 50%.

Also, as far as I understand it, these warnings do not mean, that you absolutley have to increase the values. Nextcloud will still run, even with lower values. Of course the performance will get better if you increase them, but if you for example haven a server with only 512MB of RAM there is only so much headroom and so much you can do.

Maybe the actual usage cannot be detected correctly on webhosters with limited permissions. That’s what I meant when I said the message itself could be a bug. Or is this detection always possible?

Maybe, but if you were out for the best performance, you wouldn’t use web hosting for something like Nextcloud… 

I think it’s strange that so many users have this message since NC 23. Are they all on that busy servers?

I think it highly depends on how you use your server and especially what apps you are using. I use Nextcloud mainly as a synchronistation backend for files, calendar and contacts and hardly ever login to the web interface. But if multiple useres are using the full blown Nextcloud Hub including Nextcloud Office and mail client, and they are all mainly working in the browser, things may quickly add up. Also there are probably not all apps from the app store equally well optimitzed.

But again, as a home user, I wouldn’t worry too much as long as everything is working fine. Such messages are rather to be seen as recommendations than as strict requirements. In the end, PHP optimization and server optimization in general are relatively complex topics for which there are no one-size-fits-all solutions. If you are using Nextcloud professionally though, it might be worth diving deeper into the subject…

…but yet again, if if you really wanted to do that, you probably wouldn’t use web hosting in the first place 

---

I use the following values from this tutorial 75 and never had any issues:

[opcache]  
opcache.enable=1  
opcache.enable_cli=1  
opcache.memory_consumption=128  
opcache.interned_strings_buffer=8  
opcache.max_accelerated_files=10000  
opcache.revalidate_freq=1  
opcache.save_comments=1

---

EXTCLOUD INSTALLATION INSTRUCTIONS OVERVIEW: INSTRUCTIONS  
Nextcloud 23 Installation Guide with Apache2  
by Carsten Rieger|Updated 29. May 2022

Nextcloud 23 with Apache2  
This Nextcloud 23 installation guide describes the installation, configuration and curing as well as some expansion options of Nextcloud Hub II (aka Nextcloud 23) on an Ubuntu Server 20.04.x LTS Focal Fossa (x86-64) or Debian Server 11 bullseye (x86-64).

The installation is based on the components Apache2, optional Let's Encrypt TLS 1.3, MariaDB 10.6.x, PHP 8.x (php-fpm), Redis, Fail2ban and ufw and finally receives an A+ security assessment from both Nextcloud and Qualys SSL Labs.

In the course of this guide, you only have to replace the red marked values such as your.domain.de or 192.168.2.x and /var/nc-data with the corresponding values of your system.

System requirements  
sudo-s  
add-apt repository universe && apt update -q4 && apt upgrade -y  
apt install -y software-properties-common curl gnupg2 git lsb-release ssl-cert ca-certificates apt-transport-https tree locate software-properties-common dirmngr screen htop net-tools zip unzip bzip2 ffmpeg ghostscript libfile-fcntllock-perl libfontconfig1 libfuse2 socat wget  
add-apt-repository -y ppa:ondrej/php && add-apt-repository -y ppa:ondrej/apache2  
apt update -q4 && apt upgrade -y && apt autoremove -y && apt autoclean -y  
Create necessary directories (assumption:/var/nc_data will be the Nextcloud data directory):

mkdir -p /var/www /var/nc_datachown -R www-data:www-data /var/nc_data /var/www  
Installation of the MariaDB database  
apt-key adv --recv-keys --keyserver hkps://keyserver.ubuntu.com:443 0xF1656F24C74CD1D8  
add-apt-repository 'deb [arch=amd64] http://ftp.hosteurope.de/mirror/mariadb.org/repo/10.6/ubuntu focal main'  
apt update -q4 && apt install -y mariadb-server  
Curing of the MariaDB database

mysql_secure_installation  
Configuration of the MariaDB database

service mariadb stop && mv /etc/mysql/my.cnf /etc/mysql/my.cnf.bak && nano /etc/mysql/my.cnf  
Enter all lines in the empty file:

[client] default character set = utf8mb4 port = 3306 socket = /var/run/mysqld/mysqld.sock [mysqld_safe] log_error=/var/log/mysql/mysql_error.log nice = 0 socket = /var/run/mysqld/mysqld.sock [mysqld] basedir = /usr bind address = 127.0.0.1 binlog_format = ROW bulk_insert_buffer_size = 16M character-set-server = utf8mb4 collation-server = utf8mb4_general_ci concurrent_insert = 2 connect_timeout = 5 datadir = /var/lib/mysql default_storage_engine = InnoDB expire_logs_days = 2 general_log_file = /var/log/mysql/mysql.log general_log = 0 innodb_buffer_pool_size = 1024M innodb_buffer_pool_instances = 1 innodb_flush_log_at_trx_commit = 2 innodb_log_buffer_size = 32M innodb_max_dirty_pages_pct = 90 innodb_file_per_table = 1 innodb_open_files = 400 innodb_io_capacity = 4000 innodb_flush_method = O_DIRECT innodb_read_only_compressed=OFF key_buffer_size = 128M lc_messages_dir = /usr/share/mysql lc_messages = en_US log_bin = /var/log/mysql/mariadb-bin log_bin_index = /var/log/mysql/mariadb-bin.index log_error = /var/log/mysql/mysql_error.log log_slow_verbosity = query_plan log_warnings = 2 long_query_time = 1 max_allowed_packet = 16M max_binlog_size = 100M max_connections = 200 max_heap_table_size = 64M myisam_recover_options = BACKUP myisam_sort_buffer_size = 512M port = 3306 pid-file = /var/run/mysqld/mysqld.pid query_cache_limit = 2M query_cache_size = 64M query_cache_type = 1 query_cache_min_res_unit = 2k read_buffer_size = 2M read_rnd_buffer_size = 1M skip-external locking skip-name-resolve slow_query_log_file = /var/log/mysql/mariadb-slow.log slow-query-log = 1 socket = /var/run/mysqld/mysqld.sock sort_buffer_size = 4M table_open_cache = 400 thread_cache_size = 128 tmp_table_size = 64M tmpdir = /tmp transaction_isolation = READ-COMMITTED #unix_socket=OFF user = mysql wait_timeout = 600 [mysqldump] max_allowed_packet = 16M quick quote names [isamchk] key_buffer = 16M  
Restart the MariaDB database and create the Nextcloud database and the user:

service mariadb restart  
mysql -uroot -p -e "CREATE DATABASE nextcloud CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci; CREATE USER nextcloud@localhost identified by 'nextcloud'; GRANT ALL PRIVILEGES on nextcloud.* to nextcloud@localhost; FLUSH privileges;"  
Installation PHP 8.0  
apt update -q4 && apt install -y redis-server libapache2-mod-php8.0 php8.0-{fpm,gd,mysql,curl,xml,zip,intl,mbstring,bz2,ldap,apcu,bcmath,gmp,imagick,ig  
Set the correct date format (exemplary Europe/Berlin)

timedatectl set-timezone Europe/Berlin  
Before we start optimizing PHP, we back up the configuration files:

cp /etc/php/8.0/fpm/pool.d/www.conf /etc/php/8.0/fpm/pool.d/www.conf.bak cp /etc/php/8.0/fpm/php-fpm.conf /etc/php/8.0/fpm/php-fpm.conf.bak cp /etc/php/8.0/cli/php.ini /etc/php/8.0/cli/php.ini.bak cp /etc/php/8.0/fpm/php.ini /etc/php/8.0/fpm/php.ini.bak cp /etc/php/8.0/apache2/php.ini /etc/php/8.0/apache2/php.ini.bak cp /etc/php/8.0/fpm/php-fpm.conf /etc/php/8.0/fpm/php-fpm.conf.bak cp /etc/php/8.0/mods-available/apcu.ini /etc/php/8.0/mods-available/apcu.ini.bak cp /etc/ImageMagick-6/policy.xml /etc/ImageMagick-6/policy.xml.bak  
Calculation of PHP FPM tweaks

AvailableRAM=$(awk '/MemAvailable/ {printf "%d", $2/1024}' /proc/meminfo)  
AverageFPM=$(ps --no-headers -o 'rss,cmd' -C php-fpm8.0 | awk '{ sum+=$1 } END { printf ("%d\n", sum/NR/1024,"M") }')  
FPMS=$((AvailableRAM/AverageFPM))  
PMaxSS=$((FPMS*2/3))  
PMinSS=$((PMaxSS/2))  
PStartS=$(((PMaxSS+PMinSS)/2))  
Now perform all subsequent optimizations:

sed -i's/;env\[HOSTNAME\] = /env[HOSTNAME] = /' /etc/php/8.0/fpm/pool.d/www.conf sed -i's/;env\[TMP\] = /env[TMP] = /' /etc/php/8.0/fpm/pool.d/www.conf sed -i's/;env\[TMPDIR\] = /env[TMPDIR] = /' /etc/php/8.0/fpm/pool.d/www.conf sed -i's/;env\[TEMP\] = /env[TEMP] = /' /etc/php/8.0/fpm/pool.d/www.conf sed -i's/;env\[PATH\] = /env[PATH] = /' /etc/php/8.0/fpm/pool.d/www.conf sed -i's/pm.max_children =.*/pm.max_children = '$FPMS'/' /etc/php/8.0/fpm/pool.d/www.conf sed -i's/pm.start_servers =.*/pm.start_servers = '$PStartS'/' /etc/php/8.0/fpm/pool.d/www.conf sed -i 's/pm.min_spare_servers =.*/pm.min_spare_servers = '$PMinSS'/' /etc/php/8.0/fpm/pool.d/www.conf sed -i's/pm.max_spare_servers =.*/pm.max_spare_servers = '$PMaxSS'/' /etc/php/8.0/fpm/pool.d/www.conf sed -i's/;pm.max_requests =.*/pm.max_requests = 2000/' /etc/php/8.0/fpm/pool.d/www.conf sed -i 's/output_buffering =.*/output_buffering = 'Off'/' /etc/php/8.0/cli/php.ini sed -i's/max_execution_time =.*/max_execution_time = 3600/' /etc/php/8.0/cli/php.ini sed -i's/max_input_time =.*/max_input_time = 3600/' /etc/php/8.0/cli/php.ini sed -i's/post_max_size =.*/post_max_size = 10240M/' /etc/php/8.0/cli/php.ini sed -i's/upload_max_filesize =.*/upload_max_filesize = 10240M/' /etc/php/8.0/cli/php.ini sed -i's/;date.timezone.*/date.timezone = Europe\/\Berlin/' /etc/php/8.0/cli/php.ini sed -i's/memory_limit = 128M/memory_limit = 2048M/' /etc/php/8.0/fpm/php.ini sed -i's/memory_limit = 128M/memory_limit = 2048M/' /etc/php/8.0/apache2/php.ini sed -i's/output_buffering =.*/output_buffering = 'Off'/' /etc/php/8.0/fpm/php.ini sed -i's/max_execution_time =.*/max_execution_time = 3600/' /etc/php/8.0/fpm/php.ini sed -i's/max_input_time =.*/max_input_time = 3600/' /etc/php/8.0/fpm/php.ini sed -i's/post_max_size =.*/post_max_size = 10240M/' /etc/php/8.0/fpm/php.ini sed -i's/upload_max_filesize =.*/upload_max_filesize = 10240M/' /etc/php/8.0/fpm/php.ini sed -i's/;date.timezone.*/date.timezone = Europe\/\Berlin/' /etc/php/8.0/fpm/php.ini sed -i's/;session.cookie_secure.*/session.cookie_secure = True/' /etc/php/8.0/fpm/php.ini sed -i's/;opcache.enable=.*/opcache.enable=1/' /etc/php/8.0/fpm/php.ini sed -i's/;opcache.enable_cli=.*/opcache.enable_cli=1/' /etc/php/8.0/fpm/php.ini sed -i's/;opcache.memory_consumption=.*/opcache.memory_consumption=128/' /etc/php/8.0/fpm/php.ini sed -i's/;opcache.interned_strings_buffer=.*/opcache.interned_strings_buffer=8/' /etc/php/8.0/fpm/php.ini sed -i 's/;opcache.max_accelerated_files=.*/opcache.max_accelerated_files=10000/' /etc/php/8.0/fpm/php.ini sed -i's/;opcache.revalidate_freq=.*/opcache.revalidate_freq=1/' /etc/php/8.0/fpm/php.ini sed -i's/;opcache.save_comments=.*/opcache.save_comments=1/' /etc/php/8.0/fpm/php.ini sed -i's/allow_url_fopen =.*/allow_url_fopen = 1/' /etc/php/8.0/fpm/php.ini sed -i '$aapc.enable_cli=1' /etc/php/8.0/mods-available/apcu.ini sed -i "s|;emergency_restart_threshold.*|emergency_restart_threshold = 10|g" /etc/php/8.0/fpm/php-fpm.conf sed -i "s|;emergency_restart_interval.*|emergency_restart_interval = 1m|g" /etc/php/8.0/fpm/php-fpm.conf sed -i "s|;process_control_timeout.*|process_control_timeout = 10|g" /etc/php/8.0/fpm/php-fpm.conf sed -i's/rights=\"none\" pattern=\"PS\"/rights=\"read|write\" pattern=\"PS\"/' /etc/ImageMagick-6/policy.xml sed -i's/rights=\"none\" pattern=\"EPS\"/rights=\"read|write\" pattern=\"EPS\"/' /etc/ImageMagick-6/policy.xml sed -i's/rights=\"none\" pattern=\"PDF\"/rights=\"read|write\" pattern=\"PDF\"/' /etc/ImageMagick-6/policy.xml sed -i's/rights=\"none\" pattern=\"XPS\"/rights=\"read|write\" pattern=\"XPS\"/' /etc/ImageMagick-6/policy.xml ln -s /usr/local/bin/gs /usr/bin/gs  
Now restart the services

service php8.0-fpm restart  
a2dismod php8.0 && a2dismod mpm_prefork  
a2enmod proxy_fcgi setenvif mpm_event http2  
service apache2 restart  
a2enconf php8.0-fpm  
service apache2 restart && service php8.0-fpm restart  
Download Nextcloud latest  
wget https://download.nextcloud.com/server/releases/latest.zip  
unzip latest.zip && mv nextcloud/ /var/www/html/ && chown -R www-data:www-data /var/www/html/nextcloud && rm -f latest.zip  
Adjustments Redis  
cp /etc/redis/redis.conf /etc/redis/redis.conf.bak  
sed -i "s/port 6379/port 0/" /etc/redis/redis.conf  
sed -i s/\#\ unixsocket/\unixsocket/g /etc/redis/redis.conf  
sed -i "s/unixsocketperm 700/unixsocketperm 770/" /etc/redis/redis.conf  
sed -i "s/# maxclients 10000/maxclients 10240/" /etc/redis/redis.conf  
usermod -aG redis www-data  
cp /etc/sysctl.conf /etc/sysctl.conf.bak  
sed -i '$avm.overcommit_memory = 1' /etc/sysctl.conf  
reboot now  
Customize Apache2  
a2enmod rewrite headers env dir mime  
nano /etc/apache2/mods-available/http2.conf

# mod_http2 Doesn't Work with mpm_prefork <IfModule ! mpm_prefork> Protocols H2 h2c http/1.1H2Direct on

H2StreamMaxMemSize 5120000000[…]  
service apache2 restart  
cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/001-nextcloud.conf  
a2dissite 000-default.conf  
nano /etc/apache2/sites-available/001-nextcloud.conf  
Adjust the file and especially the red values to your system

<VirtualHost *:80> ServerName your.domain.deServerAlias ihre.domain.deServerAdmin mail@domain.deDocumentRoot /var/www/html/nextcloud ErrorLog /var/log/apache2/error.log CustomLog /var/log/apache2/access.log combined RewriteEngine on RewriteCond %{SERVER_NAME} =your.domain.deRewriteRule ^ https://%{SERVER_NAME}%{REQUEST_URI} [END,NE,R=permanent] </VirtualHost>  
nano /etc/apache2/sites-available/001-nextcloud-le-ssl.conf  
Accept all lines and adjust the red values to your system

<IfModule mod_ssl.c>
SSLUseStapling on
SSLStaplingCache shmcb:/var/run/ocsp(128000)
<VirtualHost *:443>
SSLCertificateFile /etc/ssl/certs/ssl-cert-snakeoil.pem
SSLCACertificateFile /etc/ssl/certs/ssl-cert-snakeoil.pem
SSLCertificateKeyFile /etc/ssl/private/ssl-cert-snakeoil.key
Protocols h2 h2c http/1.1
Header add Strict-Transport-Security: "max-age=15552000;includeSubdomains"
ServerAdmin mail@domain.de
ServerName ihre.domain.de
ServerAlias ihre.domain.de
SSLEngine on
SSLCompression off
SSLOptions +StrictRequire
SSLProtocol -all +TLSv1.3 +TLSv1.2
SSLCipherSuite ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384
SSLHonorCipherOrder off
SSLSessionTickets off
ServerSignature off
SSLStaplingResponderTimeout 5
SSLStaplingReturnResponderErrors off
SSLOpenSSLConfCmd Curves X448:secp521r1:secp384r1:prime256v1
SSLOpenSSLConfCmd ECDHParameters secp384r1
SSLOpenSSLConfCmd DHParameters "/etc/ssl/certs/dhparam.pem"
LogLevel warn
CustomLog /var/log/apache2/access.log combined
ErrorLog /var/log/apache2/error.log
DocumentRoot /var/www/html/nextcloud
<Directory /var/www/html/nextcloud/>
Options Indexes FollowSymLinks
AllowOverride All
Require all granted
Satisfy Any
</Directory>
<IfModule mod_dav.c>
Dav off
</IfModule>
<Directory /var/nc_data/>
Require all denied
</Directory>
<Files ".ht*">
Require all denied
</Files>
TraceEnable off
RewriteEngine On
RewriteCond %{REQUEST_METHOD} ^TRACK
RewriteRule .* - [R=405,L]
SetEnv HOME /var/www/html/nextcloud
SetEnv HTTP_HOME /var/www/html/nextcloud
<IfModule mod_reqtimeout.c>
RequestReadTimeout body=0
</IfModule>
</VirtualHost>
</IfModule>
Extend and activate security
openssl dhparam -dsaparam -out /etc/ssl/certs/dhparam.pem 4096
nano /etc/apache2/apache2.conf
Set the red values: ihre.domain.de ,Options FollowSymLinks MultiViews and All

ServerName your.domain.de[…] <Directory /var/www/>Options FollowSymLinks MultiViewsAllowOverride AllRequire all granted </Directory>  
service apache2 restart  
Installation of the Nextcloud  
sudo -u www-data php /var/www/html/nextcloud/occ maintenance:install --database "mysql" --database-name "nextcloud" --database-user "nextcloud" --database-pass "nextcloud" --admin-user "Nextcloud  
Correct config.php - add the lines:

sudo -u www-data nano /var/www/html/nextcloud/config/config.php  […] ), 'datadirectory' => '/var/nc_data','overwrite.cli.url' => 'https://your.domain.de/', 'htaccess.RewriteBase' => '/',[…]  
Correct Nextcloud .htaccess

sudo -u www-data php /var/www/html/nextcloud/occ maintenance:update:htaccess  
Nextcloud adjustments

mkdir -p /var/log/nextcloud/  
chown -R www-data:www-data /var/log/nextcloud  
sudo -u www-data cp /var/www/html/nextcloud/config/config.php /var/www/html/nextcloud/config/config.php.bak  
sudo -u www-data sed -i's/^[ ]*//' /var/www/html/nextcloud/config/config.php  
sudo -u www-data sed -i '/);/d' /var/www/html/nextcloud/config/config.php  
sudo -u www-data cat <<EOF >>/var/www/html/nextcloud/config/config.php 'activity_expire_days' => 14, 'auth.bruteforce.protection.enabled' => true, 'blacklisted_files' => array ( 0 => '.htaccess', 1 => 'Thumbs.db', 2 => 'thumbs.db', ), 'cron_log' => true, 'default_phone_region' => 'EN', 'enable_previews' => true, 'enabledPreviewProviders' => array ( 0 => 'OC\\Preview\\PNG', 1 => 'OC\\Preview\\JPEG', 2 => 'OC\\Preview\\GIF', 3 => 'OC\\Preview\\BMP', 4 => 'OC\\Preview\\XBitmap', 5 => 'OC\\Preview\\Movie', 6 => 'OC\\Preview\\PDF', 7 => 'OC\\Preview\\MP3', 8 => 'OC\\Preview\\TXT', 9 => 'OC\\Preview\\MarkDown', ), 'filesystem_check_changes' => 0, 'filelocking.enabled' => 'true', 'htaccess.RewriteBase' => '/', 'integrity.check.disabled' => false, 'knowledgebaseenabled' => false, 'logfile' => '/var/log/nextcloud/nextcloud.log', 'logtimezone' => 'Europe/Berlin', 'log_rotate_size' => 104857600, 'maintenance' => false, 'memcache.local' => '\\OC\\Memcache\\APCu', 'memcache.locking' => '\\OC\\Memcache\\Redis', 'overwriteprotocol' => 'https', 'preview_max_x' => 1024, 'preview_max_y' => 768, 'preview_max_scale_factor' => 1, 'redis' => array ( 'host' => '/var/run/redis/redis-server.sock', 'port' => 0, 'dbindex' => 0, 'timeout' => 1.5, ), 'quota_include_external_storage' => false, 'share_folder' => '/shares', 'skeletondirectory' => '', 'theme' => '', 'trashbin_retention_obligation' => 'auto, 14', 'updater.release.channel' => 'stable', ); EOF  
sudo -u www-data php /var/www/html/nextcloud occ config:system:set remember_login_cookie_lifetime --value="1800"  
sudo -u www-data php /var/www/html/nextcloud occ config:system:set simpleSignUpLink.shown --type=bool --value=false  
sudo -u www-data php /var/www/html/nextcloud occ config:system:set versions_retention_obligation --value="auto, 365"  
sudo -u www-data php /var/www/html/nextcloud occ config:system:set loglevel --value=2  
sudo -u www-data php /var/www/html/nextcloud/occ config:system:set trusted_domains 1 --value=your.domain.de  
a2enmod ssl && a2ensite 001-nextcloud.conf 001-nextcloud-le-ssl.conf  
service php8.0-fpm restart && service redis-server restart && service apache2 restart  
Cronjob  
crontab -u www-data -e  
Add this line at the end

*/5 * * * * php -f /var/www/html/nextcloud/cron.php > /dev/null 2>&1  
Activate the cronjob within the Nextcloud

sudo -u www-data php /var/www/html/nextcloud/occ background:cron  
Further curing  
a2dismod status  
nano /etc/apache2/conf-available/security.conf  
[…] ServerTokens Prod[…] Server Signature Off[…] TraceEnable Off[…]  
service php8.0-fpm restart && service redis-server restart && service apache2 restart  
Install fail2ban

apt install -y fail2ban ufw  
touch /etc/fail2ban/filter.d/nextcloud.conf  
cat <<EOF >/etc/fail2ban/filter.d/nextcloud.conf [Definition] _groupsre = (?:(?:,? \s*"\w+":(?:"[^"]+"|\w+))*) failregex = ^\{%(_groupsre)s,? \s*"remoteAddr":"<HOST>"%(_groupsre)s,? \s*"message":"Login failed: ^\{%(_groupsre)s,? \s*"remoteAddr":"<HOST>"%(_groupsre)s,? \s*"message":"Trusted domain error. datepattern = ,? \s*"time"\s*:\s*"%%Y-%%m-%d[T ]%%H:%%M:%S(%%z)?" EOF  
Now create a new jail file

nano /etc/fail2ban/jail.d/nextcloud.local  
Copy all the following lines into it:

[nextcloud] backend = car enabled = true port = 80,443 protocol = tcp filter = nextcloud maxretry = 5 bantime = 3600 findtime = 36000 logpath = /var/log/nextcloud/extcloud.log  
service fail2ban restart  
Activate the firewall and adjust SH port 22 if necessary

ufw allow 80/tcp && ufw allow 443/tcp && ufw allow 22/tcp  
ufw logging medium  
ufw enable  
service ufw restart
