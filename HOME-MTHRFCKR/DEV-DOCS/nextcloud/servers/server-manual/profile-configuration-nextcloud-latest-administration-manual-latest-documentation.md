---
tags:: documents
---
# Profile configuration — Nextcloud latest Administration Manual latest documentation

The user profile presents the information of a user and is enabled by default for all users. Users may individually enable or disable their profile in their Personal info settings under the Personal settings section.

As an administrator you may change the default for new users and may also disable profile globally to remove all profile functionality.

To enable or disable profile by default for new users switch the toggle in Basic settings under the Administration settings section.

![../_images/profile_default_setting.png](../_images/profile_default_setting.png)

Note

If you are upgrading from Nextcloud 22 to 23 and want profile to be disabled by default for all users, you may run the `occ` command below before upgrading or upgrade first then switch the toggle in Basic settings before letting any users log in.
    
    
    occ config:app:set settings profile_enabled_by_default --value="0"
    
    
    
    
    
    
    
    
    Please refer to [Using the occ command](../configuration_server/occ_command.html) for all available
    occ commands.
    
    
    
    
    To disable profile globally add the following line to your config.php
    
    
    
    
    
    'profile.enabled' => false,
    
    
    
    
    
    
    
    
    Please refer to [Configuration Parameters](../configuration_server/config_sample_php_parameters.html) for
    all available config.php options.
    
    
    
    
    © Copyright 2022 Nextcloud GmbH.
    
    
    
    
    


___

#article 