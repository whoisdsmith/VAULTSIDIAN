---
tags:: occ
created: 2022-07-16T20:58:22 (UTC -04:00)
tags: []
source: https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html
author: 
---

# Config.php Parameters :: ownCloud Documentation

> ## Excerpt
> Config.php Parameters

---
# Config.php Parameters

Table of Contents

-   [Introduction](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#introduction)
-   [Default Parameters](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#default-parameters)
    -   [Unique identifier for your ownCloud installation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#unique-identifier-for-your-owncloud-installation)
    -   [Auto-generated salt used to hash all passwords](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#auto-generated-salt-used-to-hash-all-passwords)
    -   [Define list of trusted domains that users can log into](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-list-of-trusted-domains-that-users-can-log-into)
    -   [Define global list of CORS domains](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-global-list-of-cors-domains)
    -   [Define the directory where user files are stored](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-directory-where-user-files-are-stored)
    -   [Define the directory where the crash logs will be stored](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-directory-where-the-crash-logs-will-be-stored)
    -   [Current version number of your ownCloud installation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#current-version-number-of-your-owncloud-installation)
    -   [Show or hide the ownCloud version information in `status.php`](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-or-hide-the-owncloud-version-information-in-status-php)
    -   [Show or hide the server hostname in `status.php`](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-or-hide-the-server-hostname-in-status-php)
    -   [Show the short hostname in `status.php`](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-the-short-hostname-in-status-php)
    -   [Identify the database used with this installation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#identify-the-database-used-with-this-installation)
    -   [Define the database server host name](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-database-server-host-name)
    -   [Define the ownCloud database name](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-owncloud-database-name)
    -   [Define the ownCloud database user](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-owncloud-database-user)
    -   [Define the password for the database user](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-password-for-the-database-user)
    -   [Define the prefix for the ownCloud tables in the database](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-prefix-for-the-owncloud-tables-in-the-database)
    -   [Indicate whether the ownCloud instance was installed successfully](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#indicate-whether-the-owncloud-instance-was-installed-successfully)
-   [User Experience](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#user-experience)
    -   [Define the default language of your ownCloud instance](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-default-language-of-your-owncloud-instance)
    -   [Define the default app to open on user login](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-default-app-to-open-on-user-login)
    -   [Enable or disable avatars or user profile photos](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-avatars-or-user-profile-photos)
    -   [Allow or disallow users to change their display names](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-or-disallow-users-to-change-their-display-names)
    -   [Allow or disallow users to change their email addresses](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-or-disallow-users-to-change-their-email-addresses)
    -   [Define the lifetime of the remember-login cookie](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-lifetime-of-the-remember-login-cookie)
    -   [Define the lifetime of a session after inactivity](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-lifetime-of-a-session-after-inactivity)
    -   [Enable session keep-alive when a user is logged in to the Web UI](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-session-keep-alive-when-a-user-is-logged-in-to-the-web-ui)
    -   [Enable to force user logout](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-to-force-user-logout)
    -   [Enforce token only authentication for apps and clients connecting to ownCloud](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enforce-token-only-authentication-for-apps-and-clients-connecting-to-owncloud)
    -   [Enforce strict login check with user backend](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enforce-strict-login-check-with-user-backend)
    -   [Define additional login buttons on the logon screen](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-additional-login-buttons-on-the-logon-screen)
    -   [Enable or disable ownCloud’s built-in CSRF protection mechanism](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-ownclouds-built-in-csrf-protection-mechanism)
    -   [Define how to relax same site cookie settings](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-how-to-relax-same-site-cookie-settings)
    -   [Define the directory where the skeleton files are located](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-directory-where-the-skeleton-files-are-located)
    -   [Define the `user_backends` app](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-user_backends-app)
    -   [Define a custom link to reset passwords](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-a-custom-link-to-reset-passwords)
    -   [Allow medial search on user account properties](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-medial-search-on-user-account-properties)
    -   [Allow medial search on the group id](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-medial-search-on-the-group-id)
    -   [Define minimum characters entered before a search returns results](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-minimum-characters-entered-before-a-search-returns-results)
-   [Mail Parameters](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#mail-parameters)
    -   [Define the email RETURN address](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-email-return-address)
    -   [Define the email FROM address](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-email-from-address)
    -   [Enable or disable SMTP class debugging](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-smtp-class-debugging)
    -   [Define the mode for sending an email](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-mode-for-sending-an-email)
    -   [Define the IP address of your mail server host](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-ip-address-of-your-mail-server-host)
    -   [Define the port for sending an email](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-port-for-sending-an-email)
    -   [Define the SMTP server timeout](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-server-timeout)
    -   [Define the SMTP security style](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-security-style)
    -   [Define the SMTP authentication](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-authentication)
    -   [Define the SMTP authentication type](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-authentication-type)
    -   [Define the SMTP authentication username](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-authentication-username)
    -   [Define the SMTP authentication password](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-authentication-password)
-   [Proxy Configurations](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#proxy-configurations)
    -   [Override automatic proxy detection](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-automatic-proxy-detection)
    -   [Override protocol (http/https) usage](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-protocol-httphttps-usage)
    -   [Override ownClouds webroot](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-ownclouds-webroot)
    -   [Override condition for the remote IP address with a regular expression](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-condition-for-the-remote-ip-address-with-a-regular-expression)
    -   [Override cli URL](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-cli-url)
    -   [Define the Web base URL](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-web-base-url)
    -   [Define rewrite private and public links](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-rewrite-private-and-public-links)
    -   [Define clean URLs without `/index.php`](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-clean-urls-without-index-php)
    -   [Define the URL of your proxy server](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-url-of-your-proxy-server)
    -   [Define a list of hostnames that won’t be proxied.](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-a-list-of-hostnames-that-wont-be-proxied)
    -   [Define proxy authentication](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-proxy-authentication)
-   [Deleted Items (trash bin)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#deleted-items-trash-bin)
    -   [Define the trashbin retention obligation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-trashbin-retention-obligation)
    -   [Define the trashbin purge limit](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-trashbin-purge-limit)
    -   [Define trashbin directory skip list](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-trashbin-directory-skip-list)
    -   [Define trashbin file extension skip list](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-trashbin-file-extension-skip-list)
    -   [Define trashbin threshold size](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-trashbin-threshold-size)
-   [File versions](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#file-versions)
    -   [Define the files versions retention obligation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-files-versions-retention-obligation)
-   [ownCloud Verifications](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#owncloud-verifications)
    -   [Enable or disable updatechecker](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-updatechecker)
    -   [Define the updatechecker URL](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-updatechecker-url)
    -   [Check for an internet connection](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#check-for-an-internet-connection)
    -   [Check for a `.well-known` setup](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#check-for-a-well-known-setup)
    -   [Define if config.php is read only](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-if-config-php-is-read-only)
    -   [Define ownCloud operation modes](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-owncloud-operation-modes)
-   [Logging](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#logging)
    -   [Define the log type](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-type)
    -   [Define the log path](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-path)
    -   [Define the log level](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-level)
    -   [Define the syslog tag](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-syslog-tag)
    -   [Define the syslog format](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-syslog-format)
    -   [Define log conditions](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-log-conditions)
    -   [Define the log date format](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-date-format)
    -   [Define the log timezone](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-timezone)
    -   [Define logging if Cron ran successfully](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-logging-if-cron-ran-successfully)
    -   [Define the maximum log rotation file size](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-log-rotation-file-size)
-   [Alternate Code Locations](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#alternate-code-locations)
    -   [Define alternative app directories](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-alternative-app-directories)
-   [Previews](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#previews)
    -   [Enable preview generation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-preview-generation)
    -   [Define the preview path](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-preview-path)
    -   [Define the maximum x-axis width for previews](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-x-axis-width-for-previews)
    -   [Define the maximum y-axis width for previews](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-y-axis-width-for-previews)
    -   [Define the maximum preview scale factor](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-preview-scale-factor)
    -   [Define the maximum preview filesize limit](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-preview-filesize-limit)
    -   [Define the custom path for the LibreOffice / OpenOffice binary](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-custom-path-for-the-libreoffice-openoffice-binary)
    -   [Define additional arguments for LibreOffice / OpenOffice](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-additional-arguments-for-libreoffice-openoffice)
    -   [Define preview providers](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-preview-providers)
    -   [Define the jpeg preview quality](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-jpeg-preview-quality)
-   [Comments](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#comments)
    -   [Define an alternative Comments Manager](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-an-alternative-comments-manager)
    -   [Define an alternative System Tags Manager](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-an-alternative-system-tags-manager)
-   [Maintenance](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#maintenance)
    -   [Enable maintenance mode to disable ownCloud](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-maintenance-mode-to-disable-owncloud)
    -   [Enable or disable `single user mode`](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-single-user-mode)
-   [SSL](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#ssl)
    -   [Extra SSL options to be used for configuration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#extra-ssl-options-to-be-used-for-configuration)
    -   [Allow the configuration of system-wide trusted certificates](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-the-configuration-of-system-wide-trusted-certificates)
-   [Memory caching backend configuration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#memory-caching-backend-configuration)
    -   [Memory caching backend for locally stored data](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#memory-caching-backend-for-locally-stored-data)
    -   [Memory caching backend for distributed data](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#memory-caching-backend-for-distributed-data)
    -   [Define Redis connection details](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-redis-connection-details)
    -   [Define Redis Cluster connection details](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-redis-cluster-connection-details)
    -   [Define server details for memcached servers to use for memory caching](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-server-details-for-memcached-servers-to-use-for-memory-caching)
    -   [Define connection options for memcached](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-connection-options-for-memcached)
    -   [Define the location of the cache folder](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-location-of-the-cache-folder)
    -   [Define the TTL for garbage collection](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-ttl-for-garbage-collection)
    -   [Define the DAV chunk base directory](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-dav-chunk-base-directory)
-   [Sharing](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#sharing)
    -   [Define an alternative Share Provider](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-an-alternative-share-provider)
    -   [Allow schema fallback for federated sharing servers](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-schema-fallback-for-federated-sharing-servers)
    -   [Show a quick action for the public link creation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-a-quick-action-for-the-public-link-creation)
    -   [Save and display version of uploaded and edited files.](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#save-and-display-version-of-uploaded-and-edited-files)
-   [All other configuration options](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#all-other-configuration-options)
    -   [Define additional database driver options](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-additional-database-driver-options)
    -   [Define sqlite3 journal mode](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-sqlite3-journal-mode)
    -   [Define MySQL 3/4 byte character handling](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-mysql-34-byte-character-handling)
    -   [Force a specific database platform class](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#force-a-specific-database-platform-class)
    -   [Define supported database types](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-supported-database-types)
    -   [Define the location for temporary files](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-location-for-temporary-files)
    -   [Define the hashing cost](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-hashing-cost)
    -   [Define blacklisted files](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-blacklisted-files)
    -   [Define blacklisted files regular expression(s)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-blacklisted-files-regular-expressions)
    -   [Define excluded directories](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-excluded-directories)
    -   [Define excluded directories regular expression(s)](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-excluded-directories-regular-expressions)
    -   [Define files that are excluded from integrity checking](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-files-that-are-excluded-from-integrity-checking)
    -   [Define apps or themes that are excluded from integrity checking](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-apps-or-themes-that-are-excluded-from-integrity-checking)
    -   [Define a default folder for shared files and folders other than root](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-a-default-folder-for-shared-files-and-folders-other-than-root)
    -   [Define the default cipher for encrypting files](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-default-cipher-for-encrypting-files)
    -   [Define the file format for encrypting files](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-file-format-for-encrypting-files)
    -   [Define the minimum supported ownCloud desktop client version](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-minimum-supported-owncloud-desktop-client-version)
    -   [Define the suggested poll interval for clients](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-suggested-poll-interval-for-clients)
    -   [Define whether to include external storage in quota calculation](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-whether-to-include-external-storage-in-quota-calculation)
    -   [Define how often filesystem changes are detected](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-how-often-filesystem-changes-are-detected)
    -   [Define unsuccessful mountpoint rename attempts](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-unsuccessful-mountpoint-rename-attempts)
    -   [Define where part files are located](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-where-part-files-are-located)
    -   [Prevent cache changes due to changes in the filesystem](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#prevent-cache-changes-due-to-changes-in-the-filesystem)
    -   [Define ownClouds internal secret](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-ownclouds-internal-secret)
    -   [Define list of trusted proxy servers](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-list-of-trusted-proxy-servers)
    -   [Define `forwarded_for_headers`](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-forwarded_for_headers)
    -   [Define the maximum filesize for animated GIF´s](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-filesize-for-animated-gifs)
    -   [Enable transactional file locking](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-transactional-file-locking)
    -   [Define the TTL for file locking](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-ttl-for-file-locking)
    -   [Define the memory caching backend for file locking](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-memory-caching-backend-for-file-locking)
    -   [Disable the web based updater](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#disable-the-web-based-updater)
    -   [Define whether or not to enable automatic update of market apps](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-whether-or-not-to-enable-automatic-update-of-market-apps)
    -   [Enable debugging mode for this ownCloud instance](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-debugging-mode-for-this-owncloud-instance)
    -   [Define the data-fingerprint of the current data served](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-data-fingerprint-of-the-current-data-served)
    -   [Define if you have copied the sample configuration](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-if-you-have-copied-the-sample-configuration)
    -   [Enable or disable the files\_external local mount option](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-the-files_external-local-mount-option)
    -   [Enable or disable debug logging for SMB access](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-debug-logging-for-smb-access)
    -   [Enable or disable async DAV extensions](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-async-dav-extensions)
    -   [Enable propfind depth infinity requests](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-propfind-depth-infinity-requests)
    -   [Show the grace period popup](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-the-grace-period-popup)
    -   [Link to get a demo key during active grace period](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#link-to-get-a-demo-key-during-active-grace-period)

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#introduction)Introduction

ownCloud uses the `config/config.php` file to control server operations. `config/config.sample.php` lists all the configurable parameters within ownCloud, along with example or default values. This document provides a more detailed reference. Most options are configurable on your Admin page, so it is usually not necessary to edit `config/config.php`.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">The installer creates a configuration containing the essential parameters.<br>Only manually add configuration parameters to <code>config/config.php</code> if you need to use a special value for a parameter. <strong>Do not copy everything from</strong> <code>config/config.sample.php</code> <strong>. Only enter the parameters you wish to modify!</strong></td></tr></tbody></table>

ownCloud supports loading configuration parameters from multiple files. You can add arbitrary files ending with .config.php in the config/ directory, for example you could place your email server configuration in email.config.php. This allows you to easily create and manage custom configurations, or to divide a large complex configuration file into a set of smaller files. These custom files are not overwritten by ownCloud, and the values in these files take precedence over config.php.

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#default-parameters)Default Parameters

These parameters are configured by the ownCloud installer and are required for your ownCloud server to operate.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#unique-identifier-for-your-owncloud-installation)Unique identifier for your ownCloud installation

This unique identifier is created automatically by the installer.

This example is for documentation only, and you should never use it because it will not work. A valid `instanceid` is created when you install ownCloud. Needs to start with a letter.

'instanceid' ⇒ 'd3c944a9a',

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample)Code Sample

```php
'instanceid' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#auto-generated-salt-used-to-hash-all-passwords)Auto-generated salt used to hash all passwords

The salt used to hash all passwords and is auto-generated by the ownCloud installer.

(There are also per-user salts.) If you lose this salt, you lose all your passwords. This example is for documentation only, and you should never use it.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-2)Code Sample

```php
'passwordsalt' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-list-of-trusted-domains-that-users-can-log-into)Define list of trusted domains that users can log into

Specifying trusted domains prevents host header poisoning.

Do not remove this, as it performs necessary security checks. Please consider that for backend processes like background jobs or occ commands, the URL parameter in key `overwrite.cli.url` is used. For more details, please see that key.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-3)Code Sample

```php
'trusted_domains' => [
'demo.example.org',
'otherdomain.example.org',
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-global-list-of-cors-domains)Define global list of CORS domains

All users can use tools running CORS (Cross-Origin Resource Sharing) requests from the listed domains.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-4)Code Sample

```php
'cors.allowed-domains' => [
'https://foo.example.org',
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-directory-where-user-files-are-stored)Define the directory where user files are stored

This defaults to `data/` in the ownCloud directory.

The SQLite database is also stored here, when you use SQLite. (SQLite is not available in ownCloud Enterprise Edition)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-5)Code Sample

```php
'datadirectory' => '/var/www/owncloud/data',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-directory-where-the-crash-logs-will-be-stored)Define the directory where the crash logs will be stored

By default, this will be the same as the one configured as "datadirectory".

The directory MUST EXIST and be WRITABLE by the web server. Note that crashes are extremely rare (although they can come in burst due to multiple requests), so the default location is usually fine. Also note that the log can contain sensitive information, but it should be useful to pinpoint where is the problem.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-6)Code Sample

```php
'crashdirectory' => '/var/www/owncloud/data',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#current-version-number-of-your-owncloud-installation)Current version number of your ownCloud installation

This is set up during installation and update, so you shouldn’t need to change it.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-7)Code Sample

```php
'version' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-or-hide-the-owncloud-version-information-in-status-php)Show or hide the ownCloud version information in `status.php`

This hardens an ownCloud instance by hiding the version information in `status.php`.

This can be a legitimate step. Please consult the documentation before enabling this.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-8)Code Sample

```php
'version.hide' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-or-hide-the-server-hostname-in-status-php)Show or hide the server hostname in `status.php`

Optional config option, defaults to hidden.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-9)Code Sample

```php
'show_server_hostname' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-the-short-hostname-in-status-php)Show the short hostname in `status.php`

Optional config option, defaults to use the gethostname() return value.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-10)Code Sample

```php
'use_relative_domain_name' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#identify-the-database-used-with-this-installation)Identify the database used with this installation

See also config option `supportedDatabases`

Available: - sqlite (SQLite3 - Not in Enterprise Edition) - mysql (MySQL/MariaDB) - pgsql (PostgreSQL) - oci (Oracle - Enterprise Edition Only)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-11)Code Sample

```php
'dbtype' => 'mysql',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-database-server-host-name)Define the database server host name

For example `localhost`, `hostname`, `hostname.example.com`, or the IP address.

To specify a port use: `hostname:##`; To specify a Unix socket use: `localhost:/path/to/socket`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-12)Code Sample

```php
'dbhost' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-owncloud-database-name)Define the ownCloud database name

The name of the ownCloud database which is set during installation.

You should not need to change this.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-13)Code Sample

```php
'dbname' => 'owncloud',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-owncloud-database-user)Define the ownCloud database user

This must be unique across ownCloud instances using the same SQL database.

This is setup during installation, so you shouldn’t need to change it.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-14)Code Sample

```php
'dbuser' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-password-for-the-database-user)Define the password for the database user

This is set up during installation, so you shouldn’t need to change it.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-15)Code Sample

```php
'dbpassword' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-prefix-for-the-owncloud-tables-in-the-database)Define the prefix for the ownCloud tables in the database

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-16)Code Sample

```php
'dbtableprefix' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#indicate-whether-the-owncloud-instance-was-installed-successfully)Indicate whether the ownCloud instance was installed successfully

`true` indicates a successful installation, `false` indicates an unsuccessful installation.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-17)Code Sample

```php
'installed' => false,
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#user-experience)User Experience

These optional parameters control some aspects of the user interface. Default values, where present, are shown.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-default-language-of-your-owncloud-instance)Define the default language of your ownCloud instance

Using ISO\_639-1 language codes such as `en` for English, `de` for German, and `fr` for French.

Overrides automatic language detection on public pages like login or shared items. User’s language preferences configured under `personal → language` override this setting after they have logged in.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-18)Code Sample

```php
'default_language' => 'en_GB',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-default-app-to-open-on-user-login)Define the default app to open on user login

Use the app names as they appear in the URL after clicking them in the Apps menu, such as files, documents or calendar etc. You can use a comma-separated list of app names, so if the first app is not enabled for a user then ownCloud will try the second one, and so on. If no enabled apps are found it defaults to the Files app.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-19)Code Sample

```php
'defaultapp' => 'files',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-avatars-or-user-profile-photos)Enable or disable avatars or user profile photos

`true` enables avatars, or user profile photos, `false` disables them.

These appear on the User page, on user’s Personal pages and are used by some apps (contacts, mail, etc).

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-20)Code Sample

```php
'enable_avatars' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-or-disallow-users-to-change-their-display-names)Allow or disallow users to change their display names

`true` allows users to change their display names (on their Personal pages), `false` prevents them from changing their display names.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-21)Code Sample

```php
'allow_user_to_change_display_name' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-or-disallow-users-to-change-their-email-addresses)Allow or disallow users to change their email addresses

`true` allows users to change their email address (on their Personal pages), `false` prevents them from changing their email address.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-22)Code Sample

```php
'allow_user_to_change_mail_address' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-lifetime-of-the-remember-login-cookie)Define the lifetime of the remember-login cookie

The remember-login cookie is set when the user clicks the `remember` checkbox on the login screen. The default is 15 days, expressed in seconds.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-23)Code Sample

```php
'remember_login_cookie_lifetime' => 60*60*24*15,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-lifetime-of-a-session-after-inactivity)Define the lifetime of a session after inactivity

The web UI might send a "heartbeat" based on the activity happening in order to extend the session lifetime and keeping it from timing out prematurely. If there is no activity happening and the lifetime is reached, you’ll have to login again.

The default is 20 minutes, expressed in seconds.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-24)Code Sample

```php
'session_lifetime' => 60 * 20,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-session-keep-alive-when-a-user-is-logged-in-to-the-web-ui)Enable session keep-alive when a user is logged in to the Web UI

Enabling this sends a "heartbeat" to the server to keep it from timing out regardless of any activity happening. This heartbeat will keep extending the session over again, so the user won’t be logged out even if he isn’t active in the web UI.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-25)Code Sample

```php
'session_keepalive' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-to-force-user-logout)Enable to force user logout

Force the user to get logged out after the specified number of seconds when the tab or browser gets closed. A negative or 0 value disables this feature.

Note that the user can still access the page without re-authenticating (having valid access) if the timeout has not been reached. The recommended minimum value is 5 or 10 seconds. Using a lower value might cause unwanted logouts for users.

Note that this feature works properly if the user uses one tab only. If a user uses multiple tabs, closing one of them will likely force the rest to re-authenticate.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-26)Code Sample

```php
'session_forced_logout_timeout' => 0,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enforce-token-only-authentication-for-apps-and-clients-connecting-to-owncloud)Enforce token only authentication for apps and clients connecting to ownCloud

If enabled, all access requests using the user’s password are blocked for enhanced security.

Users have to generate special app-passwords (tokens) for their apps or clients in their personal settings which are further used for app or client authentication. Browser logon is not affected.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-27)Code Sample

```php
'token_auth_enforced' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enforce-strict-login-check-with-user-backend)Enforce strict login check with user backend

If enabled, strict login check for password in user backend will be enforced, meaning only the login name typed by the user would be validated. With this configuration enabled, e.g. an additional check for email will not be performed.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-28)Code Sample

```php
'strict_login_enforced' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-additional-login-buttons-on-the-logon-screen)Define additional login buttons on the logon screen

Provides the ability to create additional login buttons on the logon screen, for e.g., SSO integration 'login.alternatives' ⇒ \[ \['href' ⇒ 'https://www.testshib.org/Shibboleth.sso/ProtectNetwork?target=https%3A%2F%2Fmy.owncloud.tld%2Flogin%2Fsso-saml%2F', 'name' ⇒ 'ProtectNetwork', 'img' ⇒ '/img/PN\_sign-in.gif'\], \['href' ⇒ 'https://www.testshib.org/Shibboleth.sso/OpenIdP.org?target=https%3A%2F%2Fmy.owncloud.tld%2Flogin%2Fsso-saml%2F', 'name' ⇒ 'OpenIdP.org', 'img' ⇒ '/img/openidp.png'\], \]

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-29)Code Sample

```php
'login.alternatives' => [],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-ownclouds-built-in-csrf-protection-mechanism)Enable or disable ownCloud’s built-in CSRF protection mechanism

In some specific setups CSRF protection is handled in the environment, e.g., running F5 ASM. In these cases the built-in mechanism is not needed and can be disabled. Generally speaking, however, this config switch should be left unchanged.

<table><tbody><tr><td class="icon"><i class="fa icon-warning" title="Warning"></i></td><td class="content">leave this as is if you’re not sure what it does.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-30)Code Sample

```php
'csrf.disabled' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-how-to-relax-same-site-cookie-settings)Define how to relax same site cookie settings

Possible values: `Strict`, `Lax` or `None`.

Setting the same site cookie to `None` is necessary in case of OpenID Connect. For more information about the impact of the values see: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite#values](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite#values) and [https://web.dev/schemeful-samesite/](https://web.dev/schemeful-samesite/)

-   Use 'strict' whenever possible
    
-   If necessary relax to 'lax'
    
-   Use 'none' if it needs to be relaxed even further
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-31)Code Sample

```php
'http.cookie.samesite' => 'Strict',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-directory-where-the-skeleton-files-are-located)Define the directory where the skeleton files are located

These files will be copied to the data directory of new users.

Set this to the empty string if you do not want to copy any skeleton files. A valid path must be given for this key otherwise errors will be generated in owncloud.log.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-32)Code Sample

```php
'skeletondirectory' => '/path/to/owncloud/core/skeleton',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-user_backends-app)Define the `user_backends` app

Those need to be enabled first and allow you to configure alternate authentication backends.

Supported backends are: IMAP (OC\_User\_IMAP), SMB (OC\_User\_SMB), and FTP (OC\_User\_FTP).

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-33)Code Sample

```php
'user_backends' => [
[
'class' => 'OC_User_IMAP',
'arguments' => ['{imap.gmail.com:993/imap/ssl}INBOX']
]
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-a-custom-link-to-reset-passwords)Define a custom link to reset passwords

If your user backend does not allow password resets (e.g. when it’s a read-only user backend like LDAP), you can specify a custom link, where the user is redirected to, when clicking the "reset password" link after a failed login-attempt.

If you do not want to provide any link, replace the URL with 'disabled'.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-34)Code Sample

```php
'lost_password_link' => 'https://example.org/link/to/password/reset',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-medial-search-on-user-account-properties)Allow medial search on user account properties

These account properties can be display name, user id, email, and other search terms.

Allows finding 'Alice' when searching for 'lic'. May slow down user search. Disable this if you encounter slow username search in the sharing dialog.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-35)Code Sample

```php
'accounts.enable_medial_search' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-medial-search-on-the-group-id)Allow medial search on the group id

Allows finding 'test' in groups when searching for 'es'.

This is only used in the DB group backend (local groups). This won’t be used against LDAP, Shibboleth or any other group backend.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-36)Code Sample

```php
'groups.enable_medial_search' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-minimum-characters-entered-before-a-search-returns-results)Define minimum characters entered before a search returns results

Defines the minimum characters entered before a search returns results for users or groups in the share autocomplete form. Lower values increase search time especially for large backends.

Any exact matches to a user or group will be returned, even though less than the minimum characters have been entered. The search is case-insensitive. For example, entering "tom" will always return "Tom" if there is an exact match.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-37)Code Sample

```php
'user.search_min_length' => 2,
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#mail-parameters)Mail Parameters

These configure the email settings for ownCloud notifications and password resets.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-email-return-address)Define the email RETURN address

