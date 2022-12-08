---
created: 2022-08-05T09:12:14 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/about-directory-index
author: 
---

# Directory Index | Bluehost Support

---
There is a .htaccess code that allows you to specify the file, which loads as your default page whenever anyone types your domain name.

**Example:** If you type **_http://www.Bluehost.com_** in your browser's Address Bar, then the page which loads is **index.shtml**. You can test this by typing **_http://www.Bluehost.com/index.shtml_** and noticing that you get the same result.

___

-   [What to do first](https://www.bluehost.com/help/article/about-directory-index#what-todo)
-   [Here is the code format](https://www.bluehost.com/help/article/about-directory-index#code-format)
-   [Where do I put this code for an Addon or Subdomain?](https://www.bluehost.com/help/article/about-directory-index#where-to-put)

___

Tired of seeing the index.html file when you go to http://example.com? Want to see home.html or Index.php instead? No problem!

### What to do first

1.  Log in to your [Bluehost control panel](http://my.bluehost.com/).
2.  Go to the **File Manager** (or use FTP instead).  
    ![[rock-file-manager.gif]]
3.  Navigate to your **public\_html** folder and edit or create a file named **.htaccess**.
4.  Insert the code as described below.

### Here is the code format

```
DirectoryIndex filename.ext
```

This would cause filename.ext to be treated as your default page. You can also append other filenames to it. You may want to have each folder without filename.ext to use a different page name as the default page. That's no problem too.

```
DirectoryIndex home.html index.php index.shtml page1.php
```

Placing the above code in your .htaccess file will cause this to happen. When a user types in yoursite.com, your site looks for home.html in your root directory, find it, and load that page as the default page. If it does not find home.html, it will then look for index.php; if it finds that one, it will load it; if not, it will look for index.shtml, and the whole process repeats until it finds a file it can use. The list of files is read from left to right.

The .htaccess file is recursive, meaning it affects all the subfolders that do not have their own .htaccess file.

### Where do I put this code for an Addon or Subdomain?

Instead of creating and editing the .htaccess file inside public\_html, do this inside the document root folder of your Addon or Subdomain name. You will be able to see your domain's document root by following the instructions below:

1.  Log in to your [Bluehost control panel](http://my.bluehost.com/).
2.  Click the **Domains** tab from the side navigation menu to the left.  
    ![[rock-subdomains-docroot.png]]
3.  Hit on the word Subdomains that will appear underneath it.
4.  You will be able to see a list of all the subdomains and addon domains you have on your account, including its corresponding document root. 

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
