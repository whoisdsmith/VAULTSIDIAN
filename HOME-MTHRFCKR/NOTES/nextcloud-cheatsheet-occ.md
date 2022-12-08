# Nextcloud Cheatsheet / occ

News: <https://nextcloud.com/blog/category/release/>

## Status

  * sudo -u www-data php /var/www/nextcloud/occ status

Reset Admin Password

  * sudo -u www-data php /var/www/nextcloud/occ user:resetpassword admin

## Scan files

  * sudo -u www-data php /var/www/nextcloud/occ files:scan -v --all
  * sudo -u www-data php /var/www/nextcloud/occ files:scan -v myusername
  * sudo -u www-data php /var/www/nextcloud/occ files:scan -v --path="/myusername/files/myfolder/mysubfolder" myusername
  * For external storage one has to use a user, e.g. admin 
    * sudo -u www-data /usr/bin/php /var/www/nextcloud/occ files:scan -v --path="/admin/files/name_of_external_storage"

#### Error while scanning: "Entry path/to/file will not be accessible due to incompatible encoding"

  * German Umlauts with different encoding (OS X normalization form D for UTF-8)
  * Solution: 
    * apt install convmv
    * convmv -f utf-8 -t utf-8 --nfc -r /srv/nextcloud/
    * check, then with --notest
    * convmv -f utf-8 -t utf-8 --nfc -r --notest /srv/nextcloud/
    * \+ rescan with occ

## Upgrade

  * sudo -u www-data php /var/www/nextcloud/updater/updater.phar --no-interaction
  * sudo -u www-data php /var/www/nextcloud/occ upgrade

Turn maintenance mode on/off

  * sudo -u www-data php /var/www/nextcloud/occ maintenance:mode --on
  * sudo -u www-data php /var/www/nextcloud/occ maintenance:mode --off

Add missing indices

  * sudo -u www-data php /var/www/nextcloud/occ db:add-missing-indices

Convert to bigint

  * sudo -u www-data php /var/www/nextcloud/occ db:convert-filecache-bigint

Add missing columns:

  * sudo -u www-data php /var/www/nextcloud/occ db:add-missing-columns

Add missing primary keys:

  * sudo -u www-data php /var/www/nextcloud/occ db:add-missing-primary-keys

Fix interupted upgrades

  * sudo -u www-data php /var/www/nextcloud/occ maintenance:repair

## Install apps from the command line

<https://docs.nextcloud.com/server/20/admin_manual/configuration_server/occ_command.html#apps-commands-label>

  * sudo -u www-data php /var/www/nextcloud/occ app:list
  * sudo -u www-data php /var/www/nextcloud/occ app:install files_external
  * sudo -u www-data php /var/www/nextcloud/occ app:enable files_external

Configure

  * sudo -u www-data php /var/www/nextcloud/occ config:list

## Clients

### Ubuntu

#### Integration with Nautilus

  * sudo apt install nautilus-nextcloud
    * old: python-nautilus nextcloud-client-nautilus
  * Log off / Log in again

## Issues

### Calendar

  * <https://help.nextcloud.com/t/severe-mobile-issues-no-create-and-update-of-events-possible/53987>