The return address that you want to appear on emails sent by the ownCloud server.

Example: `oc-admin@example.com`, substituting your own domain, of course.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-38)Code Sample

```php
'mail_domain' => 'example.com',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-email-from-address)Define the email FROM address

The FROM address that overrides the built-in `sharing-noreply` and `lostpassword-noreply` FROM addresses.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-39)Code Sample

```php
'mail_from_address' => 'owncloud',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-smtp-class-debugging)Enable or disable SMTP class debugging

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-40)Code Sample

```php
'mail_smtpdebug' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-mode-for-sending-an-email)Define the mode for sending an email

Modes to use for sending mail: `sendmail`, `smtp`, `qmail` or `php`.

If you are using local or remote SMTP, set this to `smtp`.

If you are using PHP mail you must have an installed and working email system on the server. The program used to send email is defined in the `php.ini` file.

For the `sendmail` option you need an installed and working email system on the server, with `/usr/sbin/sendmail` installed on your Unix system.

For `qmail` the binary is /var/qmail/bin/sendmail, and it must be installed on your Unix system.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-41)Code Sample

```php
'mail_smtpmode' => 'sendmail',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-ip-address-of-your-mail-server-host)Define the IP address of your mail server host

Depends on `mail_smtpmode`. May contain multiple hosts separated by a semi-colon.

