---
created: 2022-08-05T09:41:12 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/url-redirect-rewrite-using-the-htaccess-file
author: 
---

# URL redirect/rewrite using the .htaccess file | Bluehost Support

---
## Overview

By default, your website can be accessed with both www.example.com and example.com. Since Google penalizes this due to duplicated content reasons, you should restrict access to either www.example.com or example.com. Some links may be outside of your website scope, and/or the search engines may have already indexed your website under both addresses.

Your primary .htaccess file is located in your public\_html folder. To see how to access this file, please see our [htaccess Tutorial](https://www.bluehost.com/help/article/htaccess-tutorial).

___

-   [Redirecting to or from www](https://www.bluehost.com/help/article/url-redirect-rewrite-using-the-htaccess-file#www)
-   [Redirect to example.com/index.php](https://www.bluehost.com/help/article/url-redirect-rewrite-using-the-htaccess-file#page)
-   [How to add a trailing slash](https://www.bluehost.com/help/article/url-redirect-rewrite-using-the-htaccess-file#slash)

___

## Redirecting to or from WWW

_**How do I redirect all links from www.example.com to example.com?**_

**Create a 301 redirect forcing all http requests to use either www.example.com or example.com:**

-   **Example 1 - Redirect example.com to www.example.com:**

```
RewriteEngine On
RewriteCond %{HTTP_HOST} !^www.example.com$ [NC]
RewriteRule ^(.*)$ http://www.example.com/$1 [L,R=301]
```

-   **Example 2 - Redirect www.example.com to example.com:**

```
RewriteEngine on
RewriteCond %{HTTP_HOST} ^www\.example\.com$
RewriteRule ^/?$ "http\:\/\/example\.com\/" [R=301,L]
```

**Explanation of this .htaccess 301 redirect:**

Let's have a look at example 1 - Redirect example.com to www.example.com. The first line tells apache to start the rewrite module. The next line:

```
RewriteCond %{HTTP_HOST} !^www.example.com$ [NC]
```

specifies that the next rule only fires when the http host (that means the domain of the queried url) is not (- specified with the "!") www.example.com.

The $ means that the host ends with www.example.com - and the result is that all pages from www.example.com will trigger the following rewrite rule. Combined with the inversive "!" is the result, every host that is not www.example.com will be redirected to this domain.

The \[NC\] specifies that the HTTP host is case insensitive. The escapes the "." - because this is a special character (normally, the dot (.) means that one character is unspecified).

The final line describes the action that should be executed:

```
RewriteRule ^(.*)$ http://www.example.com/$1 [L,R=301]
```

The ^(.\*)$ is a little magic trick. Can you remember the meaning of the dot? If not, this can be any character(but only one). So .\* means that you can have a lot of characters, not only one. This is what we need because ^(.\*)$ contains the requested URL without the domain.

The next part http://www.example.com/$1, describes the target of the rewrite rule. This is our "final" used domain name, where $1 contains the content of the (.\*).

The next part is also important since it does the 301 redirects for us automatically: \[L, R=301\]. L means this is the last rule in this run. After this rewrite, the webserver will return a result. The R=301 means that the web server returns a 301 moved permanently to the requesting browser or search engine.

## Redirect to example.com/index.php

You have a website with the name example.com, and you want to redirect all incoming URLs that are going to example.com/ to example.com/index.php.

```
RewriteEngine On
RewriteCond %{HTTP_HOST} ^example.com$
RewriteRule ^$ http://example.com/index.php [L,R=301]
```

****Explanation of this .htaccess 301 redirect:****

What does this code above do? Let's have a look at Example 1 - Redirect example.com to www.example.com. The first line starts the rewrite module. The next line:

```
RewriteCond %{HTTP_HOST} !www.example.com$
```

specifies that the next rule only fires when the HTTP host (that means the domain of the queried URL) is not (- specified with the "!") www.example.com.

The $ means that the host ends with www.example.com - and the result is that all pages from example.com will trigger the following rewrite rule. Combined with the inversive "!" is the result, every host that is not www.example.com will be redirected to this domain.

The \[NC\] specifies that the HTTP host is case insensitive. The escapes the "." - because this is a special character (normally, the dot (.) means that one character is unspecified).

The final line describes the action that should be executed:

```
RewriteRule ^(.*)$ http://www.example.com/$1 [L,R=301].
```

The ^(.\*)$ is a little magic trick. Remember the meaning of the dot? If not, this can be any character(but only one). The .\* means that you can have a lot of characters, not only one. This is what was intended. ^(.\*)$ contains the requested URL without the domain.

The next part http://www.example.com/$1 \[L, R=301\], describes the target of the rewrite rule -this is the "final" used domain name, where $1 contains the content of the (.\*).

The next part is also important since it does the 301 redirects for us automatically: \[L, R=301\]. L means this is the last rule in this run. After this rewrite, the webserver will return a result. The R=301 means that the web server returns a 301 moved permanently to the requesting browser or search engine.

**Redirect visitors to a new site**

You have an old website accessible under oldexample.com, and you have a new website accessible under newexample.com. Copying the old website's content to the new website is the first step - but what comes after that? You should do a 301 moved permanently redirect from the old domain to the new domain - which is easy and has some advantages:

-   Users will automatically be redirected to the new domain - you do not have to inform them.
-   Search engines will be redirected to the new domain, and all related information will be moved to the new domain (but this might take some time).
-   Google's PageRank Ã¢â€žÂ¢ will be transferred to the new domain, as well as other internal information that is being used to set the position of pages in the search engine result pages (serp's) - like TrustRank.

**Create a 301 redirect for all http requests that are going to the old domain.**

-   **Example 1 - Redirect from oldexample.com to www.newexample.com:**

```
RewriteEngine On
RewriteCond %{HTTP_HOST} !oldexample.com$ [NC]
RewriteRule ^(.*)$ http://www.newexample.com/$1 [L,R=301]
```

This is useful when you use www.newexample.com as your new domain name (see also this article about redirecting www and non-www domains). If not - use the code of example 2.

-   **Example 2 - Redirect from oldexample.com to newexample.com:**

```
RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} !oldexample.com$ [NC]
RewriteRule ^(.*)$ http://newexample.com/$1 [L,R=301]
```

## How to add a trailing slash

Some search engines remove the trailing slash from URLs that look like directories - e.g., Yahoo does it. However, it could result in duplicated content problems when the same page content is accessible under different URLs. Apache gives some more information in the Apache Server FAQ.

Let's have a look at an example: example.com/google/ is indexed in Yahoo as example.com/google - which would result in two URLs with the same content.

The solution is to create a .htaccess rewrite rule that adds the trailing slashes to these URLs. Example - redirect all URLs that do not have a trailing slash to URLs with a trailing slash:

```
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_URI} !example.php
RewriteCond %{REQUEST_URI} !(.*)/$
RewriteRule ^(.*)$ http://example.com/$1/ [L,R=301]
```

**Explanation of the add trailing slash .htaccess rewrite rule:**

The first line tells Apache that this is code for the rewrite engine of the mod\_rewrite module of Apache. The 2nd line sets the current directory as the page root. But the interesting part is:  
`RewriteCond %{REQUEST_FILENAME} !-f`

makes sure that existing files will not get a slash added. You shouldn't do the same with directories since this would exclude the rewrite behavior for existing directories. The line

```
RewriteCond %{REQUEST_URI} !example.php
```

excludes a sample URL that should not be rewritten. This is just an example. If you do not have a file or URL that should not be rewritten, remove this line. The condition:

```
RewriteCond %{REQUEST_URI} !(.*)/$
```

finally fires when a URL does not contain a trailing slash. Now we need to redirect the URLs without the trailing slash:

```
RewriteRule ^(.*)$ http://example.com/$1/ [L,R=301]
```

does the 301 redirect to the URL, with the trailing slash appended? You should replace example.com with your domain.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
