---
created: 2022-08-05T09:41:03 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/hotlink-protection
author: 
---

# Hotlink Protection | Bluehost Support

---
### Summary

You can use the .htaccess file to enable Hotlink Protection on your site. This will prevent people from linking to your images.

___

-   [Hotlink Protection](https://www.bluehost.com/help/article/hotlink-protection#hotlink)

___

### Hotlink Protection

Apache has a built-in method for protecting images within directories from prying eyes, using the .htaccess file.  
 

When your browser sends a request for an image, it usually also sends the URL of the page that linked to that image. The following .htaccess file causes the server to check this URL ("Referer" in the following snippet) and, if it is one of the authorized URLs that you specify, it will set an internal flag called "locally\_linked". This internal flag is technically called an "environmental variable". If the URL sent is not in this list of authorized URLs, the flag (or ev) is not set. Note that we also set the "locally\_linked" variable if the browser does not send any URL at all: this occurs when the visitor accesses your site using a browser or a proxy that suppresses the referring URL.

The web server then checks if the file requested has an extension in the list given below (gif, png, jpg and jpeg). If so, and the "locally\_linked" variable is set, it will send the image. Otherwise, an error will be sent. If this is too complex, then you can use the Hotlink manager or the Password Protect icon in the cPanel.

```
SetEnvIfNoCase Referer    "^http://www.example.com/" locally_linked=1
SetEnvIfNoCase Referer "^http://www.example.com$" locally_linked=1
SetEnvIfNoCase Referer "^http://example.com/" locally_linked=1
SetEnvIfNoCase Referer "^http://example.com$" locally_linked=1
SetEnvIfNoCase Referer "^$" locally_linked=1
<FilesMatch ".(gif|png|jpe?g)$">
  Order Allow,Deny
  Allow from env=locally_linked
</FilesMatch>


```

Due to either ignorance or an "I'll do what I want because I want to" attitude, there are plenty of people that will place image tags on their pages that pull images from your server. This linking can place a greater load on your Bluehost server/account without having visitors actually seeing your website.  
Note: You can enable Hotlink Protection in the cPanel, [Hotlink Protection](https://www.bluehost.com/help/article/hotlink-protection-setup) [Setup](http://www.bluehost.com/help/article/hotlink-protection-setup).

___

-   [How does this work?](https://www.bluehost.com/help/article/hotlink-protection#mod)
-   [Setup Leech Protection with mod\_rewrite](https://www.bluehost.com/help/article/hotlink-protection#leech-protection)

___

### How does mod\_rewrite work?

The Apache Server's Mod Rewrite Engine can examine the name of the document requesting a file of a particular type. You can then define logic that basically does the following:

If the URL of the page requesting the image file is from an allowed domain, display the image. Otherwise, return a broken image.

The logic, or rules, are then placed in the directory(s) that contain your image files.  
 

### Setup Leech Protection with mod\_rewrite

In order for it to work, the browser that requested the page must return the URL of the page, or what is called the HTTP\_REFERRER. There is also a performance penalty on the server due to the extra overhead for testing the file requests.

This method should be used when off-site linking has become an issue of concern to you. A little bit of tolerance or maybe a gentle e-mail to the other site's webmaster may also be an acceptable solution. I have actually made a few friends this way!

1.  Make certain that your Apache Server was compiled with mod\_rewrite. By default, the basic installation of Apache does not include it. Do not attempt this if mod\_rewrite is not installed, or your site may stop functioning! Check with your system administrator. If you are the system administrator, check the Apache INSTALL file for instruction regarding the option --enable-module=rewrite
    -   Get organized! Try to get all of your images into directories that do not contain your HTML files. Each directory containing the images should have an empty index.html file to prevent people from looking at your directory listing.
    -   Create or edit a .htaccess in one of the directories containing your images. I suggest doing one directory first so you can test your rules, and quickly comment out the lines or rename the file if it causes server configuration errors. The .htaccess file should contain the following lines.
        
        ```
        RewriteEngine on
        RewriteCond %{HTTP_REFERER} !^$
        RewriteCond %{HTTP_REFERER} !^http://domain.com/.*$     [NC]
        RewriteCond %{HTTP_REFERER} !^http://www.domain.com/.*$ [NC]
        RewriteRule .*.gif$    -                            [L]
        ```
        
        ```
        RewriteCond %{HTTP_REFERER} !^$
        RewriteCond %{HTTP_REFERER} !^http://domain.com/.*$     [NC]
        RewriteCond %{HTTP_REFERER} !^http://www.domain.com/.*$ [NC]
        RewriteRule .*.jpg$      -                           [L]
        ```
        
          
        **Note**: When cutting and pasting, be sure that each RewriteCond is on one line. Line wrapping in the page display could introduce broken lines.
2.  Test! Create a page on another server and insert an image tag pointing to an image in the protected directory. If you get a broken image icon- you did it! The requests will still appear in your logs, but your bandwidth will be protected.
