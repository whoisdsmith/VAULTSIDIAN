# Regex Generator for Text

## Generate a Regular Expression That Matches Similar Lines Such as

3:27 PM https://www.flickr.com/photos/133795233@N02/18245684450  
3:27 PM https://www.flickr.com/photos/133795233@N02/18429192412  

```
\d{1,2}:\d{2} [AP]M https:\/\/www\.flickr\.com\/photos\/\d+\/\d+
```

```
\d{1,2}:\d{2} [AP]M https:\/\/www\.flickr\.com\/photos\/\d+\/\d+\b
```

## Match Similar Urls Like

https://www.flickr.com/photos/133795233@N02/18429192412

```
https:\/\/www\.flickr\.com\/photos\/\d+@?[a-zA-Z\d]*\/\d+
```

## Match Social Urls

```
(?:https?:\/\/)?(?:www\.)?(?:(?:twitter|instagram|facebook|linkedin|youtube)\.com|tiktok\.com)\/[\w\d]+(?:\/[\w\d]+)*\/?
```

## Find All Mobile Urls

```
\bhttps?:\/\/m\.[\w.\/?&=-]+\b
```

## Find Similar Urls Like

https://www.facebook.com/photo.php?fbid=2134221387981&set=a.2131841728491.2116882.1019447865&type=1

```
https?:\/\/www\.facebook\.com\/(?:.+\/)?(?:photos|videos)\/\d+\/?(?:[?&][\w-]+=[\w-]+)*
```

```
https?:\/\/www\.facebook\.com\/(?:.+\/)?(?:photos|videos)\/\d+\/?(?:[?&][\w-]+=[\w-]*)*
```

## Find Similar Lines Like

3:28 PM 3:42 PM 3:42 PM 3:43 PM 3:43 PM 6:41 PM 6:41 PM 6:41 PM # 2014-09-16  
3:40 PM

```
^(?:\d{1,2}:\d{2} [AP]M )+\d{1,2}:\d{2} [AP]M # \d{4}-\d{2}-\d{2}$
```

## Find Similar Lines 7:06 PM Flickr Photo: IMG_4693

```
^\d{1,2}:\d{2} [AP]M Flickr Photo: [A-Z0-9_]+$
```

## Find Similar Lines

10:59 AM 3:40 PM 3:40 PM 4:46 PM 4:46 PM 10:19 AM 10:20 AM 12:16 PM 12:16 PM 12:22 PM 12:22 PM 2:23 PM 2:24 PM 3:46 PM 4:28 PM 4:28 PM 4:28 PM 4:28 PM 4:28 PM 4:28 PM 4:28 PM 4:28 PM 4:28 PM 4:29 PM 4:29 PM 4:29 PM 4:29 PM 4:29 PM 4:30 PM 4:35 PM Flickr Photo: IMG_4100  
4:35 PM 4:36 PM 4:36 PM Flickr Photo: IMG_4102

```
^(?:\d{1,2}:\d{2} [AP]M )+\d{1,2}:\d{2} [AP]M Flickr Photo: [A-Z0-9_]+$
```

## Find Similar IMG_3908

```
\bIMG_\d+\b
```

## Find Similar Lines Like

2014-11-26.txt

```
^\d{4}-\d{2}-\d{2}\.txt$
```

## Find Similar Lines Like

\# 2014.11.15 - 15 November 2014

```
^# \d{4}\.\d{2}\.\d{2} - \d{1,2} [a-zA-Z]+ \d{4}$
```

## Regex Generator Txt Pattern

find all lines with .txt in it

```
.*\.txt$
```

## Match Lines That Start Something Like This

\# Date: -05-22, 2022 at 4:03 PM

```
^#\sDate:\s-\d{2}-\d{2},\s\d{4}\sat\s\d{1,2}:\d{2}\s(?:AM|PM)
```

## Match Lines That Start Something Like This

\# Date: 5/22/22, 4:03:43 PM

```
^#\sDate:\s\d{1,2}/\d{1,2}/\d{2},\s\d{1,2}:\d{2}:\d{2}\s(?:AM|PM)
```

## Regex for Non-ASCII

non ASCII characters

[^\x00-\x7F]

non utf-8 characters

(?![\x00-\x7F])[^\x00-\xFF]

## Find Corrupted Characters Regex

```
(?:[\x00-\x1F\x7F-\x9F\u2028\u2029\uFFF9-\uFFFD]|[\uD800-\uDBFF][\uDC00-\uDFFF])
```

## Regex Generator Request

Date: 4/25/22, 12:59:06 PM  
Journal: project-audio  
Topic: may-4-2019.md

```
/\bDate: \d{1,2}\/\d{1,2}\/\d{2}, \d{1,2}:\d{2}:\d{2} [AP]M\nJournal: [a-z0-9_-]+\nTopic: [\w-]+\.md\b/
```

## Regex Ex to Match at Beginning of Document

```
/^.*/
```

## Regex to Match 1st 3 Lines of Document

```
/^(.*\n){0,2}.*$/
```

```
^(.*[\r\n]){0,2}.*[\r\n]
```

```
/^(.*[\r\n]){0,2}.*$/s
```

## I Have Multiple Files That Start with the Same 3 Lines

Date:  
Journal:  
Topic:

what is the regex string to remove these?

You can use the following regex to remove the first three lines of each file:

```
^Date:.*\nJournal:.*\nTopic:.*\n
```

## Regex to Remove Formatting From Txt File

```
<[^>]*>
```

## Regex to Strip Markdown in BBedit

Find: `(?s)^#+\h+(.*)$|(?m)^[*-]\h+(.*)$|(?m)^>\h+(.*)$|(?m)^```\h*\n([\s\S]*?)^```$|\[(.*?)\]\((.*?)\)|\*\*(.*?)\*\*|__(.*?)__|\*(.*?)\*|_(.*?)_|~~(.*?)~~|\n{2,}```[\s\S]*?```|\n{2,}|\s*$`

Replace:

```
\1\2\3\4\5\6\7\8\9\10\11
```
