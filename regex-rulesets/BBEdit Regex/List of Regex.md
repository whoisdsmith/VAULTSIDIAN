# List of Regex

Here is a Regular Expression That Matches Multiple Date and Time Formats:

```
(\d{4}-\d{2}-\d{2}(T|\s)\d{2}:\d{2}:\d{2}(\.\d+)?(\+|-)\d{2}:\d{2})|(\d{4}-\d{2}-\d{2}(T|\s)\d{2}:\d{2}:\d{2}(\.\d+)?Z)|(\d{4}-\d{2}-\d{2}(T|\s)\d{2}:\d{2}:\d{2}(\.\d+)?(\+|-)\d{2}:?\d{2})|(\d{2}/\d{2}/\d{4}\s\d{2}:\d{2}:\d{2}\s(AM|PM))|(\d{2}/\d{2}/\d{4}\s\d{1,2}:\d{2}:\d{2}\s(AM|PM))|(\d{2}/\d{2}/\d{4}\s\d{1,2}:\d{2}\s(AM|PM))|(\d{2}/\d{2}/\d{4}\s\d{2}:\d{2}\s(AM|PM))|(\d{2}/\d{2}/\d{4}\s\d{2}:\d{2}:\d{2})|(\d{2}/\d{2}/\d{4}\s\d{1,2}:\d{2}:\d{2})|(\d{2}/\d{2}/\d{4}\s\d{1,2}:\d{2})|(\d{2}/\d{2}/\d{4}\s\d{2}:\d{2})|(\d{2}/\d{2}/\d{4}\s\d{2}:\d{2}:\d{2}\s(AM|PM))
```

This Regular Expression Matches the Following Date and Time Formats:

- YYYY-MM-DDTHH:MM:SS.sss+HH:MM (with optional fractional seconds and timezone offset)
- YYYY-MM-DDTHH:MM:SS.sssZ (with optional fractional seconds and UTC timezone)
- YYYY-MM-DD HH:MM:SS.sss+HH:MM (with optional fractional seconds and timezone offset)
- MM/DD/YYYY HH:MM:SS AM/PM (with optional leading zeros and 12-hour time format)
- MM/DD/YYYY H:MM:SS AM/PM (with optional leading zeros for hour and 12-hour time format)
- MM/DD/YYYY H:MM AM/PM (with optional leading zeros for hour and 12-hour time format)
- MM/DD/YYYY HH:MM AM/PM (with optional leading zeros for hour and 12-hour time format)

1. Regular expression to match email addresses:

```
[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}
```

1. Regular expression to match phone numbers in US format (XXX) XXX-XXXX:

```
\(\d{3}\)\s\d{3}-\d{4}
```

