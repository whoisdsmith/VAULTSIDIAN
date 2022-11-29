# URL RegEx

---

Let’s say you want to fix a URL that looks like:

```
https://www.example.com/my/path//to-file.jpg
```

Using a string replace or a simple regex could incorrectly “fix” the double slashes following the protocol. We can fix that by using a negative lookbehind.

```
(?<!:)/+
```

**For PHP:**

```
<?php$url = 'https://www.example.com/my/path//to-file.jpg';$str = preg_replace('#(?<!:)/+#im', '/', $url);// https://www.example.com/my/path/to-file.jpg
```

**For Javascript:**

```
let url = 'https://www.example.com/my/path//to-file.jpg';url.replaceAll(/(?<!:)\/+/gm, '/');// "https://www.example.com/my/path/to-file.jpg"
```

---

# URL Regex That Starts with HTTP or HTTPS

HTTP and HTTPS URLs that start with protocol can be validated using the following regular expression

```
/^https?:\/\/(?:www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%_\+.~#?&\/=]*)$/
```

Test it!

```
/^https?:\/\/(?:www\.)?[-a-zA-Z0-9@:%.*\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%*\+.~#?&\/=]*)$/
```



Example code in Javascript:

```
var httpRegex = /^https?:\/\/(?:www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%_\+.~#?&\/=]*)$/;
// Validate URL
httpRegex.test('https://uibakery.io'); // Returns true
httpRegex.test('https:/uibakery.io'); // Returns false

// Extract URL from a string
var httpRegexG = /https?:\/\/(?:www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%_\+.~#?&\/=]*)/g;
'You can view more details at https://uibakery.io or just ping via email.'.match(httpRegexG); // returns ['https://uibakery.io']
```

# URL Regex That doesn’t Start with HTTP or HTTPS

The regular expression to validate URL without protocol is very similar:

```
/^[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%_\+.~#?&//=]*)$/
```

Test it!

```
/^[-a-zA-Z0-9@:%.*\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%*\+.~#?&//=]*)$/
```



Example code in Javascript:

```
var httpRegex = /^[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%_\+.~#?&//=]*)$/;
// Validate URL
httpRegex.test('uibakery.io/contact'); // Returns true
httpRegex.test('/uibakery.io'); // Returns false

// Extract URL from a string
var httpRegexG = /[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b(?:[-a-zA-Z0-9()@:%_\+.~#?&//=]*)/g;
'You can view more details at uibakery.io or just ping via email.'.match(httpRegexG); // returns ['uibakery.io']
```


## Notes on URL Validation

The above-mentioned regular expressions only cover the most commonly used types of URLs with domain names. If you have some more complex cases you might need a different solution.Call home or are you

---

# The Perfect URL Regular Expression

Simply copy and paste the URL regex below for the language of your choice.

## PHP (use with [preg_match](https://php.net/manual/en/function.preg-match.php))

```
%^(?:(?:https?|ftp)://)(?:\S+(?::\S*)?@|\d{1,3}(?:\.\d{1,3}){3}|(?:(?:[a-z\d\x{00a1}-\x{ffff}]+-?)*[a-z\d\x{00a1}-\x{ffff}]+)(?:\.(?:[a-z\d\x{00a1}-\x{ffff}]+-?)*[a-z\d\x{00a1}-\x{ffff}]+)*(?:\.[a-z\x{00a1}-\x{ffff}]{2,6}))(?::\d+)?(?:[^\s]*)?$%iu
```

## PHP (with [validate filter](https://php.net/manual/en/filter.filters.validate.php))

```
if (filter_var($url, FILTER_VALIDATE_URL) !== false)...
```

<iframe id="aswift_0" style="height: 1px !important; max-height: 1px !important; max-width: 1px !important; width: 1px !important;"><iframe id="google_ads_frame0"></iframe>

---

## Python

