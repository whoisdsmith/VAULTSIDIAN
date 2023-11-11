# Strip Markdown in BBedit

## Replace Headers

Find: `^#{1,6}\s*(.+)$`  
Replace: `\1`

## Replace Bold and Italic Text

Find: `(\*{1,2}|_{1,2})(.+?)\1`  
Replace: `\2`

## Replace Inline Code

Find: `` `(.+?)` ``  
Replace: `\1`

## Replace Strikethrough

Find: `~~(.+?)~~`  
Replace: `\1`

## Replace Links

Find: `!\[(.*?)\]\((.*?)\)`  
Replace: `\1`

## Replace Images

Find: `!\[(.*?)\]\((.*?)\)`  
Replace: `\1`

## Replace Blockquotes

Find: `^>\s*(.+)$`  
Replace: `\1`

## Replace Ordered and Unordered Lists

Find: `^(\s*[-*+]|(\d+\.))\s+(.+)$`  
Replace: `\3`

## Replace Horizontal Lines

Find: `^-{3,}$`  
Replace: `` (empty string)

## Find Markdown Links, Markdown Images

1. Markdown Links:

```
\[(.+?)\]\((.*?)\)
```

1. Markdown Images:

```
!\[(.+?)\]\((.*?)\)
```

## Find a String That Matches Everything After URL: for Example

URL: Optional("https://www.facebook.com/photo.php?fbid=1293627213652&set=a.1292272819793.2042826.1019447865&type=1")

```
URL:\s*(.*)
```

## Find a String That Matches Everything After Journal: Heres an Example

Journal: diary

```
Journal:\s*(.*)
```

## Find Files

.md extensions

```
^.+\.md$
```

## Find Date and or Time Strings

1. Matches date in the format YYYY-MM-DD:

```
\d{4}-\d{2}-\d{2}
```

1. Matches time in the format HH:MM:SS (24-hour clock):

```
\d{2}:\d{2}:\d{2}
```

1. Matches date and time in the format YYYY-MM-DD HH:MM:SS (24-hour clock):

```
\d{4}-\d{2}-\d{2}\s+\d{2}:\d{2}:\d{2}
```

1. Matches date in various formats (e.g., MM/DD/YYYY, DD/MM/YYYY, YYYY/MM/DD, etc.):

```
\d{1,2}[/-]\d{1,2}[/-]\d{4}
```

1. Matches time in various formats (e.g., 12-hour clock with AM/PM, 24-hour clock, etc.):

```
\d{1,2}:\d{2}(:\d{2})?( )?[apAP][mM]|\d{2}:\d{2}(:\d{2})?
```

## Find Only Dates That Have a /

Here's a regular expression that matches dates with a forward slash (/) separator:

```
\d{1,2}/\d{1,2}/\d{4}
```

## Find a String That Matches

Feed: and everything after

```
Feed:\s*(.*)
```

## Find Everything Between

[[]]

```
\[\[(.*?)\]\]
```

## Find Files Inside

[[]]]

```
\[\[\[(.*?)\]\]\]
```

```
\[\[(.*?)\]\]
```

## The Regular Expression to Match

`![]()`

```
!\[\]()
```

Note that if you want to capture the source URL of the image, you can modify the regex to include a capturing group:

```
!\[\]\((.+)\)
```

## Generate a Regex to Match for

(>)

```
\(>\)
```

Note that if you want to capture the greater-than sign, you can remove the parentheses around it:

```
\>
```

## Regex for Indented Lines

```
^\s{4}.+
```

## Regex to Match First 2 Lines of File That Stars with

Date:

```
^Date:.*\nDate:.*
```

```
^# Date:.*"2023"
```

## Regex to Replace First Line of File with Filename

Find: `^.*`

Replace: `filename`

```
sed -i '1s/^.*$/filename/' file.txt
```

## String to Extract Full Content Featuring

**Everett Smith**

```
.*\bEverett Smith\b.*
```
