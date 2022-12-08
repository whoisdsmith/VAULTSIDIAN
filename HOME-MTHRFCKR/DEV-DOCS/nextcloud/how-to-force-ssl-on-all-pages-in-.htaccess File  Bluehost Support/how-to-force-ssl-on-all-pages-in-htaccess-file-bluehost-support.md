---
created: 2022-08-05T11:13:17 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/force-ssl-on-all-pages
author: 
---

# How To Force SSL On All Pages In .htaccess File | Bluehost Support

---
___

-   [Forcing All Pages](https://www.bluehost.com/help/article/force-ssl-on-all-pages#forcing-all-pages)
-   [Forcing Specific Pages](https://www.bluehost.com/help/article/force-ssl-on-all-pages#forcing-specific-pages)
    -   [Edit The .htaccess File](https://www.bluehost.com/help/article/force-ssl-on-all-pages#edit-htaccess-file)

___

## Forcing All Pages

You can force all of your pages to use HTTPS. To do this, you will need to modify your .htaccess file.

Using the **Code Editor** in the **File Manager**, add these lines to the beginning of the .htaccess file.

```
RewriteEngine On 
RewriteCond %{HTTPS} off 
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

## Forcing Specific Pages

To set up SSL protection on specific pages, you must edit the .htaccess file specific to that domain. For more information on how to access the .htaccess, please see this article [.htaccess Tutorial](https://www.bluehost.com/help/article/htaccess-tutorial). 

**Note**: The **Advanced** tab will load your cPanel. **Legacy** accounts will feature a **horizontal navigation** bar at the top of the screen, while **Bluerock** account users will see a **vertical navigation** menu on the left-hand side of the screen. To learn more, please see [Bluerock vs. Legacy](https://www.bluehost.com/help/article/rock-vs-legacy).

### Edit The .htaccess File

Access the .htaccess file inside the **file manager**:

#### Bluerock Account

![[How To Force SSL On All Pages In .htaccess File  Bluehost Support/rock-file-manager.gif]]

1.  Log in to your [Bluehost control panel.](https://my.bluehost.com/cgi-bin/cplogin)
2.  Click the **Advanced** tab on the left-hand side menu.
3.  Under the **File** section, click the **File Manager** icon.
4.  Look for the **Settings** button located towards the upper right corner of your screen.  
    ![[How To Force SSL On All Pages In .htaccess File  Bluehost Support/rock-file-manager-settings.png]]
5.  From here, click the **Preferences** pop-up, then click the checkbox for **Show Hidden Files (dotfiles)**.  
    ![[How To Force SSL On All Pages In .htaccess File  Bluehost Support/rock-file-manager-preferences.png]]
6.  Scroll to locate the .htaccess file from the list.

#### Legacy Account

![[How To Force SSL On All Pages In .htaccess File  Bluehost Support/legacy-file-manager.gif]]

1.  Log in to your [Bluehost control panel](https://my.bluehost.com/cgi-bin/cplogin).
2.  Click the **File Manager** icon located in the file section.
3.  From the file manager pop-up settings, choose the folder you would like to open, most often the **WebRoot (public\_html/www).**
4.  Under the Preferences, make sure the **Show hidden files** is checked**.**  
    ![[How To Force SSL On All Pages In .htaccess File  Bluehost Support/legacy-file-show-hidden-files1.png]]
    
    **Note**: If you do not see this pop-up, you will need to click the reset all interface settings link at the bottom of the cPanel page.
    
5.  Click the **Submit** button.
6.  The File Manager will open in a new tab or window.
7.  Look for the **.htaccess** file in the list of files. You may need to scroll to find this file.

**Then proceed to the steps below, which will explain how to edit the file to add protection.**

1.  Right-click on the **.htaccess** file and select the **Edit** option.
2.  A pop-up message will appear, then click the **Edit** button.
3.  At the top of the file, insert the following **code**:
    
    ```
    RewriteEngine On 
    RewriteCond %{HTTPS} off 
    RewriteCond %{REQUEST_URI} /[SSL Requested page]/ 
    RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [R,L]
    ```
    
4.  Click the **Save Changes** button towards the top right corner of your screen.
5.  Check your website to ensure it is functioning as expected.

**If that doesn't work**, you can try using this default cPanel code.

```
RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://example.com/$1 [R,L]
```

**Note:** Make sure to replace **_example.com_** with **your domain name**. Don't forget to **Save Changes** when finished.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
