 # How to config.php 
 **By Vincent_Stans**

I would like to share for those who did not know.
you can configure your Nextcloud installation with seperate config(s).php

create a file setting-name.config.php starting with

```
<?php
$CONFIG = array (
);
```


and put your settings after ( and before );

For example you have your default config.php that contain all your settings. To make your config.php clearer you can take all the database settings and put them in a separate config names database.config.php

the file database.config.php would look like
```
<?php
$CONFIG = array (
  'dbtype' => 'mysql',
  'dbname' => 'nextcloud',
  'dbhost' => 'localhost',
  'dbport' => '',
  'dbtableprefix' => 'oc_',
  'dbuser' => 'DB_USERNAME',
  'dbpassword' => 'DB_PASSWORD',
  'mysql.utf8mb4' => true,
);
```

Remove these copied settings from config.php
another example: redis.config.php

```
<?php
$CONFIG = array (
  'filelocking.enabled' => true,
  'memcache.locking' => '\\OC\\Memcache\\Redis',
  'memcache.local' => '\\OC\\Memcache\\Redis',
  'redis' =>
  array (
    'host' => 'localhost',
    'port' => 6379,
  ),
);
```

I give you one more for mail.config.php

```
<?php
$CONFIG = array (
  'mail_smtpmode' => 'sendmail',
  'mail_from_address' => 'cloud',
  'mail_domain' => 'domain.tld',
  'app.mail.imaplog.enabled' => 'true',
  'mail_smtpauthtype' => 'LOGIN',
  'mail_smtphost' => 'smtp.domain.tld',
  'mail_smtpport' => '587',
  'mail_smtpsecure' => 'tls',
  'mail_smtpauth' => 1,
  'mail_smtpname' => 'MAIL_USERNAME',
  'mail_smtppassword' => 'MAIL_PASSWORD',
);
```

custom.config.php

```
<?php
$CONFIG = array (
  'theme' => 'Theme1',
  'default_phone_region' => 'NL',
  'defaultapp' => 'files',
  'knowledgebaseenabled' => false,
  'simpleSignUpLink.shown' => false,
  'profile.enabled' => true,
  'login_form_autocomplete' => false,
);
```

Any file located in NC_Installation_dir/config/ ending with .config.php will be merged and stored as config.php
I found this very useful and hope others may have use of it too.