If you need to specify the port number, append it to the IP address separated by a colon, like this: `127.0.0.1:24`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-42)Code Sample

```php
'mail_smtphost' => '127.0.0.1',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-port-for-sending-an-email)Define the port for sending an email

Depends on `mail_smtpmode`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-43)Code Sample

```php
'mail_smtpport' => 25,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-server-timeout)Define the SMTP server timeout

Depends on `mail_smtpmode`. Sets the SMTP server timeout in seconds.

You may need to increase this if you are running an anti-malware or spam scanner.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-44)Code Sample

```php
'mail_smtptimeout' => 10,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-security-style)Define the SMTP security style

Depends on `mail_smtpmode`. Specify when you are using `ssl` or `tls`.

Leave empty for no encryption.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-45)Code Sample

```php
'mail_smtpsecure' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-authentication)Define the SMTP authentication

Depends on `mail_smtpmode`. Change this to `true` if your mail server requires authentication.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-46)Code Sample

```php
'mail_smtpauth' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-authentication-type)Define the SMTP authentication type

Depends on `mail_smtpmode`. If SMTP authentication is required, choose the authentication type as `LOGIN` (default) or `PLAIN`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-47)Code Sample

```php
'mail_smtpauthtype' => 'LOGIN',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-authentication-username)Define the SMTP authentication username

