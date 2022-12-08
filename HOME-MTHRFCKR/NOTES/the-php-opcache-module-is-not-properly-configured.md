---
tags:: notes
created: 2022-07-04T22:19:58 (UTC -04:00)
tags: []
source: https://help.nextcloud.com/t/the-php-opcache-module-is-not-properly-configured/135870/5
author: 
---

# The PHP OPcache module is not properly configured



---
Hello,

I have these warning in my Nexcloud :

The PHP OPcache module is not properly configured:

-   The maximum number of OPcache keys is nearly exceeded. To assure that all scripts can be hold in cache, it is recommended to apply `opcache.max_accelerated_files` to your PHP configuration with a value higher than `3000`.
-   The OPcache buffer is nearly full. To assure that all scripts can be hold in cache, it is recommended to apply `opcache.memory_consumption` to your PHP configuration with a value higher than `32`.
-   The OPcache interned strings buffer is nearly full. To assure that repeating strings can be effectively cached, it is recommended to apply `opcache.interned_strings_buffer` to your PHP configuration with a value higher than `8`.

My opcache setup is :

zend\_extension=opcache.so;  
opcache.enable=1;  
opcache.memory\_consumption=32;  
opcache.interned\_strings\_buffer=8;  
opcache.max\_accelerated\_files=3000;  
opcache.revalidate\_freq=60;  
opcache.fast\_shutdown=0;  
opcache.enable\_cli=0;  
opcache.revalidate\_path=0;  
opcache.validate\_timestamps=1;  
opcache.max\_file\_size=0;  
opcache.file\_cache=/xxx/htdocs/nextcloud/.opcache;  
opcache.file\_cache\_only=1;

What are the recommanded values for opcache.max\_accelerated\_files and opcache.memory\_consumption and opcache.interned\_strings\_buffer ?

I use Nexcloud 23.0.2 with PHP 8 and Debian.

Thanks for your help

Thanks

---

Hi [@Marquys](https://help.nextcloud.com/u/marquys)

I use the following values from [this tutorial 72](https://www.c-rieger.de/nextcloud-installationsanleitung-apache2/) and never had any issues:

```
[opcache]
opcache.enable=1
opcache.enable_cli=1
opcache.memory_consumption=128
opcache.interned_strings_buffer=8
opcache.max_accelerated_files=10000
opcache.revalidate_freq=1
opcache.save_comments=1
```


When I set your values, I have the same warning…


Did you restart the php-fpm service?

```
systemctl restart php8.0-fpm
```

Maybe you also have to set `opcache.interned_strings_buffer=8` to higher value than 8. I mean that’s what it’s telling you… ![:wink:](https://help.nextcloud.com/images/emoji/twitter/wink.png?v=12 ":wink:") There are no “recommanded” values or a “one fits them all” solution because it highly depends on how many php processes are runing on your server, and how much memory they are using.

---

Reading this thread might also be helpful…

![](https://help.nextcloud.com/letter_avatar_proxy/v4/letter/b/46a35a/40.png) [Nextcloud 23.02 OPcache interned strings buffer](https://help.nextcloud.com/t/nextcloud-23-02-opcache-interned-strings-buffer/134007) [ℹ️ Support](https://help.nextcloud.com/c/support/7)

> Hello, I just updated from 23.0 to 23.02 and starting getting this warning: The OPcache interned strings buffer is nearly full. To assure that repeating strings can be effectively cached, it is recommended to apply opcache.interned\_strings\_buffer to your PHP configuration with a value higher than \`8’ I saw in the 10-opcache.ini file that the line was commented out so I guess 8 is the default. I uncommented the line and set the value to 16. After restarting php-fpm, the warning message went aw…

---

I don’t have FPM, I am hosted by Ionos in a small server.

---

I have read this thead but it’s not clear. Which value for opcache.max\_accelerated\_files and opcache.memory\_consumption and opcache.interned\_strings\_buffer please ?

---

Are there other PHP apps running on the server or only Nextcloud and which IONS server do you have exactly? 512MB, 2GB or more…?

I’m not an expert and others may be abele to give you a more detailed explenation on how this works. But at the end of the day it depends on your workload and on how much RAM your server has, which values you have to set. So you won’t get around doing some testing. On a server with 2GB of RAM, I would try to double the values and then see if the warnings go away and everything still runs fine. On a server with only 512MB of RAM it’s probably better to increase the values in smaller amounts, maybe by 25% or 50%.

Also, as far as I understand it, these warnings do not mean, that you absolutley have to increase the values. Nextcloud will still run, even with lower values. Of course the performance will get better if you increase them, but if you for example haven a server with only 512MB of RAM there is only so much headroom and so much you can do.

---

RAM : 12 Go (DDR3 ECC)  
4 core (HT) x 3,1 GHz

There is just a small wordpress in this server for the moment.

Thanks

---

Marquys:

> There is just a small wordpress in this server for the moment.

Well that’s most likely at least one factor why it complains that the values are too low. Any additional PHP app you are hosting on your server uses the opcache too and therefore it adds to it.

If you want to dive deeper into the topic in order to fine tune it, threre are plenty of opcache tuning guides on the internet. But I don’t think it’s necessary to go into too much detail if the instance is only for personal use with relatively low traffic. Just do what the warnings suggest and increase those values. 12GB is plenty of RAM so I would start with doubleing all the values it complains about and then go from there and maybe increase individual values even further, if necessary.

---

My Wordpress don’t use OPcache.

I have double the value and I have the same warnings…

---

Does the warning show the new values? If for examle the `opcache.interned_strings_buffer` warning still says `8` then it does not use the new values. If it says `16`, try `24` or `32`.

And try rebooting your server in case the new values do not take effect.

---

Yes the warning show the new values. I can’t reboot the server, I don’t have a root access.

---

I hope it’s OK to participate in this thread, because I have the same problem as the thread starter. I googled the problem and also searched the forum and there are dozens of threads with this problem - all since Nextcloud 23.

I get the messages like in the first posting, but with the values 10000 / 128 / 8. So I increased them via the `/.user.ini` to 20000 / 256 / 16. I still get these messages with the values as before. I cannot restart anything, because I use a web hoster (all-inkl in Germany).

The user.ini works, because when I set the `memory_limit` to 512 MB, I can remove the message which says I should increase it to 512 MB.

So the question is, how can I get rid of the OPCache messages in the admin panel? Double the values again? I use a rather small NC installation, only 15 users (only 1 or 2 active at the same time) and the calendar is the only app (no filesharing at all).

Currently for me it looks like the messages concerning OPCache are more a bug than a new feature since version 23.

---

bvp:

> Currently for me it looks like the messages concerning OPCache are more a bug than a new feature since version 23.

Maybe. Or maybe something is not working as it should, if your OPCache gets filled up even if you double and triple the values. Or maybe you have that much going on on your server, that it uses that much. Hard to say. I doubled it on my server to 16 and never saw the warning again.

Besides of that: Warning messages are not error messages and can be ignored, if you face no issues. This is especially true for cache settings, which are more like recommendations than hard requirements. Of course you should have certain minimum values, if you want everything to run stable and performant. But otherwise there are no “one fits them all” values. This is the reason why this warning now is dynamic and should appear depending on the actual usage of the cache.

Btw. If you have enough RAM I would recommend to also increase the `memory_limit` even further: For example: 1024MB if your server has 4GB RAM or 2048MB if it has 8GB RAM.
