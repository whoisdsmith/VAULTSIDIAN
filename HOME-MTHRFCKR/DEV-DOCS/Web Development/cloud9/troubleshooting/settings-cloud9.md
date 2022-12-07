## Security & setup warnings

[](https://docs.nextcloud.com/server/24/go.php?to=admin-warnings)

It's important for the security and performance of your instance that everything is configured correctly. To help you with that we are doing some automatic checks. Please see the linked documentation for more information.

All checks passed.

There are some errors regarding your setup.

There are some warnings regarding your setup.

Checking for system and security issues.

- The "Strict-Transport-Security" HTTP header is not set to at least "15552000" seconds. For enhanced security, it is recommended to enable HSTS as described in the [security tips ↗](https://docs.nextcloud.com/server/24/go.php?to=admin-security).

- No memory cache has been configured. To enhance performance, please configure a memcache, if available. Further information can be found in the [documentation ↗](https://docs.nextcloud.com/server/24/go.php?to=admin-performance).

- The PHP OPcache module is not properly configured. See the [documentation ↗](https://docs.nextcloud.com/server/24/go.php?to=admin-php-opcache) for more information.
  - The OPcache buffer is nearly full. To assure that all scripts can be hold in cache, it is recommended to apply `opcache.memory_consumption` to your PHP configuration with a value higher than `128`.
  - The OPcache interned strings buffer is nearly full. To assure that repeating strings can be effectively cached, it is recommended to apply `opcache.interned_strings_buffer` to your PHP configuration with a value higher than `8`.

- MySQL version "5.7.23-23" is used. Nextcloud 21 will no longer support this version and requires MySQL 8.0 or MariaDB 10.2 or higher.

Please double check the [installation guides ↗](https://docs.nextcloud.com/server/24/go.php?to=admin-install), and check for any errors or warnings in the [log](https://cloud9.ctrlaltback.space/index.php/settings/admin/logging).

Check the security of your Nextcloud over [our security scan ↗](https://scan.nextcloud.com).