Depends on `mail_smtpauth`. Specify the username for authenticating to the SMTP server.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-48)Code Sample

```php
'mail_smtpname' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-smtp-authentication-password)Define the SMTP authentication password

Depends on `mail_smtpauth`. Specify the password for authenticating to the SMTP server.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-49)Code Sample

```php
'mail_smtppassword' => '',
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#proxy-configurations)Proxy Configurations

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-automatic-proxy-detection)Override automatic proxy detection

The automatic hostname detection of ownCloud can fail in certain reverse proxy and CLI/cron situations. This option allows you to manually override the automatic detection; for example `www.example.com`, or specify the port `www.example.com:8080`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-50)Code Sample

```php
'overwritehost' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-protocol-httphttps-usage)Override protocol (http/https) usage

When generating URLs, ownCloud attempts to detect whether the server is accessed via `https` or `http`. However, if ownCloud is behind a proxy and the proxy handles the `https` calls, ownCloud would not know that `ssl` is in use, which would result in incorrect URLs being generated.

Valid values are `http` and `https`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-51)Code Sample

```php
'overwriteprotocol' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-ownclouds-webroot)Override ownClouds webroot

ownCloud attempts to detect the webroot for generating URLs automatically.

For example, if `www.example.com/owncloud` is the URL pointing to the ownCloud instance, the webroot is `/owncloud`. When proxies are in use, it may be difficult for ownCloud to detect this parameter, resulting in invalid URLs.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-52)Code Sample

```php
'overwritewebroot' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-condition-for-the-remote-ip-address-with-a-regular-expression)Override condition for the remote IP address with a regular expression

This option allows you to define a manual override condition as a regular expression for the remote IP address. The keys `overwritewebroot`, `overwriteprotocol`, and `overwritehost` are subject to this condition.

For example, defining a range of IP addresses starting with `10.0.0.` and ending with 1 to 3: \* `^10\.0\.0\.[1-3]$`

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-53)Code Sample

```php
'overwritecondaddr' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#override-cli-url)Override cli URL

Use this configuration parameter to specify the base URL for any URLs which are generated within ownCloud using any kind of command line tools (cron or occ).

The value should contain the full base URL: `[https://www.example.com/owncloud](https://www.example.com/owncloud)` As an example, alerts shown in the browser to upgrade an app are triggered by a cron background process and therefore uses the url of this key, even if the user has logged on via a different domain defined in key `trusted_domains`. When the user clicks an alert like this, they will be redirected to that URL and must logon again.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-54)Code Sample

```php
'overwrite.cli.url' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-web-base-url)Define the Web base URL

This key is necessary for the navigation item to the new ownCloud Web UI and for redirecting public and private links.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-55)Code Sample

```php
'web.baseUrl' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-rewrite-private-and-public-links)Define rewrite private and public links

Rewrite private and public links to the new ownCloud Web UI (if available).

If web.rewriteLinks is set to 'true', public and private links will be redirected to this url. The Web UI will handle these links accordingly.

As an example, in case 'web.baseUrl' is set to 'http://web.example.com', the shared link 'http://ocx.example.com/index.php/s/THoQjwYYMJvXMdW' will be redirected by ownCloud to 'http://web.example.com/index.html#/s/THoQjwYYMJvXMdW'.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-56)Code Sample

```php
'web.rewriteLinks' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-clean-urls-without-index-php)Define clean URLs without `/index.php`

This parameter will be written as `RewriteBase` on update and installation of ownCloud to your `.htaccess` file. While this value is often simply the URL path of the ownCloud installation it cannot be set automatically properly in every scenario and needs thus some manual configuration.

In a standard Apache setup this usually equals the folder that ownCloud is accessible at. So if ownCloud is accessible via `[https://mycloud.org/owncloud](https://mycloud.org/owncloud)` the correct value would most likely be `/owncloud`. If ownCloud is running under `[https://mycloud.org/](https://mycloud.org/)` then it would be `/`.

Note that the above rule is not valid in every case, as there are some rare setup cases where this may not apply. However, to avoid any update problems this configuration value is explicitly opt-in.

After setting this value run `sudo -u www-data occ maintenance:update:htaccess`. Now, when the following conditions are met ownCloud URLs won’t contain `index.php`:

-   `mod_rewrite` is installed
    
-   `mod_env` is installed
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-57)Code Sample

```php
'htaccess.RewriteBase' => '/',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-url-of-your-proxy-server)Define the URL of your proxy server

Example: `proxy.example.com:8081`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-58)Code Sample

```php
'proxy' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-a-list-of-hostnames-that-wont-be-proxied)Define a list of hostnames that won’t be proxied.

This option only applies if the `proxy` option is used Example: `['specific.hostname.com', '.sub.domain.com']`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-59)Code Sample

```php
'proxy_ignore' => [],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-proxy-authentication)Define proxy authentication

The optional authentication for the proxy to use to connect to the internet.

The format is: `username:password`.

The username and the password need to be urlencoded to avoid breaking the delimiter syntax "username:password@hostname:port"

Example: `usern@me` needs to be encoded as `usern%40ame`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-60)Code Sample

```php
'proxyuserpwd' => '',
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#deleted-items-trash-bin)Deleted Items (trash bin)

These parameters control the Deleted files app.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-trashbin-retention-obligation)Define the trashbin retention obligation

If the trash bin app is enabled (default), this setting defines the policy for when files and folders in the trash bin will be permanently deleted.

The app allows for two settings, a minimum time for trash bin retention, and a maximum time for trash bin retention. Minimum time is the number of days a file will be kept, after which it may be deleted. Maximum time is the number of days at which it is guaranteed to be deleted. Both minimum and maximum times can be set together to explicitly define file and folder deletion. For migration purposes, this setting is installed initially set to `auto`, which is equivalent to the default setting in ownCloud 8.1 and before.

Available values:

-   `auto` default setting. Keeps files and folders in the deleted files for up to 30 days, automatically deleting them (at any time) if space is needed. Note: files may not be removed if space is not required.
    
-   `D, auto` keeps files and folders in the trash bin for D+ days, delete anytime if space needed (Note: files may not be deleted if space is not needed)
    
-   `auto, D` delete all files in the trash bin that are older than D days automatically, delete other files anytime if space needed
    
-   `D1, D2` keep files and folders in the trash bin for at least D1 days and delete when exceeds D2 days
    
-   `disabled` trash bin auto clean disabled, files and folders will be kept forever
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-61)Code Sample

```php
'trashbin_retention_obligation' => 'auto',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-trashbin-purge-limit)Define the trashbin purge limit

This setting defines the percentage of free space occupied by deleted files that triggers auto purging of deleted files for this user

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-62)Code Sample

```php
'trashbin_purge_limit' => 50,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-trashbin-directory-skip-list)Define trashbin directory skip list

Define a list of directories that will skip the trashbin and therefore be deleted immediately.

Only defined directories and only in the root of a mount will skip the trashbin. Consider not to use reserved directory names when using snapshot capable storage systems. The setting expects folder names with or without trailing slash. All the content of such directories including their subdirectories will also skip the trashbin.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-63)Code Sample

```php
'trashbin_skip_directories' => [
'temp',
],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-trashbin-file-extension-skip-list)Define trashbin file extension skip list

Define a list of file extensions to determine files that will skip the trashbin and therefore be deleted immediately.

Extension names are valid for all mount points, take care when selecting the names.

Values must not have a leading ".", otherwise corresponding files won’t be detected. Values are case-insensitive

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-64)Code Sample

```php
'trashbin_skip_extensions' => [
'iso',
'mkv',
],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-trashbin-threshold-size)Define trashbin threshold size

Define a threshold for files to skip the trashbin and delete immediately Once the size of a resource is greater than or equal the given value, the trashbin will be skipped.

File sizes are valid for all mount points, take care when defining the threshold.

All positive numbers and zero is allowed. Append one of the following options directly and without space: B, K, KB, MB, M, GB, G, TB, T, PB, P

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-65)Code Sample

