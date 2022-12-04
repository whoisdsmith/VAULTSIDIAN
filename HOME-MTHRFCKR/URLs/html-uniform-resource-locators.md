# HTML Uniform Resource Locators

A Uniform Resource Locator (URL), which is commonly called a web address, is a reference to a web resource specifying its location on the computer network and a mechanism for restoring it. A URL is a special type of Uniform Resource Identifier (URI), although sometimes these two terms are used interchangeably. In the majority web browsers, the URL of a web page is displayed above the page in an address bar.

A URL can be composed of words or an Internet Protocol (IP) address. Generally, users enter the name as they are easier to remember than numbers.

The syntax of a full Web address is the following:

```
scheme://prefix.domain:port/path/filename
```

### Explanation:

<table class="table table-bordered table-striped table-header small-font"><tbody><tr><td>scheme</td><td>Specifies the type of Internet service. http/https is the most common.</td></tr><tr><td>prefix</td><td>Specifies a domain prefix. www is the default for http.</td></tr><tr><td>domain</td><td>Specifies the name of the Internet domain.</td></tr><tr><td>port</td><td>Specifies the port number at the host. 80 is the default for http.</td></tr><tr><td>path</td><td>Specifies a path at the server. If it is omitted, the resource will be located at the root directory.</td></tr><tr><td>filename</td><td>Specifies the name of a resource or document.</td></tr></tbody></table>

  

In [HTML](https://www.w3docs.com/learn-html/html-introduction.html), a URL can have a partial form which is often called a relative URL. To create a full URL, a browser fills in missing parts of the URL from the relevant parts of the URL of the current page.

The following table lists some common schemes:

| Scheme | Used for |
| --- | --- |
| http (HyperText Transfer Protocol) | Common web pages (non encrypted). |
| https (Secure HyperText Transfer Protocol) | Secure web pages (encrypted). |
| ftp (File Transfer Protocol) | Downloading or uploading files. |
| file | A file on your computer. |

## URL Encoding

URLs can be transmitted over the Internet only using the [ASCII character set.](https://www.w3docs.com/learn-html/html-ascii.html) If a URL has characters outside the ASCII set, the URL must be converted.

Non-ASCII characters are replaced with a "%", which is followed by hexadecimal digits.

URLs cannot contain spaces. URL encoding commonly replaces a space with %20, or a plus (+) sign.