1. Regular expression to match URLs (starting with http:// or https://):

```
https?://\S+
```

1. Regular expression to match social security numbers in US format (XXX-XX-XXXX):

```
\d{3}-\d{2}-\d{4}
```

1. Regular expression to match credit card numbers in the format of Visa, MasterCard, American Express, and Discover:

```
\b(?:4[0-9]{12}(?:[0-9]{3})?|5[1-5][0-9]{14}|3[47][0-9]{13}|6(?:011|5[0-9][0-9])[0-9]{12})\b
```

1. Regular expression to match IPv4 addresses:

```
\b(?:\d{1,3}\.){3}\d{1,3}\b
```

1. Regular expression to match hexadecimal color codes in HTML/CSS format (#RRGGBB or #RGB):

```
#([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})
```

1. Regular expression to match ZIP codes in US format (XXXXX or XXXXX-XXXX):

```
\b\d{5}(?:-\d{4})?\b
```

1. Regular expression to match dates in the format MM/DD/YYYY:

```
\d{2}\/\d{2}\/\d{4}
```

1. Regular expression to match time in the format HH:MM:SS:

```
\d{2}:\d{2}:\d{2}
```

1. Regular expression to match hashtags in a tweet or social media post:

```
#\w+
```

1. Regular expression to match mentions in a tweet or social media post:

```
@\w+
```

1. Regular expression to match mentions and hashtags in a tweet or social media post:

```
[#@]\w+
```

1. Regular expression to match HTML tags in a string:

```
<([a-z]+)(?:\s+[a-z]+\s*=\s*(?:"[^"]*"|'[^']*'))*\s*/?>
```

1. Regular expression to match XML tags in a string:

```
<([a-z]+)(?:\s+[a-z]+\s*=\s*(?:"[^"]*"|'[^']*'))*\s*/?>
```

1. Regular expression to match Markdown links in a string:

```
\[(.*?)\]\((.*?)\)
```

1. Regular expression to match Markdown images in a string:

```
!\[(.*?)\]\((.*?)\)
```

1. Regular expression to match IP addresses in IPv4 or IPv6 format:

```
(?:\d{1,3}\.){3}\d{1,3}|(?:[a-fA-F0-9]{1,4}:){7}[a-fA-F0-9]{1,4}
```

1. Regular expression to match US dollar amounts with optional decimal places:

```
\$\d+(?:\.\d{2})?
```

1. Regular expression to match social media usernames starting with @:

```
@[\w\d]+
```

1. Regular expression to match repeated characters (e.g. "aaaaa" or "bb"):

```
(.)\1+
```

1. Regular expression to match consecutive numbers (e.g. "123" or "7890"):

```
\d{2,}
```

1. Regular expression to match repeated words (e.g. "hello hello" or "the the"):

```
\b(\w+)\b\s+\1\b
```

1. Regular expression to match HTML-style comments (<!-- … -->):

```
<!--[\s\S]*?-->
```

1. Regular expression to match double-quoted strings in a programming language:

```
"[^"\\]*(?:\\.[^"\\]*)*"
```

1. Regular expression to match single-quoted strings in a programming language:

```
'[^'\\]*(?:\\.[^'\\]*)*'
```

1. Regular expression to match Markdown bold text in a string:

```
\*\*(.*?)\*\*
```

1. Regular expression to match Markdown italic text in a string:

```
\*(.*?)\*
```

1. Regular expression to match Twitter-style mentions with the @ symbol followed by a username:

```
@\w+
```

1. Regular expression to match Twitter-style hashtags with the # symbol followed by a word:

```
#\w+
```

1. Regular expression to match US zip codes in a string:

```
\b\d{5}(?:-\d{4})?\b
```

1. Regular expression to match time in 12-hour format with optional leading zero:

```
(0?[1-9]|1[0-2]):([0-5][0-9])(:[0-5][0-9])?\s*(am|pm)
```

1. Regular expression to match time in 24-hour format with optional leading zero:

```
([01][0-9]|2[0-3]):[0-5][0-9]
```

1. Regular expression to match hexadecimal numbers:

```
0[xX][0-9a-fA-F]+
```

1. Regular expression to match whitespace characters (spaces, tabs, and newlines):

```
\s+
```

1. Regular expression to match ISBN 10 numbers:

```
\b\d{9}[\dX]\b
```

1. Regular expression to match ISBN 13 numbers:

```
\b\d{13}\b
```

1. Regular expression to match MAC addresses in colon-separated format:

```
(?:[0-9a-fA-F]{2}:){5}[0-9a-fA-F]{2}
```

1. Regular expression to match MAC addresses in hyphen-separated format:

```
(?:[0-9a-fA-F]{2}-){5}[0-9a-fA-F]{2}
```

1. Regular expression to match US phone numbers in the format of (XXX)XXX-XXXX:

```
\(\d{3}\)\d{3}-\d{4}
```

1. Regular expression to match US phone numbers in the format of XXX-XXX-XXXX:

```
\d{3}-\d{3}-\d{4}
```

1. Regular expression to match US phone numbers in the format of XXX.XXX.XXXX:

```
\d{3}\.\d{3}\.\d{4}
```

1. Regular expression to match positive integers:

```
\b\d+\b
```

1. Regular expression to match negative integers:

```
\b-\d+\b
```

1. Regular expression to match floating-point numbers with optional decimal places:

```
\b\d+\.\d*\b
```

1. Regular expression to match strings with only letters:

```
^[a-zA-Z]+$
```

1. Regular expression to match strings with only numbers:

```
^[0-9]+$
```

1. Regular expression to match strings with only letters and numbers:

```
^[a-zA-Z0-9]+$
```

1. Regular expression to match strings that start with a letter and may contain letters, numbers, and underscores:

```
^[a-zA-Z][a-zA-Z0-9_]*$
```

1. Regular expression to match HTML tags with optional attributes:

```
<([a-z]+)(\s+[a-z]+\s*=\s*(?:"[^"]*"|'[^']*'))*\s*/?>
```

1. Regular expression to match time in 12-hour format with optional leading zero and meridian abbreviation:

```
(0?[1-9]|1[0-2]):([0-5][0-9])(:[0-5][0-9])?\s*(a|p)m
```

1. Regular expression to match time in 24-hour format with optional leading zero and meridian abbreviation:

```
([01][0-9]|2[0-3]):[0-5][0-9]\s*(a|p)m
```

1. Regular expression to match credit card expiration dates in the format of MM/YY:

```
(0[1-9]|1[0-2])\/\d{2}
```

1. Regular expression to match IPv6 addresses in full format:

```
(?:[a-fA-F0-9]{1,4}:){7}[a-fA-F0-9]{1,4}
```

1. Regular expression to match ISBN 10 and ISBN 13 numbers:

```
\b(?:\d{9}[\dX]|\d{13})\b
```

1. Regular expression to match URLs (starting with http://, https://, or www.):

```
(?:https?://|www\.)\S+
```

1. Regular expression to match strings that contain at least one uppercase letter, lowercase letter, and number:

```
^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).+$
```

1. Regular expression to match US Social Security numbers with or without dashes:

```
\b\d{3}[- ]?\d{2}[- ]?\d{4}\b
```

1. Regular expression to match ISO 8601 date format (YYYY-MM-DD):

```
\d{4}-\d{2}-\d{2}
```

1. Regular expression to match ISO 8601 date and time format (YYYY-MM-DDTHH:MM:SS):

```
\d{4}-\d{2}-\d{2}T\d{2}:\d{2}:\d{2}
```

1. Regular expression to match positive and negative floating-point numbers:

```
[-+]?\d*\.\d+
```

1. Regular expression to match positive and negative integers:

```
[-+]?\d+
```

1. Regular expression to match US state abbreviations:

```
[A-Z]{2}
```

1. Regular expression to match US ZIP codes in the format of XXXXX:

```
\b\d{5}\b
```

1. Regular expression to match UK postcodes in the format of AA1A 1AA or A1A 1AA:

```
\b[A-Z]{1,2}\d{1,2}[A-Z]?\s\d[A-Z]{2}\b
```

Here is a Regular Expression That Matches Strings in the Format of

`YYYY-MM-DD hh:mm:ss AM/PM`:

```
\d{4}-\d{2}-\d{2}\s\d{2}:\d{2}:\d{2}\s(AM|PM)
```

Here is a Regular Expression That Matches Strings in the Format of

`MM/DD/YY*  DD Month YYYY`:

```
\d{2}\/\d{2}\/\d{2}\*\s+\d{2}\s+\w+\s+\d{4}
```

Here is a Regular Expression That Matches Strings in the Format of 

`HH:MM:SS`:

```
\d{2}:\d{2}:\d{2}
```

Lowercase Letters

```
[a-z]
```

Capital Letters

```
[A-Z]
```

Numbers

```
[\d]
```

Lowercase and Uppercase Accented Letters

```
[àèìòùáéíóúâêîôûäëïöüãõ]
```

#Accented Lowercase and Uppercase Letters and Cedilla

```
[\p{Letter}]
```

Cedilla

```
[ç]
```

Accents

```
[`´^~¨]
```

Punctuation Marks

```
[.:,;\-_<>=+*!?)(}{|''""\][\\/]
```

Symbols

```
[@#$%&]
```

Spaces

```
[\s]
```

Line Breaks

```
[\n]
```

Characters Non-unicode

```
(?![ -~ç´¨àèìòùáéíóúâêîôûäëïöüãõ\n]).
```

Character Non-unicode

```
[^\p{Letter}\d`´^~¨.,;\-_<>=+*!?)(}{|'"\]

[\\/@#$%&\s\n]

[a-zA-Z\dàèìòùáéíóúâêîôûäëïöüãõç`´^~¨.:,;\-_<>=+*!?)(}{|'"\][\\/@#$%&\s\n]

[\p{Letter}\d`´^~¨.:,;\-_<>=+*!?)(}{|'"\][\\/@#$%&\s\n]

```

Regex to Remove Space at the End of a Line

```
\s+$
```

Remove Empty Space at the Begining of a Line

```
^\s+
```

Regex to Remove All Non Alphabet and Numbers

```
[^a-zA-Z0-9]
```

Regex to Remove Emojis

```
[\u{1F600}-\u{1F64F}\u{1F300}-\u{1F5FF}\u{1F680}-\u{1F6FF}\u{2600}-\u{26FF}\u{2700}-\u{27BF}]
```

Regex to Replace Double Spaces

```
\s{2,}
```

To find all lines that start with ##, the regular expression would be:

```
^##.*
```

```
^##.*\n
```

Generate a Regular Expression That Adds to the End of Each Document

```
$---$
```

Add a New Line to End of Document with ---

```
\n---$
```

Find End of Document

```
\Z
```
