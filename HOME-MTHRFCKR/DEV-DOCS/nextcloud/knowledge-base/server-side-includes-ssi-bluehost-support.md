---
created: 2022-08-05T09:41:41 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/server-side-includes-ssi
author: 
---

# Server Side Includes (SSI) | Bluehost Support

---
## **Apache Handlers**

By default, **.html** files will not run **server side includes**, but **.shtml** files will. To allow these you need to add a new handler for **HTML**:

To allow **SSI**, set the handler as '**server-parsed**' and the extension as '**.html**' (without the quotes).

This will tell the server to read the **.html** files so that you may use these directives in them.

Follow these rules:

-   Commands and arguments are in lowercase letters
-   The double quotes around the value are required
-   There is no space until after the command
-   That hash mark (#) is required
-   There is a space after the second double quote, before the second double hyphen (at the end)

Here's the format of the **SSI**:

```
<!--#include file="included.html" -->
```

The above format will create an SSI that will include the text found in the file "**included.html**".

## Why Use "**file="**?

You use "**file="** when the file that will be included is held within the same directory as the file that is calling for it. You can also use the file argument when the file is within a subdirectory of the directory containing the file that is calling for it.

You would use the "**virtual="** argument if the file you are calling for is located in a position requiring an address starting at the server root. This means the file isn't in the same directory as the page that's calling for it.

Many times an "**includes**" directory is setup that contains all of your include files. This is a popular method of doing things. If so, then you'll use the **virtual** argument to attach the **SSI** command to the files. Just make a point of giving the command the path from the server root (the domain name). Like so:

```
<!--#include virtual="/directory/included.html" -->
```

That forward slash before the first directory is representative of the domain name (server root for that domain).

**/home#/username/public\_html/** is the server root to your Main Site of your hosting account (where username is your cPanel username).

**/home#/username/public\_html/addondomain/** is the server root to an addon domain of your hosting account.

If you have a file located at **/home#/username/public\_html/addondomain/includes/includedfile.html** that you want to include in **http://www.addondomain.com/index.html**, then your **SSI** format inside the index.html file would look like this:

**`<!--#include virtual="/includes/includedfile.html" -->`**

By using that leading slash, the server will add the domain name to the front of the address for you.

Rule of Thumb Use "**file="** when the included file is within the same directory as the page that wants it. Use "**virtual="** when it isn't.

**Note:** You need to adjust /home#/ to /home/, /home1/ or home2/ or a different number depending on the home directory your account resides on. To view the home directory for your account simply view the stats column on the main cPanel page of your account and look for the home directory.

### **Additional Notes:**

By Default, there is an **Apache Handler** on the server to parse **.shtml** files which already have **server side includes** (**SSI**) inside of them.

Please add this line of code to the .htaccess file to run .shtml includes in a regular html file. AddHandler server-parsed .html

-   **SSI**s will **_NOT work_** until the **DNS** has propagated to the Bluehost **name servers**. You will not be able to test them in advance by using something in the format of **http://204.130.255.7/~username/test.shtml**.