```php
'trashbin_skip_size_threshold' => "1GB",
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#file-versions)File versions

These parameters control the Versions app.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-files-versions-retention-obligation)Define the files versions retention obligation

If the versions app is enabled (default), this setting defines the policy for when versions will be permanently deleted.

The app allows for two settings, a minimum time for version retention, and a maximum time for version retention. Minimum time is the number of days a version will be kept, after which it may be deleted. Maximum time is the number of days at which it is guaranteed to be deleted. Both minimum and maximum times can be set together to explicitly define version deletion. For migration purposes, this setting is installed initially set to "auto", which is equivalent to the default setting in ownCloud 8.1 and before.

Available values:

-   `auto` default setting. Automatically expire versions according to expire rules. Please refer to [https://doc.owncloud.com/server/latest/admin\_manual/configuration/files/file\_versioning.html](https://doc.owncloud.com/server/latest/admin_manual/configuration/files/file_versioning.html) for more information.
    
-   `D, auto` keep versions at least for D days, apply expire rules to all versions that are older than D days
    
-   `auto, D` delete all versions that are older than D days automatically, delete other versions according to expire rules
    
-   `D1, D2` keep versions for at least D1 days and delete when exceeds D2 days
    
-   `disabled` versions auto clean disabled, versions will be kept forever
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-66)Code Sample

```php
'versions_retention_obligation' => 'auto',
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#owncloud-verifications)ownCloud Verifications

ownCloud performs several verification checks. There are two options, `true` and `false`.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-updatechecker)Enable or disable updatechecker

Check if ownCloud is up-to-date and shows a notification if a new version is available.

This option is only applicable to ownCloud core. It is not applicable to app updates.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-67)Code Sample

```php
'updatechecker' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-updatechecker-url)Define the updatechecker URL

The URL that ownCloud should use to look for updates

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-68)Code Sample

```php
'updater.server.url' => 'https://updates.owncloud.com/server/',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#check-for-an-internet-connection)Check for an internet connection

Is ownCloud connected to the Internet or running in a closed network?

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-69)Code Sample

```php
'has_internet_connection' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#check-for-a-well-known-setup)Check for a `.well-known` setup

Allows ownCloud to verify a working .well-known URL redirect.

This is done by attempting to make a request from JS to `[https://your-domain.com/.well-known/caldav/](https://your-domain.com/.well-known/caldav/)`

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-70)Code Sample

```php
'check_for_working_wellknown_setup' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-if-config-php-is-read-only)Define if config.php is read only

In certain environments it is desired to have a read-only configuration file.

When this switch is set to `true` ownCloud will not verify whether the configuration is writable. However, it will not be possible to configure all options via the Web interface. Furthermore, when updating ownCloud it is required to make the configuration file writable again for the update process.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-71)Code Sample

```php
'config_is_read_only' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-owncloud-operation-modes)Define ownCloud operation modes

This defines the mode of operations. The default value is `single-instance` which means, that ownCloud is running on a single node, which might be the most common operations mode. The only other possible value for now is `clustered-instance` which means, that ownCloud is running on at least 2 nodes. The mode of operations has various impacts on the behavior of ownCloud.

The primary impact is, that clustered instances won’t download apps from the marketplace and install in one server. Instead the admin has to ensure that this happens manually on all servers. The same applies to config.php configuration settings done via `occ`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-72)Code Sample

```php
'operation.mode' => 'single-instance',
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#logging)Logging

These parameters configure the logging options. For additional information or advanced configuration, please see the logging section in the documentation.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-type)Define the log type

By default the ownCloud logs are sent to the `owncloud.log` file in the default ownCloud data directory.

If syslogging is desired, set this parameter to `syslog`. Setting this parameter to `errorlog` will use the PHP error\_log function for logging.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-73)Code Sample

```php
'log_type' => 'owncloud',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-path)Define the log path

Log file path for the ownCloud logging type.

Defaults to `[datadirectory]/owncloud.log`

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-74)Code Sample

```php
'logfile' => '/var/log/owncloud.log',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-level)Define the log level

Loglevel to start logging at. Valid values are: 0 = Debug, 1 = Info, 2 = Warning, 3 = Error, and 4 = Fatal. The default value is Warning.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-75)Code Sample

```php
'loglevel' => 2,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-syslog-tag)Define the syslog tag

If you maintain different instances and aggregate the logs, you may want to distinguish between them. `syslog_tag` can be set per instance with a unique id. Only available if `log_type` is set to `syslog`.

The default value is `ownCloud`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-76)Code Sample

```php
'syslog_tag' => 'ownCloud',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-syslog-format)Define the syslog format

The syslog format can be changed to remove or add information.

In addition to the %replacements% below %level% can be used, but it is used as a dedicated parameter to the syslog logging facility anyway.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-77)Code Sample

```php
'log.syslog.format' => '[%reqId%][%remoteAddr%][%user%][%app%][%method%][%url%] %message%',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-log-conditions)Define log conditions

Log condition for log level increase based on conditions. Once one of these conditions is met, the required log level is set to debug. This allows to debug specific requests, users or apps

Supported conditions: - `shared_secret`: If a request parameter with the name `log_secret` is set to this value the condition is met - `users`: If the current request is done by one of the specified users, this condition is met - `apps`: If the log message is invoked by one of the specified apps, this condition is met - `logfile`: The log message invoked by the specified apps get redirected to this logfile, this condition is met Note: Not applicable when using syslog

Defaults to an empty array

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-78)Code Sample

```php
'log.conditions' => [
[
'shared_secret' => '57b58edb6637fe3059b3595cf9c41b9',
'users' => ['user1'],
'apps' => ['files_texteditor'],
'logfile' => '/tmp/test.log'
],
[
'shared_secret' => '57b58edb6637fe3059b3595cf9c41b9',
'users' => ['user1'],
'apps' => ['files_mediaviewer'],
'logfile' => '/tmp/mediaviewer.log'
],
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-date-format)Define the log date format

This uses PHP.date formatting; see [http://php.net/manual/en/function.date.php](http://php.net/manual/en/function.date.php)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-79)Code Sample

```php
'logdateformat' => 'F d, Y H:i:s',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-log-timezone)Define the log timezone

The default timezone for logfiles is UTC. You may change this; see [http://php.net/manual/en/timezones.php](http://php.net/manual/en/timezones.php)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-80)Code Sample

```php
'logtimezone' => 'Europe/Berlin',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-logging-if-cron-ran-successfully)Define logging if Cron ran successfully

Log successful cron runs.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-81)Code Sample

```php
'cron_log' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-log-rotation-file-size)Define the maximum log rotation file size

Enables log rotation and limits the total size of the logfiles.

The default is 0 or false which disables log rotation. Specify a size in bytes, for example 104857600 (100 megabytes = 100 \* 1024 \* 1024 bytes). A new logfile is created with a new name when the old logfile reaches the defined limit. If a rotated log file is already present, it will be overwritten. If enabled, only the active log file and one rotated file are stored.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-82)Code Sample

```php
'log_rotate_size' => false,
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#alternate-code-locations)Alternate Code Locations

Some of the ownCloud code may be stored in alternate locations.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-alternative-app-directories)Define alternative app directories

If you want to store apps in a custom directory instead of ownCloud’s default `/apps`, you need to modify the `apps_paths` key. There, you need to add a new associative array that contains three elements. These are:

-   `path` The absolute file system path to the custom app folder.
    
-   `url` The request path to that folder relative to the ownCloud web root, prefixed with /.
    
-   `writable` Whether users can install apps in that folder. After the configuration is added, new apps will only install in a directory where writable is set to true.
    

The configuration example shows how to add a second directory, called `/apps-external`. Here, new apps and updates are only written to the `/apps-external` directory. This eases upgrade procedures of owncloud where shipped apps are delivered to apps/ by default. `OC::$SERVERROOT` points to the web root of your instance. Please see the Apps Management description on how to move custom apps properly.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-83)Code Sample

```php
'apps_paths' => [
0 =>
[
'path' => OC::$SERVERROOT.'/apps',
'url' => '/apps',
'writable' => false,
],
1 =>
[
'path' => OC::$SERVERROOT.'/apps-external',
'url' => '/apps-external',
'writable' => true,
],
  ],
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#previews)Previews

ownCloud supports previews of image files, the covers of MP3 files, and text files. These options control enabling and disabling previews, and thumbnail size.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-preview-generation)Enable preview generation

By default, ownCloud can generate previews for the following filetypes:

-   Image files
    
-   Covers of MP3 files
    
-   Text documents
    

Valid values are `true`, to enable previews, or `false`, to disable previews

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-84)Code Sample

```php
'enable_previews' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-preview-path)Define the preview path

Location of the thumbnails folder, defaults to `data/$user/thumbnails` where `$user` is the current user. When specified, the format will change to `$previews_path/$user` where `$previews_path` is the configured previews base directory and `$user` will be substituted with the user id automatically.

For example if `previews_path` is `/var/cache/owncloud/thumbnails` then for a logged-in user `user1` the thumbnail path will be `/var/cache/owncloud/thumbnails/user1`.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-85)Code Sample

```php
'previews_path' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-x-axis-width-for-previews)Define the maximum x-axis width for previews

The maximum width, in pixels, of a preview.

A value of `null` means there is no limit.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-86)Code Sample

```php
'preview_max_x' => 2048,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-y-axis-width-for-previews)Define the maximum y-axis width for previews

The maximum height, in pixels, of a preview. A value of `null` means there is no limit.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-87)Code Sample

```php
'preview_max_y' => 2048,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-preview-scale-factor)Define the maximum preview scale factor

If a lot of small pictures are stored on the ownCloud instance and the preview system generates blurry previews, you might want to consider setting a maximum scale factor. By default, pictures are upscaled to 10 times the original size. A value of `1` or `null` disables scaling.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-88)Code Sample

