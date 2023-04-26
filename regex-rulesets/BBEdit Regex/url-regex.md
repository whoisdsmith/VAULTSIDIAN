# URL RegEx

---

https://www.example.com/my/path//to-file.jpg

```
(?<!:)/+
```

HTTP and HTTPS URLs that start with protocol can be validated using the following regular expression

```
/^https?:\/\/(?:www\.)?[-a-zA-Z0-9@:%.*\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%*\+.~#?&\/=]*)$/
```

The regular expression to validate URL without protocol is very similar:

```
/^[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%_\+.~#?&//=]*)$/
```


PHP (use with [preg_match](https://php.net/manual/en/function.preg-match.php))

```
%^(?:(?:https?|ftp)://)(?:\S+(?::\S*)?@|\d{1,3}(?:\.\d{1,3}){3}|(?:(?:[a-z\d\x{00a1}-\x{ffff}]+-?)*[a-z\d\x{00a1}-\x{ffff}]+)(?:\.(?:[a-z\d\x{00a1}-\x{ffff}]+-?)*[a-z\d\x{00a1}-\x{ffff}]+)*(?:\.[a-z\x{00a1}-\x{ffff}]{2,6}))(?::\d+)?(?:[^\s]*)?$%iu
```

Python

```
http[s]?://(?:[a-zA-Z]|[0-9]|[$-_@.&+]|[!*\(\),]|(?:%[0-9a-fA-F][0-9a-fA-F]))+
```

Javascript

```
/((([A-Za-z]{3,9}:(?:\/\/)?)(?:[\-;:&=\+\$,\w]+@)?[A-Za-z0-9\.\-]+|(?:www\.|[\-;:&=\+\$,\w]+@)[A-Za-z0-9\.\-]+)((?:\/[\+~%\/\.\w\-_]*)?\??(?:[\-\+=&;%@\.\w_]*)#?(?:[\.\!\/\\\w]*))?)/
```

HTML5

```
<input type="url" />
```

Below is the regex used in type=”url” from [RFC3986](https://www.ietf.org/rfc/rfc3986.txt):

```
^(([^:/?#]+):)?(//([^/?#]*))?([^?#]*)(\?([^#]*))?(#(.*))?
```

Perl

```
^(((ht|f)tp(s?))\://)?(www.|[a-zA-Z].)[a-zA-Z0-9\-\.]+\.(com|edu|gov|mil|net|org|biz|info|name|museum|us|ca|uk)(\:[0-9]+)*(/($|[a-zA-Z0-9\.\,\;\?\'\\\+&%\$#\=~_\-]+))*$
```

Ruby

```

/\A(?:(?:https?|ftp):\/\/)(?:\S+(?::\S*)?@)?(?:(?!10(?:\.\d{1,3}){3})(?!127(?:\.\d{1,3}){3})(?!169\.254(?:\.\d{1,3}){2})(?!192\.168(?:\.\d{1,3}){2})(?!172\.(?:1[6-9]|2\d|3[0-1])(?:\.\d{1,3}){2})(?:[1-9]\d?|1\d\d|2[01]\d|22[0-3])(?:\.(?:1?\d{1,2}|2[0-4]\d|25[0-5])){2}(?:\.(?:[1-9]\d?|1\d\d|2[0-4]\d|25[0-4]))|(?:(?:[a-z\u00a1-\uffff0-9]+-?)*[a-z\u00a1-\uffff0-9]+)(?:\.(?:[a-z\u00a1-\uffff0-9]+-?)*[a-z\u00a1-\uffff0-9]+)*(?:\.(?:[a-z\u00a1-\uffff]{2,})))(?::\d{2,5})?(?:\/[^\s]*)?\z/i

```

Objective-C

```

(http|https)://((\\w)*|([0-9]*)|([-|_])*)+([\\.|/]((\\w)*|([0-9]*)|([-|_])*))+
```

Swift

```
((?:http|https)://)?(?:www\\.)?[\\w\\d\\-_]+\\.\\w{2,3}(\\.\\w{2})?(/(?<=/)(?:[\\w\\d\\-./_]+)?)?
```

Java

```
^(https?|ftp|file)://[-a-zA-Z0-9+&@#/%?=~_|!:,.;]*[-a-zA-Z0-9+&@#/%=~_|]
```

VB.NET

```
(http(s)?://)?([\w-]+\.)+[\w-]+[.com]+(/[/?%&=]*)?
```

C #

```
^(ht|f)tp(s?)\:\/\/[0-9a-zA-Z]([-.\w]*[0-9a-zA-Z])*(:(0-9)*)*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&%\$#_]*)?$
```

This Regex Validates a Url Which Should Include **http** or **https**

```
https**?**:\/\/**(**www\.**)****?**_[-a-zA-Z0-9@:%._**\+**~#=]_**{1,256}**\._[a-zA-Z0-9()]_**{1,6}****\b****(**_[-a-zA-Z0-9()!@:%_**\+**.~#?&**\/****\/**=]_*******)**
```

For URL RegEx Try

---

```vbnet
((?:https?:\/\/)?(?:www\.)?facebook\.com\/[\w.]*)(?=[^w.])(?!.*\1)
```

It's your regex (somewhat simplified) with a negative look ahead added to make sure the URL isn't repeated later in the text. This means that **only the last match** is kept in the list.

```vbnet
((?:https?:\/\/)?(?:www\.)?facebook\.com\/[\w.]*)
```

Find All Links and Urls

```
\b(?:https?://|www\.)\S+\b
```

1. Match email addresses:

```
\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b
```

1. Match URLs with optional "www" prefix:

```
\b(?:https?://)?(?:www\.)?\S+\b
```

1. Match social media URLs (Facebook, Twitter, Instagram, etc.):

```
\b(?:https?://)?(?:www\.)?(?:facebook|twitter|instagram)\.\S+\b
```

Regular expression that can be used to remove double lines (i.e., blank lines):

Find:

```
^\s*\n
```

Replace with:

```
(empty string)
```

Regular expression that can be used to replace two line breaks with one:

Find:

```
\n\n
```

Replace with:

```
\n
```
