---
created: 2022-08-05T09:41:51 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/character-sets-in-html
author: 
---

# Character sets in HTML | Bluehost Support

---
Many web browsers display Western Character Encoding (ISO-8859-1) by default. This means that pages with text in a non-Western alphabet, like Cyrillic or Arabic, will often look garbled. Unicode, on the other hand, is capable of displaying several alphabets; the standard Unicode encoding is UTF-8.

Not all character sets will be correctly rendered with this encoding format, but most will. You can find specific information about which character encoding will display at [Handling character encodings in HTML and CSS (tutorial)](https://www.w3.org/International/tutorials/tutorial-char-enc/index.en)

To ensure that your web page displays correctly across different web browsers and platforms (if it's not in English), you should take the following steps:

1.  In your PHP document, insert an XML line which specifies your character encoding under your Doc Type Declaration (DTD). If you're using UTF-8, then the line will look like this: <><?xml encoding="UTF-8"?>
2.  When coding your HTML, be sure to include a META tag in your header specifying the character set. If you're going to encode your page in Unicode, specify UTF-8 as your character set in the META tag. If you're going to use UTF-8 encoding, your META tag will look like this:
    
    ```
    <META http-equiv="Content-Type" content="text/html; charset=UTF-8">
    ```
    
3.  When saving your HTML, be sure that the character encoding is set to whatever you've specified it to be. If you choose UTF-8, then you will need to save your page in that type of encoding.
4.  In your Bluehost account, add an .htaccess file in the directory where your web pages using non-Western encoding will be. If your entire site uses different characters, then you can put your .htaccess file in public\_html/. Inside of the .htaccess file, add this line:
    
    ```
    AddDefaultCharset Off
    ```
    

**Note:** If you are using 'default.html' as the index or home page, our Apache configuration overrides the content-type for this file and sets it to ISO-8859-1, no matter what. To fix this issue, you will need to rename 'default.html' to 'index.html' or 'index.htm'