```php
'preview_max_scale_factor' => 10,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-preview-filesize-limit)Define the maximum preview filesize limit

Max file size for generating image previews with imagegd (default behaviour) If the image is bigger, it will try other preview generators, but will most likely show the default mimetype icon

Value represents the maximum filesize in megabytes Default is 50. Set to -1 for no limit.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-89)Code Sample

```php
'preview_max_filesize_image' => 50,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-custom-path-for-the-libreoffice-openoffice-binary)Define the custom path for the LibreOffice / OpenOffice binary

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-90)Code Sample

```php
'preview_libreoffice_path' => '/usr/bin/libreoffice',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-additional-arguments-for-libreoffice-openoffice)Define additional arguments for LibreOffice / OpenOffice

Use this setting if LibreOffice/OpenOffice requires additional arguments.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-91)Code Sample

```php
'preview_office_cl_parameters' =>
'--headless --nologo --nofirststartwizard --invisible --norestore ',
'--convert-to pdf --outdir ',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-preview-providers)Define preview providers

Show thumbnails for register providers that have been explicitly enabled.

The following providers are enabled by default if no other providers are selected:

-   OC\\Preview\\PNG
    
-   OC\\Preview\\JPEG
    
-   OC\\Preview\\WEBP
    
-   OC\\Preview\\GIF
    
-   OC\\Preview\\BMP
    
-   OC\\Preview\\XBitmap
    
-   OC\\Preview\\MarkDown
    
-   OC\\Preview\\MP3
    
-   OC\\Preview\\TXT
    

See the Previews Configuration documentation for more details.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-92)Code Sample

```php
'enabledPreviewProviders' => [
'OC\Preview\PDF',
'OC\Preview\SGI',
'OC\Preview\Heic',
'OC\Preview\PNG',
'OC\Preview\JPEG',
'OC\Preview\WEBP',
'OC\Preview\GIF',
'OC\Preview\BMP',
'OC\Preview\XBitmap',
'OC\Preview\MP3',
'OC\Preview\TXT',
'OC\Preview\MarkDown'
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-jpeg-preview-quality)Define the jpeg preview quality

This setting defines the JP(E)G image quality in \[%\] for displaying thumbnails and image previews for apps like 'files\_mediaviewer'. Note that this setting is for displaying only and has no impact on the stored thumbnail / preview quality or size.

The scale ranges from 1 to 100, where 1 is the lowest and 100 the highest. It defaults to -1 which is equivalent to approximately 75% of the original image quality.

Note that any value over 80 may result in an unnecessary increase of the displayed image and has larger responses sizes when requesting images, without much increase of the image quality.

For more information see: [https://www.php.net/manual/en/function.imagejpeg.php](https://www.php.net/manual/en/function.imagejpeg.php)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-93)Code Sample

```php
'previewJPEGImageDisplayQuality' => -1,
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#comments)Comments

Global settings for the Comments infrastructure

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-an-alternative-comments-manager)Define an alternative Comments Manager

Replaces the default Comments Manager Factory. This can be utilized if an own or 3rdParty CommentsManager should be used that – for instance – uses the filesystem instead of the database to keep the comments.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-94)Code Sample

```php
'comments.managerFactory' => '\OC\Comments\ManagerFactory',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-an-alternative-system-tags-manager)Define an alternative System Tags Manager

Replaces the default System Tags Manager Factory. This can be utilized if an own or 3rdParty SystemTagsManager should be used that – for instance – uses the filesystem instead of the database to keep the tags.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-95)Code Sample

```php
'systemtags.managerFactory' => '\OC\SystemTag\ManagerFactory',
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#maintenance)Maintenance

These options are for halting user activity when you are performing server maintenance.

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-maintenance-mode-to-disable-owncloud)Enable maintenance mode to disable ownCloud

If you want to prevent users from logging in to ownCloud before you start doing some maintenance work, you need to set the value of the maintenance parameter to true. Please keep in mind that users who are already logged-in are kicked out of ownCloud instantly.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-96)Code Sample

```php
'maintenance' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-single-user-mode)Enable or disable `single user mode`

When set to `true`, the ownCloud instance will be unavailable for all users who are not in the `admin` group.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-97)Code Sample

```php
'singleuser' => false,
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#ssl)SSL

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#extra-ssl-options-to-be-used-for-configuration)Extra SSL options to be used for configuration

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-98)Code Sample

```php
'openssl' => [
'config' => '/absolute/location/of/openssl.cnf',
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-the-configuration-of-system-wide-trusted-certificates)Allow the configuration of system-wide trusted certificates

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-99)Code Sample

```php
'enable_certificate_management' => false,
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#memory-caching-backend-configuration)Memory caching backend configuration

Available cache backends:

-   `\OC\Memcache\APCu` APC user backend
    
-   `\OC\Memcache\ArrayCache` In-memory array-based backend (not recommended)
    
-   `\OC\Memcache\Memcached` Memcached backend
    
-   `\OC\Memcache\Redis` Redis backend
    

Advice on choosing between the various backends:

-   APCu should be easiest to install. Almost all distributions have packages. Use this for single user environment for all caches.
    
-   Use Redis or Memcached for distributed environments. For the local cache (you can configure two) take APCu.
    

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#memory-caching-backend-for-locally-stored-data)Memory caching backend for locally stored data

-   Used for host-specific data, e.g. file paths
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-100)Code Sample

```php
'memcache.local' => '\OC\Memcache\APCu',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#memory-caching-backend-for-distributed-data)Memory caching backend for distributed data

-   Used for installation-specific data, e.g. database caching
    
-   If unset, defaults to the value of memcache.local
    

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-101)Code Sample

```php
'memcache.distributed' => '\OC\Memcache\Memcached',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-redis-connection-details)Define Redis connection details

Connection details for Redis to use for memory caching in a single server configuration.

For enhanced security it is recommended to configure Redis to require a password. See [http://redis.io/topics/security](http://redis.io/topics/security) for more information.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-102)Code Sample

```php
'redis' => [
'host' => 'localhost', // can also be a unix domain socket: '/tmp/redis.sock'
'port' => 6379,
'timeout' => 0.0,
'password' => '', // Optional, if not defined no password will be used.
'dbindex' => 0,   // Optional, if undefined SELECT will not run and will use Redis Server's default DB Index. Out of the box, every Redis instance supports 16 databases so `<dbIndex>` has to be set between 0 and 15.
 // Optional config option
 // In order to use connection_parameters php-redis extension >= 5.3.0 is required
 // In order to use SSL/TLS redis server >= 6.0 is required
 // In a single-server configuration, prefix the host with tls:// like tls://localhost
 // In a single-server configuration the SSL/TLS data **must** be in the stream section
'connection_parameters' => [
'stream' => [
'local_cert' => '/file/path/to/redis.crt',
'local_pk' => '/file/path/to/redis.key',
'cafile' => '/file/path/to/ca.crt',
'verify_peer_name' => true
],
],

  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-redis-cluster-connection-details)Define Redis Cluster connection details

Only for use with Redis Clustering, for Sentinel-based setups use the single server configuration above, and perform HA on the hostname.

Redis Cluster support requires the php module phpredis in version 3.0.0 or higher.

Available failover modes: - \\RedisCluster::FAILOVER\_NONE - only send commands to primary nodes (default) - \\RedisCluster::FAILOVER\_ERROR - failover to replicas for read commands if primary is unavailable - \\RedisCluster::FAILOVER\_DISTRIBUTE - randomly distribute read commands across primary and replica nodes

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-103)Code Sample

```php
'redis.cluster' => [
'seeds' => [ // provide some/all of the cluster servers to bootstrap discovery, port required
  'localhost:7000',
  'localhost:7001'
],
'timeout' => 0.0,
'read_timeout' => 0.0,
'failover_mode' => \RedisCluster::FAILOVER_DISTRIBUTE,
'password' => '', // Optional, if not defined no password will be used.
 // Optional config option
 // In order to use connection_parameters php-redis extension >= 5.3.0 is required
 // In order to use SSL/TLS redis server >= 6.0 is required
 // In a cluster configuration, prefix the seeds with tls:// like tls://localhost:7000
 // In a cluster configuration the SSL/TLS data **must not** be in the stream section
'connection_parameters' => [
'local_cert' => '/file/path/to/redis.crt',
'local_pk' => '/file/path/to/redis.key',
'cafile' => '/file/path/to/ca.crt',
'verify_peer_name' => true
],
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-server-details-for-memcached-servers-to-use-for-memory-caching)Define server details for memcached servers to use for memory caching

Server details for one or more memcached servers to use for memory caching

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-104)Code Sample

```php
'memcached_servers' => [
// hostname, port and optional weight. Also see:
// http://www.php.net/manual/en/memcached.addservers.php
// http://www.php.net/manual/en/memcached.addserver.php
['localhost', 11211],
//[other.host.local', 11211],
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-connection-options-for-memcached)Define connection options for memcached

For more details please see [http://apprize.info/php/scaling/15.html](http://apprize.info/php/scaling/15.html)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-105)Code Sample

```php
'memcached_options' => [
// Set timeouts to 50ms
\Memcached::OPT_CONNECT_TIMEOUT => 50,
\Memcached::OPT_RETRY_TIMEOUT =>   50,
\Memcached::OPT_SEND_TIMEOUT =>    50,
\Memcached::OPT_RECV_TIMEOUT =>    50,
\Memcached::OPT_POLL_TIMEOUT =>    50,

// Enable compression
\Memcached::OPT_COMPRESSION =>          true,

// Turn on consistent hashing
\Memcached::OPT_LIBKETAMA_COMPATIBLE => true,

// Enable Binary Protocol
\Memcached::OPT_BINARY_PROTOCOL =>      true,

// Binary serializer will be enabled if the igbinary PECL module is available
//\Memcached::OPT_SERIALIZER => \Memcached::SERIALIZER_IGBINARY,
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-location-of-the-cache-folder)Define the location of the cache folder

