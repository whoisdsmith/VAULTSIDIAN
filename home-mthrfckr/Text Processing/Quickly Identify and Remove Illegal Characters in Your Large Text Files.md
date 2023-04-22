# Quickly Identify and Remove Illegal Characters in Your Large Text Files

---

When working with modeling software packages like XPSWMM or SWMM, text files are often used to store the models. Even software that uses a database to store the model, like InfoWorks ICM, may still use text files as an exchange format. As the size of the model grows, the text file can sometimes become corrupted, resulting in foreign characters or symbols appearing in the file. Unfortunately, the software may not always alert you to this issue, and you may experience strange errors when trying to work with the file.

In this post, I’ll show you how to quickly identify any illegal characters that may be causing problems in your text file.

To get started, you’ll need to open the text file using a text editor that supports regular expressions. [Notepad++](https://notepad-plus-plus.org/downloads/) is a popular choice, but there are many other options available. Once you have your text editor open, you can use a regular expression to search for any illegal characters in your file.

![](https://miro.medium.com/v2/resize:fit:700/1*QP3e-7ZY_fQU9JQiYArvBg.png)

The regular expression is: \[^a-zA-Z0–9#-\_!’”\\s\]. This expression will match any characters that are not letters (uppercase or lowercase), numbers, spaces, or any of the following special characters: #—\_ ! ‘ “.

![](https://miro.medium.com/v2/resize:fit:700/1*toP2lrM74W7ItkM4EPI45A.png)

If you find that this expression is not catching all of the illegal characters in your file, you can modify it to suit your needs. For example, if you know that your file should only contain ASCII characters, you could use the following regular expression instead: **\[^\\x00-\\x7F\]**. This expression will match any non-ASCII characters in your file.

By using regular expressions to search for illegal characters in your text file, you can quickly identify any issues that may be causing problems with your modeling software. This can save you a lot of time and frustration in the long run.
