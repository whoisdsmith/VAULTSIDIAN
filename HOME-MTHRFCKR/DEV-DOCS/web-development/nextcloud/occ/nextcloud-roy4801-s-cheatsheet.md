---
created: 2022-08-05T00:26:43 (UTC -04:00)
tags: []
source: https://docs.roy4801.tw/Services/nextcloud/
author: 
---

# nextcloud - roy4801's cheatsheet

> ## Excerpt
> A place to dump memory from my brain

---
# nextcloud
Info

On `Ubuntu 20.04`, TODO: redis, php-fpm

-   Install php, apache2, and mariadb

<table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span>
<span class="normal">2</span>
<span class="normal">3</span>
<span class="normal">4</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_1"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_1 > code"></button><code tabindex="0">sudo apt update
sudo apt install apache2 mariadb-server libapache2-mod-php7.4
sudo apt install php7.4-gd php7.4-mysql php7.4-curl php7.4-mbstring php7.4-intl
sudo apt install php7.4-gmp php7.4-bcmath php-imagick php7.4-xml php7.4-zip
</code></pre></div></td></tr></tbody></table>

-   Initialize the DB

<table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span>
<span class="normal">2</span>
<span class="normal">3</span>
<span class="normal">4</span>
<span class="normal">5</span>
<span class="normal">6</span>
<span class="normal">7</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_2"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_2 > code"></button><code tabindex="0">sudo mysql -uroot -p <span class="o">&lt;&lt;&lt;</span>EOF
CREATE USER <span class="s1">'nextcloud'</span>@<span class="s1">'localhost'</span> IDENTIFIED BY <span class="s1">'password'</span><span class="p">;</span>
CREATE DATABASE IF NOT EXISTS nextcloud CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci<span class="p">;</span>
GRANT ALL PRIVILEGES ON nextcloud.* TO <span class="s1">'nextcloud'</span>@<span class="s1">'localhost'</span><span class="p">;</span>
FLUSH PRIVILEGES<span class="p">;</span>
<span class="nb">exit</span>
EOF<span class="p">;</span>
</code></pre></div></td></tr></tbody></table>

-   Download nextcloud and install

<table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span>
<span class="normal">2</span>
<span class="normal">3</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_3"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_3 > code"></button><code><span class="nb">cd</span> /var/www
wget https://download.nextcloud.com/server/releases/nextcloud-23.0.0.zip <span class="se">\</span>
 <span class="o">&amp;&amp;</span> unzip nextcloud-23.0.0.zip <span class="o">&amp;&amp;</span> rm nextcloud-23.0.0.zip
</code></pre></div></td></tr></tbody></table>

-   Add apache2 conf: `/etc/apache2/sites-available/nextcloud.conf`
    -   Remember to change the `ServerName`
    -   Run `a2ensite nextcloud.conf` to enable

<table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal"> 1</span>
<span class="normal"> 2</span>
<span class="normal"> 3</span>
<span class="normal"> 4</span>
<span class="normal"> 5</span>
<span class="normal"> 6</span>
<span class="normal"> 7</span>
<span class="normal"> 8</span>
<span class="normal"> 9</span>
<span class="normal">10</span>
<span class="normal">11</span>
<span class="normal">12</span>
<span class="normal">13</span>
<span class="normal">14</span>
<span class="normal">15</span>
<span class="normal">16</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_4"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_4 > code"></button><code>Alias /nextcloud "/var/www/nextcloud/"

&lt;VirtualHost *:80&gt;
  DocumentRoot /var/www/nextcloud/
  ServerName  your.server.com

  &lt;Directory /var/www/nextcloud/&gt;
    Require all granted
    AllowOverride All
    Options FollowSymLinks MultiViews

    &lt;IfModule mod_dav.c&gt;
      Dav off
    &lt;/IfModule&gt;
  &lt;/Directory&gt;
&lt;/VirtualHost&gt;
</code></pre></div></td></tr></tbody></table>

-   Enable some apache2 modules