```
http[s]?://(?:[a-zA-Z]|[0-9]|[$-_@.&+]|[!*\(\),]|(?:%[0-9a-fA-F][0-9a-fA-F]))+
```

## Javascript

```
/((([A-Za-z]{3,9}:(?:\/\/)?)(?:[\-;:&=\+\$,\w]+@)?[A-Za-z0-9\.\-]+|(?:www\.|[\-;:&=\+\$,\w]+@)[A-Za-z0-9\.\-]+)((?:\/[\+~%\/\.\w\-_]*)?\??(?:[\-\+=&;%@\.\w_]*)#?(?:[\.\!\/\\\w]*))?)/
```

## HTML5

```
<input type="url" />
```

Below is the regex used in type=”url” from [RFC3986](https://www.ietf.org/rfc/rfc3986.txt):

```
^(([^:/?#]+):)?(//([^/?#]*))?([^?#]*)(\?([^#]*))?(#(.*))?
```

## Perl

```
^(((ht|f)tp(s?))\://)?(www.|[a-zA-Z].)[a-zA-Z0-9\-\.]+\.(com|edu|gov|mil|net|org|biz|info|name|museum|us|ca|uk)(\:[0-9]+)*(/($|[a-zA-Z0-9\.\,\;\?\'\\\+&%\$#\=~_\-]+))*$
```

## Ruby

```

/\A(?:(?:https?|ftp):\/\/)(?:\S+(?::\S*)?@)?(?:(?!10(?:\.\d{1,3}){3})(?!127(?:\.\d{1,3}){3})(?!169\.254(?:\.\d{1,3}){2})(?!192\.168(?:\.\d{1,3}){2})(?!172\.(?:1[6-9]|2\d|3[0-1])(?:\.\d{1,3}){2})(?:[1-9]\d?|1\d\d|2[01]\d|22[0-3])(?:\.(?:1?\d{1,2}|2[0-4]\d|25[0-5])){2}(?:\.(?:[1-9]\d?|1\d\d|2[0-4]\d|25[0-4]))|(?:(?:[a-z\u00a1-\uffff0-9]+-?)*[a-z\u00a1-\uffff0-9]+)(?:\.(?:[a-z\u00a1-\uffff0-9]+-?)*[a-z\u00a1-\uffff0-9]+)*(?:\.(?:[a-z\u00a1-\uffff]{2,})))(?::\d{2,5})?(?:\/[^\s]*)?\z/i

```

---

<iframe id="aswift_1" style="height: 1px !important; max-height: 1px !important; max-width: 1px !important; width: 1px !important;"><iframe id="google_ads_frame1"></iframe>

---

## Go (use the Govalidator [IsURL()](hhttps://github.com/asaskevich/govalidator/blob/master/validator.go#L49))

```

package main  
 import (  
         "fmt"  
         "github.com/asaskevich/govalidator"  
 )  
 func main() {  
         str := "https://www.urlregex.com"  
         validURL := govalidator.IsURL(str)  
         fmt.Printf("%s is a valid URL : %v \n", str, validURL)  
 }

```

## Objective-C

```

(http|https)://((\\w)*|([0-9]*)|([-|_])*)+([\\.|/]((\\w)*|([0-9]*)|([-|_])*))+
```

## Swift

```
((?:http|https)://)?(?:www\\.)?[\\w\\d\\-_]+\\.\\w{2,3}(\\.\\w{2})?(/(?<=/)(?:[\\w\\d\\-./_]+)?)?
```

Use it in a function:

```
func canOpenURL(string: String?) -> Bool {
    let regEx = "((https|http)://)((\\w|-)+)(([.]|[/])((\\w|-)+))+"
    let predicate = NSPredicate(format:"SELF MATCHES %@", argumentArray:[regEx])
    return predicate.evaluateWithObject(string)
}
```

Usage:

```
if canOpenURL("https://www.urlregex.com") {
    print("valid url.")
} else {
    print("invalid url.")
}
```

<iframe id="aswift_2" style="height: 1px !important; max-height: 1px !important; max-width: 1px !important; width: 1px !important;"><iframe id="google_ads_frame2"></iframe>

## Swift (use [canOpenURL](https://developer.apple.com/reference/uikit/uiapplication/1622952-canopenurl))

```
UIApplication.sharedApplication().canOpenURL(urlString)
```

## Java

```
^(https?|ftp|file)://[-a-zA-Z0-9+&@#/%?=~_|!:,.;]*[-a-zA-Z0-9+&@#/%=~_|]
```

## VB.NET

```
(http(s)?://)?([\w-]+\.)+[\w-]+[.com]+(/[/?%&=]*)?
```

## C#

```
^(ht|f)tp(s?)\:\/\/[0-9a-zA-Z]([-.\w]*[0-9a-zA-Z])*(:(0-9)*)*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&%\$#_]*)?$
```

## MySQL

```
SELECT field FROM table 
WHERE field 
REGEXP "^(https?://|www\\.)[\.A-Za-z0-9\-]+\\.[a-zA-Z]{2,4}
```

---

# URL

---

```
https**?**:\/\/**(**www\.**)****?**_[-a-zA-Z0-9@:%._**\+**~#=]_**{1,256}**\._[a-zA-Z0-9()]_**{1,6}****\b****(**_[-a-zA-Z0-9()!@:%_**\+**.~#?&**\/****\/**=]_*******)**
```

<iframe src="https://embed.ihateregex.io/make/aHR0cHMlM0YlM0ElNUMlNUMlMkYlNUMlNUMlMkYod3d3JTVDJTVDLiklM0YlNUItYS16QS1aMC05JTQwJTNBJTI1Ll8lNUMlNUMlMkJ-JTIzJTNEJTVEJTdCMSUyQzI1NiU3RCU1QyU1Qy4lNUJhLXpBLVowLTkoKSU1RCU3QjElMkM2JTdEJTVDJTVDYiglNUItYS16QS1aMC05KCkhJTQwJTNBJTI1XyU1QyU1QyUyQi5-JTIzJTNGJTI2JTVDJTVDJTJGJTVDJTVDJTJGJTNEJTVEKik" height="550" style="width:100%" frameborder="0" />

## This Regex Validates a Url Which Should Include **http** or **https**

Cheatsheet

| expr | usage |
| --- | --- |
| `/[a-zA-Z0-9]/` | matches all lowercase, uppercase letters and numbers |
| `/(hello){4}/` | matches "hellohellohellohello" |
| `/^/` | matches beginning of a line |
| `/$/` | matches end of a line |

---


# For URL RegEx Try:

---

```vbnet
((?:https?:\/\/)?(?:www\.)?facebook\.com\/[\w.]*)(?=[^w.])(?!.*\1)
```

It's your regex (somewhat simplified) with a negative look ahead added to make sure the URL isn't repeated later in the text. This means that **only the last match** is kept in the list.

```vbnet
((?:https?:\/\/)?(?:www\.)?facebook\.com\/[\w.]*)
```

[See it here,](https://regexr.com/45h54)

[This will explain it for you graphically.](https://regexper.com/#%28%28%3F%3Ahttps%3F%3A%5C%2F%5C%2F%29%3F%28%3F%3Awww%5C.%29%3Ffacebook%5C.com%5C%2F%5B%5Cw.%5D*%29%28%3F%3D%5B%5Ew.%5D%29%28%3F!.*%5C1%29).

Explanation lite:

`(:?`... `)` makes a non captured group. `?` makes the character or group preceding it optional. `(?=[^w.])` - a positive look ahead is to make sure the whole URL is matched (followed by something NOT a word character or a dot). `(?!.*\1)` is a negative look ahead making sure capture group (the URL part captured between the `()`), preceded by anything (`.*`), doesn't repeat.


---