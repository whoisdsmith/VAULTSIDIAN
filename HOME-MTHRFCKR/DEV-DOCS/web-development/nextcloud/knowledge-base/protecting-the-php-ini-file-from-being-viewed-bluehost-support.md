---
created: 2022-08-05T09:11:40 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/protecting-the-php-ini-file-from-being-viewed
author: 
---

# Protecting the php.ini File From Being Viewed | Bluehost Support

---
To prevent people to viewing your php.ini file via a browser a few lines need to be pasted into the .htaccess file.

1.  Log in to your [Bluehost cPanel account.](https://my.bluehost.com/cgi-bin/cplogin)
2.  Click on File Manager (if prompted, select the checkbox to view hidden files)
3.  Double-click on the public\_html folder to open it
4.  Right-click on the .htaccess file and then select the "Edit".
5.  Paste the following code into the bottom of the file and then click save:

```
<Files php.ini>
  Order allow,deny
  Deny from all
</Files>
```

 

Now your php.ini file is protected. This change prevents PHP hackers from finding exploits on your site.