<table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span>
<span class="normal">2</span>
<span class="normal">3</span>
<span class="normal">4</span>
<span class="normal">5</span>
<span class="normal">6</span>
<span class="normal">7</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_5"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_5 > code"></button><code>sudo a2enmod rewrite
sudo a2enmod headers
sudo a2enmod env
sudo a2enmod dir
sudo a2enmod mime
sudo a2enmod ssl
sudo systemctl restart apache2
</code></pre></div></td></tr></tbody></table>

-   Pretty urls
    
    -   Add these line in `/var/www/nextcloud/config/config.php`
    -   Run `sudo -u www-data php /var/www/nextcloud/occ maintenance:update:htaccess` to update
        
        <table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span>
        <span class="normal">2</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_6"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_6 > code"></button><code>'overwrite.cli.url' =&gt; 'https://nextcloud.roy4801.tw/',
        'htaccess.RewriteBase' =&gt; '/',
        </code></pre></div></td></tr></tbody></table>
        
-   Chown the permission to `www-data`
    
    <table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_7"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_7 > code"></button><code>chown -R www-data:www-data /var/www/nextcloud/
    </code></pre></div></td></tr></tbody></table>
    
-   Install Certificate by `certbot`
    

<table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span>
<span class="normal">2</span>
<span class="normal">3</span>
<span class="normal">4</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_8"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_8 > code"></button><code>sudo apt install python3-certbot-apache
sudo certbot --apache

sudo systemctl status certbot.timer <span class="c1"># Checking the auto renew</span>
</code></pre></div></td></tr></tbody></table>

-   Add cron job
    
    <table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span>
    <span class="normal">2</span>
    <span class="normal">3</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_9"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_9 > code"></button><code>crontab -u www-data -e
    
    */5  *  *  *  *  php -f /var/www/nextcloud/cron.php
    </code></pre></div></td></tr></tbody></table>
    

## Apps

Warning

Remember to enable apps in Settings

-   Preview Generator
    
    <table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal">1</span>
    <span class="normal">2</span>
    <span class="normal">3</span>
    <span class="normal">4</span>
    <span class="normal">5</span></pre></div></td><td class="code"><div class="highlight"><pre id="__code_10"><span></span><button class="md-clipboard md-icon" title="Copy to clipboard" data-clipboard-target="#__code_10 > code"></button><code><span class="nb">cd</span> /var/www/nextcloud/apps
    git clone https://github.com/nextcloud/previewgenerator.git
    
    crontab -u www-data -e
    <span class="c1"># */10 *  *  *  *  php /var/www/nextcloud/occ preview:pre-generate</span>
    </code></pre></div></td></tr></tbody></table>
    

## HEIC

[https://eplt.medium.com/5-minutes-to-install-imagemagick-with-heic-support-on-ubuntu-18-04-digitalocean-fe2d09dcef1](https://eplt.medium.com/5-minutes-to-install-imagemagick-with-heic-support-on-ubuntu-18-04-digitalocean-fe2d09dcef1)

[https://gist.github.com/ishad0w/788555191c7037e249a439542c53e170](https://gist.github.com/ishad0w/788555191c7037e249a439542c53e170)

[https://github.com/nextcloud/photos/issues/498](https://github.com/nextcloud/photos/issues/498)

[https://github.com/major-mayer/imageconverter/](https://github.com/major-mayer/imageconverter/)

## References

[https://docs.nextcloud.com/server/latest/admin\_manual/installation/example\_ubuntu.html](https://docs.nextcloud.com/server/latest/admin_manual/installation/example_ubuntu.html)

[https://docs.nextcloud.com/server/latest/admin\_manual/installation/source\_installation.html#apache-configuration-label](https://docs.nextcloud.com/server/latest/admin_manual/installation/source_installation.html#apache-configuration-label)

[https://www.pigo.idv.tw/archives/832](https://www.pigo.idv.tw/archives/832)

[https://stackoverflow.com/questions/55183514/symfony-4-an-exception-occurred-in-driver-could-not-find-driver](https://stackoverflow.com/questions/55183514/symfony-4-an-exception-occurred-in-driver-could-not-find-driver)