The location of the cache folder defaults to `data/$user/cache` where `$user` is the current user. When specified, the format will change to `$cache_path/$user` where `$cache_path` is the configured cache directory and `$user` is the user.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-106)Code Sample

```php
'cache_path' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-ttl-for-garbage-collection)Define the TTL for garbage collection

TTL of chunks located in the cache folder before they’re removed by garbage collection (in seconds). Increase this value if users have issues uploading very large files via the ownCloud Client as upload isn’t completed within one day.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-107)Code Sample

```php
'cache_chunk_gc_ttl' => 86400, // 60*60*24 = 1 day
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-dav-chunk-base-directory)Define the DAV chunk base directory

Location of the chunk folder, defaults to `data/$user/uploads` where `$user` is the current user. When specified, the format will change to `$dav.chunk_base_dir/$user` where `$dav.chunk_base_dir` is the configured cache directory and `$user` is the user.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-108)Code Sample

```php
'dav.chunk_base_dir' => '',
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#sharing)Sharing

Global settings for Sharing

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-an-alternative-share-provider)Define an alternative Share Provider

Replaces the default Share Provider Factory. This can be utilized if own or 3rdParty Share Providers are used that – for instance – use the filesystem instead of the database to keep the share information.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-109)Code Sample

```php
'sharing.managerFactory' => '\OC\Share20\ProviderFactory',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#allow-schema-fallback-for-federated-sharing-servers)Allow schema fallback for federated sharing servers

When talking with federated sharing server, allow falling back to HTTP instead of hard forcing HTTPS

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-110)Code Sample

```php
'sharing.federation.allowHttpFallback' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-a-quick-action-for-the-public-link-creation)Show a quick action for the public link creation

Set this to true to display a quick action for creating public links in the filelist. A public link created this way will be read-only per default.

Note: if enforced password protection for read-only links is enabled, the quick action will not be displayed!

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-111)Code Sample

```php
'sharing.showPublicLinkQuickAction' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#save-and-display-version-of-uploaded-and-edited-files)Save and display version of uploaded and edited files.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-112)Code Sample

```php
'file_storage.save_version_author' => false,
```

## [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#all-other-configuration-options)All other configuration options

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-additional-database-driver-options)Define additional database driver options

Additional driver options for the database connection, e.g. to enable SSL encryption in MySQL or specify a custom wait timeout on a cheap hoster.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-113)Code Sample

```php
'dbdriveroptions' => [
PDO::MYSQL_ATTR_SSL_CA => '/file/path/to/ca_cert.pem',
PDO::MYSQL_ATTR_INIT_COMMAND => 'SET wait_timeout = 28800'
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-sqlite3-journal-mode)Define sqlite3 journal mode

sqlite3 journal mode can be specified using this configuration parameter - can be 'WAL' or 'DELETE' see for more details [https://www.sqlite.org/wal.html](https://www.sqlite.org/wal.html)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-114)Code Sample

```php
'sqlite.journal_mode' => 'DELETE',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-mysql-34-byte-character-handling)Define MySQL 3/4 byte character handling

During setup, if requirements are met (see below), this setting is set to true and MySQL can handle 4 byte characters instead of 3 byte characters.

If you want to convert an existing 3-byte setup into a 4-byte setup please set the parameters in MySQL as mentioned below and run the migration command: `sudo -u www-data occ db:convert-mysql-charset` The config setting will be set automatically after a successful run.

Consult the documentation for more details.

MySQL requires a special setup for longer indexes (> 767 bytes) which are needed:

```console
[mysqld]
innodb_large_prefix=ON
innodb_file_format=Barracuda
innodb_file_per_table=ON
```

Tables will be created with \* character set: utf8mb4 \* collation: utf8mb4\_bin \* row\_format: compressed

See: [https://dev.mysql.com/doc/refman/5.7/en/charset-unicode-utf8mb4.html](https://dev.mysql.com/doc/refman/5.7/en/charset-unicode-utf8mb4.html) [https://dev.mysql.com/doc/refman/5.7/en/innodb-parameters.html#sysvar\_innodb\_large\_prefix](https://dev.mysql.com/doc/refman/5.7/en/innodb-parameters.html#sysvar_innodb_large_prefix) [https://mariadb.com/kb/en/mariadb/xtradbinnodb-server-system-variables/#innodb\_large\_prefix](https://mariadb.com/kb/en/mariadb/xtradbinnodb-server-system-variables/#innodb_large_prefix) [http://www.tocker.ca/benchmarking-innodb-page-compression-performance.html](http://www.tocker.ca/benchmarking-innodb-page-compression-performance.html) [https://titanwolf.org/Network/Articles/Article?AID=58c487d4-7e0f-4fbe-9262-4285553ef443](https://titanwolf.org/Network/Articles/Article?AID=58c487d4-7e0f-4fbe-9262-4285553ef443) (Using innodb\_large\_prefix to avoid ERROR 1071)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-115)Code Sample

```php
'mysql.utf8mb4' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#force-a-specific-database-platform-class)Force a specific database platform class

False means that autodetection will take place.

E.g. to fix MariaDB 1.2.7+ taken for MySQL 'db.platform' ⇒ '\\Doctrine\\DBAL\\Platforms\\MariaDb1027Platform',

See: [https://docs.microsoft.com/en-us/azure/mariadb/concepts-limits#current-known-issues](https://docs.microsoft.com/en-us/azure/mariadb/concepts-limits#current-known-issues)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-116)Code Sample

```php
'db.platform' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-supported-database-types)Define supported database types

Database types that are supported for installation.

Available: - sqlite (SQLite3 - Not in Enterprise Edition) - mysql (MySQL) - pgsql (PostgreSQL) - oci (Oracle - Enterprise Edition Only)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-117)Code Sample

```php
'supportedDatabases' => [
'sqlite',
'mysql',
'pgsql',
'oci',
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-location-for-temporary-files)Define the location for temporary files

Override where ownCloud stores temporary files. Useful in situations where the system temporary directory is on a limited space ramdisk or is otherwise restricted, or if external storages which do not support streaming are in use.

The Web server user must have write access to this directory.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-118)Code Sample

```php
'tempdirectory' => '/tmp/owncloudtemp',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-hashing-cost)Define the hashing cost

The hashing cost used by hashes generated by ownCloud.

Using a higher value requires more time and CPU power to calculate the hashes. As this number grows, the amount of work (typically CPU time or memory) necessary to compute the hash increases exponentially.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-119)Code Sample

```php
'hashingCost' => 10,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-blacklisted-files)Define blacklisted files

Blacklist a specific file or files and disallow the upload of files with this name. `.htaccess` is blocked by default.

<table><tbody><tr><td class="icon"><i class="fa icon-warning" title="Warning"></i></td><td class="content">USE THIS ONLY IF YOU KNOW WHAT YOU ARE DOING.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-120)Code Sample

```php
'blacklisted_files' => [
'.htaccess'
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-blacklisted-files-regular-expressions)Define blacklisted files regular expression(s)

Blacklist files that match any of the given regular expressions and disallow the upload of those files. The matching is case-insensitive.

<table><tbody><tr><td class="icon"><i class="fa icon-warning" title="Warning"></i></td><td class="content">USE THIS ONLY IF YOU KNOW WHAT YOU ARE DOING.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-121)Code Sample

```php
'blacklisted_files_regex' => [
'.*\.ext',
'^somefilename.*'
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-excluded-directories)Define excluded directories

Exclude specific directory names and disallow scanning, creating and renaming using these names. The matching is case-insensitive.

Excluded directory names are queried at any path part like at the beginning, in the middle or at the end and will not be further processed if found. Please see the documentation for details and examples. Use when the storage backend supports, e.g. snapshot directories to be excluded.

<table><tbody><tr><td class="icon"><i class="fa icon-warning" title="Warning"></i></td><td class="content">USE THIS ONLY IF YOU KNOW WHAT YOU ARE DOING.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-122)Code Sample

```php
'excluded_directories' => [
'.snapshot',
'~snapshot',
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-excluded-directories-regular-expressions)Define excluded directories regular expression(s)

Exclude directory names that match any of the given regular expressions and disallow scanning, creating and renaming using these names. The matching is case-insensitive.

Excluded directory names are queried at any path part like at the beginning, in the middle or at the end and will not be further processed if found. Please see the documentation for details and examples. Use when the storage backend supports, e.g. snapshot directories to be excluded.

<table><tbody><tr><td class="icon"><i class="fa icon-warning" title="Warning"></i></td><td class="content">USE THIS ONLY IF YOU KNOW WHAT YOU ARE DOING.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-123)Code Sample

```php
'excluded_directories_regex' => [
'^backup.*',
'.*backup$',
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-files-that-are-excluded-from-integrity-checking)Define files that are excluded from integrity checking

Exclude files from the integrity checker command

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-124)Code Sample

```php
'integrity.excluded.files' => [
'.DS_Store',
'Thumbs.db',
'.directory',
'.webapp',
'.htaccess',
'.user.ini',
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-apps-or-themes-that-are-excluded-from-integrity-checking)Define apps or themes that are excluded from integrity checking

The list of apps that are allowed and must not have a signature.json file present.

Besides ownCloud apps, this is particularly useful when creating ownCloud themes, because themes are treated as apps. The app is identified with it´s app-id. The app-id can be identified by the foldername of the app in your apps directory. The following example allows app-1 and theme-2 to have no signature.json file.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-125)Code Sample