CSS fix for V16 / V1.7.0

  * Menu -> Apps -> Add/Enable "Custom CSS" app
  * Menu -> Settings -> Administration -> Theming
  * Add custom CSS and save: 
    *         /* Fix mobile right sidebar issues (create, update buttons hidden) */
        
         @media only screen and (max-height: 760px) {
        
          #app-sidebar {
            height: auto; /* there are problems with the height calculation */
            width: auto; /* use max width on mobile */
            top: 0; /* surpress top margin when not fixed (see below */
          }
        
          .modal-content #app-sidebar {
            position: relative;      /* do not fix sidebar to right side */
          }
        }
        
        /* OTHER TWEAKS */
        
        /* bold time */
        .fc-day-grid-event .fc-time {
            opacity: 1;
            font-size: 90%;
            font-weight: bold;
        }
        
        /* show event name in mobile */
        .fc-day-grid-event .fc-content {
            white-space: normal;
        }
        
        
        		
        
        	
    	
    
    
    
    
    
    ## Install OnlyOffice in Nextcloud 18
    
    
    
    
    
    
    	
      * Apps -> Office -> Install and enable OnlyOffice Connector
    
    	
      * Apps -> Office -> Install and enable Documentserver Community
    	
        		
            * Nope, does not work, there is currently a curl time out.
        
        		
            * Go to <https://apps.nextcloud.com/apps/documentserver_community/releases?platform=18#18>
        
        		
            * And copy the download link
        
        		
            * ssh to your server
        
        		
            * cd /tmp/
        
        		
            * wget <https://github.com/nextcloud/documentserver_community/releases/download/vX.X.X/documentserver_community.tar.gz>
        		
            			
                  * _wget <https://github.com/nextcloud/documentserver_community/releases/download/v0.1.5/documentserver_community.tar.gz>_
            
            		
        		
        
        		
            * tar -xvzf documentserver_community.tar.gz
        
        		
            * 
        		
        
        mv documentserver_community /var/www/nextcloud/apps/
        
        
        		
        
        		
            * 
        		
        
        chown www-data:www-data /var/www/nextcloud/apps/documentserver_community/ -R
        
        
        		
        
        		
            * 
        		
        
        rm /tmp/documentserver_community.tar.gz
        
        
        		
        
        	
    	
    
    	
      * 
    	
    
    Apps -> Documentserver Community -> Enable
    
    
    	
    
    	
      * 
    	
    
    Test by going to "Files" and create a new office document
    
    
    	
    
    	
      * 
    	
    
    <s>Workaround for problem "Only office changes are not saved back to Nextcloud files"</s>
    
    
    
    	
        		
            * 
        		
        
        <s>vi /etc/crontab</s>
        
        
        
        		
            			
                  * 
            			
            
            <s>*/1 *   * * *   www-data php /var/www/nextcloud/occ documentserver:flush > /dev/null 2>&1</s>
            
            
            			
            
            		
        		
        
        	
    	
    
    
    
    
    
    ##  
    
    
    
    
    
    ## Update to PHP7.4 on Ubuntu 18.04
    
    
    
    
    
    
    	
      * apt --yes remove 'php*'
    
    	
      * add-apt-repository ppa:ondrej/php
    
    	
      * apt update
    
    	
      * apt install php7.4-gd php7.4-ldap php7.4-imap php7.4-json php7.4-curl php7.4-intl php7.4-bcmath php7.4-gmp php7.4-imagick php7.4-mbstring php7.4-redis php7.4-xml php7.4-zip php7.4-apcu php7.4-apcu-bc php7.4-mysql
    
    
    
    
    
    
    
    With FPM
    
    
    
    
    
    
    	
      * a2dismod php7.4 mpm_prefork
    
    	
      * apt install php7.4-fpm
    
    	
      * a2enmod mpm_event proxy_fcgi setenvif
    
    	
      * a2enconf php7.4-fpm
    
    	
      * vi /etc/apache2/apache2.conf
    	
        		
            * 
        		
        
        # Enable http2  
        
        		Protocols h2 h2c http/1.1  
        
        		  
        
        		# Add security headers  
        
        		      Header always add Strict-Transport-Security "max-age=15768000; includeSubDomains; preload"
        
        
        		
        
        	
    	
    
    
    
    
    
    
    	
      * vi /etc/php/7.4/fpm/pool.d/www.conf
    	
        		
            *       pm = dynamic  
        
        		      pm.max_children = 120  
        
        		      pm.start_servers = 12  
        
        		      pm.min_spare_servers = 6  
        
        		      pm.max_spare_servers = 18
        
        	
    	
    
    	
      * vi /etc/php/7.4/fpm/php.ini
    	
        		
            * 
        		
        
        memory_limit = 512M
        
        
        		
        
        		
            * 
        		
        
        [opcache]  
        
        		; Determines if Zend OPCache is enabled  
        
        		opcache.enable = 1
        
        
        
        		
        
        ; Determines if Zend OPCache is enabled for the CLI version of PHP  
        
        		opcache.enable_cli = 1
        
        
        
        		
        
        ; The OPcache shared memory storage size.  
        
        		opcache.memory_consumption = 128
        
        
        
        		
        
        ; The amount of memory for interned strings in Mbytes.  
        
        		opcache.interned_strings_buffer = 8
        
        
        
        		
        
        ; The maximum number of keys (scripts) in the OPcache hash table.  
        
        		; Only numbers between 200 and 1000000 are allowed.  
        
        		opcache.max_accelerated_files = 10000
        		 
        
        
        
        		
        
        ; How often (in seconds) to check file timestamps for changes to the shared  
        
        		; memory storage allocation. ("1" means validate once per second, but only  
        
        		; once per request. "0" means always validate)  
        
        		opcache.revalidate_freq = 1
        
        
        		
        
        	
    	
    
    	
      * 
    	
    
    	
    
    service php7.4-fpm restart
    
    
    
    	
    
    	
    
    	
    	 
    
    	
    
    	
    	
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
      
    
    
    


___

#article 