```php
'integrity.ignore.missing.app.signature' => [
'app-id of app-1',
'app-id of theme-2',
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-a-default-folder-for-shared-files-and-folders-other-than-root)Define a default folder for shared files and folders other than root

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-126)Code Sample

```php
'share_folder' => '/',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-default-cipher-for-encrypting-files)Define the default cipher for encrypting files

Currently AES-128-CFB and AES-256-CFB are supported.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-127)Code Sample

```php
'cipher' => 'AES-256-CFB',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-file-format-for-encrypting-files)Define the file format for encrypting files

Define if encrypted files will be written in the old format (`true`) or the new binary format (`false`) which has a significant reduced filesize. Defaults to `false`.

With binary, only new files are written in the binary format, existing encrypted files in the old format stay readable. This guarantees a smooth transition.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-128)Code Sample

```php
'encryption.use_legacy_encoding' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-minimum-supported-owncloud-desktop-client-version)Define the minimum supported ownCloud desktop client version

Define the minimum ownCloud desktop client version that is allowed to sync with this server instance. All connections made from earlier clients will be denied by the server.

As shipped, the value here is the oldest desktop client that is technically compatible with the server. The version number seen here does not imply official support or test coverage on behalf of ownCloud.

<table><tbody><tr><td class="icon"><i class="fa icon-note" title="Note"></i></td><td class="content">Lowering this value may lead to unexpected behaviour, and can include data loss.</td></tr></tbody></table>

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-129)Code Sample

```php
'minimum.supported.desktop.version' => '2.3.3',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-suggested-poll-interval-for-clients)Define the suggested poll interval for clients

Specifies how often clients should poll the server for changes.

The value is in milliseconds. The value is not enforced. Clients may use this value to decide how frequently to check the server for changes.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-130)Code Sample

```php
'pollinterval' => 30000,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-whether-to-include-external-storage-in-quota-calculation)Define whether to include external storage in quota calculation

EXPERIMENTAL: option whether to include external storage in quota calculation, defaults to false.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-131)Code Sample

```php
'quota_include_external_storage' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-how-often-filesystem-changes-are-detected)Define how often filesystem changes are detected

Specifies how often the local filesystem (the ownCloud data/ directory, and NFS mounts in data/) is checked for changes made outside ownCloud. This does not apply to external storages.

→ Never check the filesystem for outside changes, provides a performance increase when it’s certain that no changes are made directly to the filesystem

→ Check each file or folder at most once per request, recommended for general use if outside changes might happen.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-132)Code Sample

```php
'filesystem_check_changes' => 0,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-unsuccessful-mountpoint-rename-attempts)Define unsuccessful mountpoint rename attempts

This config value avoids infinite loops for seldom cases where a file renaming conflict between different share backends could occur.

The value defines how many unsuccessful mountpoint rename attempts are allowed. e.g. target mountpoint name could be claimed as unused by the filesystem but renaming to this target name will fail due to some other reasons like database constraints. Change this value only under supervision of ownCloud support.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-133)Code Sample

```php
'filesystem.max_mountpoint_move_attempts' => 10,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-where-part-files-are-located)Define where part files are located

By default ownCloud will store the part files created during upload in the same storage as the upload target. Setting this to false will store the part files in the root of the user’s folder which might be required to work with certain external storage setups that have limited rename capabilities.

Note that setting this to false causes issues with the following apps: Encryption, Document classification, Anti-Virus and Ransomware Protection.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-134)Code Sample

```php
'part_file_in_storage' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#prevent-cache-changes-due-to-changes-in-the-filesystem)Prevent cache changes due to changes in the filesystem

When `true`, prevent ownCloud from changing the cache due to changes in the filesystem for all storage.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-135)Code Sample

```php
'filesystem_cache_readonly' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-ownclouds-internal-secret)Define ownClouds internal secret

Secret used by ownCloud for various purposes, e.g. to encrypt data.

If you lose this string there will be data corruption.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-136)Code Sample

```php
'secret' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-list-of-trusted-proxy-servers)Define list of trusted proxy servers

If you configure these also consider setting `forwarded_for_headers` which otherwise defaults to `HTTP_X_FORWARDED_FOR` (the `X-Forwarded-For` header).

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-137)Code Sample

```php
'trusted_proxies' => [
'203.0.113.45',
'198.51.100.128'
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-forwarded_for_headers)Define `forwarded_for_headers`

Headers that should be trusted as client IP address in combination with `trusted_proxies`. If the HTTP header looks like 'X-Forwarded-For', then use 'HTTP\_X\_FORWARDED\_FOR' here.

If set incorrectly, a client can spoof their IP address as visible to ownCloud, bypassing access controls and making logs useless!

If not set, defaults to 'HTTP\_X\_FORWARDED\_FOR'.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-138)Code Sample

```php
'forwarded_for_headers' => [
'HTTP_X_FORWARDED',
'HTTP_FORWARDED_FOR'
  ],
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-maximum-filesize-for-animated-gifs)Define the maximum filesize for animated GIF´s

Max file size for animating gifs on public-sharing-site.

If the gif is bigger, it’ll show a static preview.

Value represents the maximum filesize in megabytes. Default is `10`. Set to `-1` for no limit.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-139)Code Sample

```php
'max_filesize_animated_gifs_public_sharing' => 10,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-transactional-file-locking)Enable transactional file locking

Transactional file locking is enabled by default.

Prevents concurrent processes from accessing the same files at the same time. Can help prevent side effects that would be caused by concurrent operations. Mainly relevant for very large installations with many users working with shared files.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-140)Code Sample

```php
'filelocking.enabled' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-ttl-for-file-locking)Define the TTL for file locking

Set the lock’s time-to-live in seconds.

Any lock older than this will be automatically cleaned up. If not set this defaults to either 1 hour or the php max\_execution\_time, whichever is higher.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-141)Code Sample

```php
'filelocking.ttl' => 3600,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-memory-caching-backend-for-file-locking)Define the memory caching backend for file locking

Because most memcache backends can clean values without warning, using redis is highly recommended to **avoid data loss**.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-142)Code Sample

```php
'memcache.locking' => '\\OC\\Memcache\\Redis',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#disable-the-web-based-updater)Disable the web based updater

The web based updater is enabled by default.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-143)Code Sample

```php
'upgrade.disable-web' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-whether-or-not-to-enable-automatic-update-of-market-apps)Define whether or not to enable automatic update of market apps

Set to `false` to disable.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-144)Code Sample

```php
'upgrade.automatic-app-update' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-debugging-mode-for-this-owncloud-instance)Enable debugging mode for this ownCloud instance

Only enable this for local development and not in production environments This will disable the minifier and outputs some additional debug information

WARNING: Be warned that, if you set this to `true`, exceptions display stack traces on the web interface, **including passwords**, — **in plain text!**. We strongly encourage you never to use it in production.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-145)Code Sample

```php
'debug' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-the-data-fingerprint-of-the-current-data-served)Define the data-fingerprint of the current data served

This is a property used by the clients to find out if a backup has been restored on the server. Once a backup is restored run sudo -u www-data occ maintenance:data-fingerprint To set this to a new value.

Updating/Deleting this value can make connected clients stall until the user has resolved conflicts.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-146)Code Sample

```php
'data-fingerprint' => '',
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#define-if-you-have-copied-the-sample-configuration)Define if you have copied the sample configuration

This entry is just here to show a warning in case somebody copied the sample configuration.

<table><tbody><tr><td class="icon"><i class="fa icon-warning" title="Warning"></i></td><td class="content">DO NOT ADD THIS SWITCH TO YOUR CONFIGURATION!</td></tr></tbody></table>

If you, brave person, have read until here be aware that you should not modify **ANY** settings in this file without reading the documentation.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-147)Code Sample

```php
'copied_sample_config' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-the-files_external-local-mount-option)Enable or disable the files\_external local mount option

Set this property to true if you want to enable the files\_external local mount option.

Default: `false`

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-148)Code Sample

```php
'files_external_allow_create_new_local' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-debug-logging-for-smb-access)Enable or disable debug logging for SMB access

Set this property to true if you want to enable debug logging for SMB access.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-149)Code Sample

```php
'smb.logging.enable' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-or-disable-async-dav-extensions)Enable or disable async DAV extensions

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-150)Code Sample

```php
'dav.enable.async' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#enable-propfind-depth-infinity-requests)Enable propfind depth infinity requests

Tell the clients whether `depth=infinity` is allowed for propfind requests.

Streamed infinite depth propfind requests can reduce memory usage with large responses. For details see: [https://datatracker.ietf.org/doc/html/rfc4918#section-10.2](https://datatracker.ietf.org/doc/html/rfc4918#section-10.2)

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-151)Code Sample

```php
'dav.propfind.depth_infinity' => false,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#show-the-grace-period-popup)Show the grace period popup

Decide whether show or not the grace period popup. There is no change in the behaviour of the grace period.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-152)Code Sample

```php
'grace_period.demo_key.show_popup' => true,
```

### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#link-to-get-a-demo-key-during-active-grace-period)Link to get a demo key during active grace period

The admin will be directed to that web page when they click on the "get a demo key" link in the grace period popup. It’s expected that the web page contains instructions on how to get a valid demo key to be used in the ownCloud server.

If this key isn’t present, ownCloud’s default will be used.

#### [](https://doc.owncloud.com/server/next/admin_manual/configuration/server/config_sample_php_parameters.html#code-sample-153)Code Sample

```php
'grace_period.demo_key.link' => 'https://owncloud.com/try-enterprise/',
```
