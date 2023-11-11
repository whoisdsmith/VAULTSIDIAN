# Regex Snippets

# Overview

* [Linux command outputs](#linux)

  * [ls -l output](#ls--l-output)

  * [cat /etc/passwd](#cat-etcpasswd-output)

* [Security](#security)

  * [Shellcode](#shellcode)

  * [Leaked email and password](#leaked-email-and-password)

* [Hashes](#hashes)

  * [MD5](#md5)

  * [Drupal 7 (old)](#drupal-7-old)

* [Encodings](#encodings)

  * [Base64](#base64)

* [Filesharing](#filesharing)

  * [TV-Shows](#tv-shows)

* [General stuff](#general-stuff)

  * [Email](#email)

  * [URLs](#urls)

  * [MAC-Address](#mac-address)

  * [User-Agent](#user-agent)

  * [Version number](#version-number)

  * [IMDb Movie info](#imdb-movie-info)

---
<br>

# Linux

## `ls -l` Output

The pattern below matches the following match groups:

1. Type of element: File, directory, symlink, named pipe, socket, block device or door.
2. Permission
3. Number of nodes (?)
4. User
5. Group
6. Filesize
7. Month (3 chars)
8. Day
9. Year (or in some cases a time in the format HH:MM)
10. Filename

(This pattern can also be used for FTP server listings)

### Pattern

```
([-|d|l|p|s|b|D])([-|r|w|x|s|t]{9})\s+?(\d+?)\s+?(\w+)\s+(\w+)\s+?(\d+)\s+?(\w{3})\s+(\d+)\s+?(\d{4}|\d{2}\:\d{2})\s(.*)
```

### Example

This version supports the `ls -l` and `ls -lh` command: <https://regex101.com/r/cN5gG2/2>

---
<br>

## `cat /etc/passwd` Output

The following groups are matched:

1. Username
2. Password (Encrypted password or `x` if it's stored in the shadow file)
3. User ID (UID)
4. Group ID (GID)
5. User ID Info
6. Home directory
7. Command/Shell

### Pattern

```
(.+)\:(.+?)\:(\d+)\:(\d+)\:(.*?)\:(.*?)\:(.*)
```

### Example

<https://regex101.com/r/dK9pG0/1>

---
<br>

# Security

## Shellcode

Finds shellcode, it's not used to match a complete shellcode buffer  
but instead to check if there is shellcode in a document.

### Pattern

```
((?:\\x[a-fA-F0-9]{2})+)
```

### Example

<https://regex101.com/r/kU7cZ8/1>

---
<br>

## Leaked Email and Password

Finds email and password combinations.  
The following matchgroups are matched:

1. Email
2. Password

### Pattern

```
([\w\.\?\+\-\^\{\}]+\@[\w\.\?\+\-\^]+\.[a-zA-Z]{2,4})(?:[\:\,\.\|\;\t]|\ {1,4})([^\r\n]+)
```

### Example

<https://regex101.com/r/zW7aT8/1>

---
<br>

# Hashes

## MD5

Checks for hexadecimal values which must be 32 chars long.

### Pattern

```
[a-fA-F0-9]{32}
```

### Example

<https://regex101.com/r/tU4fA1/1>

---
<br>

## Drupal 7 (old)

Matches old Drupal 7 password hashes.  
The following groups are matched:

1. Hash type (always "$S$")
2. Number of log2 rounds (X) based on the position of the char in this list  
   './0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz', example "D" -> 15
3. Salt
4. SHA512 hash using 2^X rounds

(Source of the parts of the hash from  [stackoverflow](http://stackoverflow.com/questions/5031662/what-is-drupals-default-password-encryption-method#answer-19274472)

### Pattern

```
(\$S\$)([0-9A-Za-z\.\/])([0-9A-Za-z\.\/]{8})([0-9A-Za-z\.\/]{43})
```

### Example

<https://regex101.com/r/zA9zK8/1>

---
<br>

# Encodings

## Base64

Searches for base64 encoded data.

### Pattern

```
((?:[a-zA-Z0-9\+\/]{4}){4,}(?:[a-zA-Z0-9\+\/]{0,3}\={1,3})?)
```

### Example

<https://regex101.com/r/vS8wI0/1>

---
<br>

# Filesharing

## TV-Shows

Matches the following groups:

1. Name
2. Season
3. Episode
4. Quality (if it exists, e.g. 720p, 1080p, ..)
5. Mixed stuff (if it exists. Might contain the quality, file encoding etc.)
6. Groupname
7. Packager (if it exists [xyz])
8. Fileextension

### Patterns

Version 1: Less restrictive

```
(.+)(?:[Ss _\.](\d{2,})[Ee _\.](\d{2,}))[\. _](\d{3,4}p)?(.+)?.*?\-(.+?)(?:\[(.+)\])?\.(\w+)
```

Version 2: Restrictive

```
([a-zA-Z0-9\.\- ]+)[\. _](?:[Ss](\d{2,})[Ee](\d{2,}))[\. _](\d{3,4}p)?(.+)\-([a-zA-Z0-9]+)(?:\[(.+)\])?\.(mkv|mp4|avi)
```

### Examples

Version 1: <https://regex101.com/r/eO0lY8/4>

Version 2: <https://regex101.com/r/eO0lY8/3>

---
<br>

# General Stuff

## Email

Matches the following groups:

1. Username
2. Domain

### Pattern

```
([a-zA-Z0-9_\-\.]+)\@(.+\..{2,})
```

### Example

<https://regex101.com/r/kR6yE2/1>

---
<br>

## URLs

Matches the following groups:

1. Scheme (http, https, …)
2. Domain
3. Path (if any)
4. GET-Arguments (if any)
5. Fragment (if any)

### Pattern

```
(\w{3,})\:\/\/(?:(.+?)(\/.+)?(\?.+)(\#.+)|(.+?)(\/.+)(\?.+)|(.+?)(\/.+)(\#.+)|(.+?)(\/.+)|[^\s\/\#\?]+)
```

### Example

<https://regex101.com/r/cL5kR3/7>

---
<br>

## MAC-Address

Matches each value of a MAC-Address.

The matched formats are:  
`MM:MM:MM:SS:SS:SS`, `MM-MM-MM-SS-SS-SS` and `MMMM.MMSS.SSSS`

### Pattern

```
(?<![a-fA-F0-9])(?:([a-fA-F0-9]{2})[\:\-]([a-fA-F0-9]{2})[\:\-]([a-fA-F0-9]{2})[\:\-]([a-fA-F0-9]{2})[\:\-]([a-fA-F0-9]{2})[\:\-]([a-fA-F0-9]{2})|([a-fA-F0-9]{4})\.([a-fA-F0-9]{4})\.([a-fA-F0-9]{4}))(?![a-fA-F0-9])
```

### Example

<https://regex101.com/r/lF5pJ4/2>

---
<br>

## User-Agent

Matches various parts of the user-agent.

**some/many user-agents arent matched yet - working on a better version**

### Pattern

```regex
([\w]+?\/(?:\d+?\.?)+?)\ ?\((.+?)\)\ ?([\w]+?\/(?:\d+?\.?)+?)\ (?:([\w]+?\/(?:\d+?\.?)+?[^\w])|\(([\w\d ;,:\.\-]+?)\)\ ([\w\d\.]+\/[\w\d\.]+)(?:\ ([\w\d\.\]+[\/[\w\d\.]+[^\w]))?)
```

### Example

<https://regex101.com/r/cZ9fM7/3>

---
<br>

## Version Number

Matches common version numbers.

### Pattern

```regex
((?:\d\.?)+(?:\-?\w+(?!\w))?)
```

### Example

<https://regex101.com/r/lH5jW8/1>

---
<br>

## IMDb Movie Info

Matches the following information on imdb movie pages:

1. IMDb Title ID (ttxxxxx)
2. Rating (x/10)
3. Title
4. Duration
5. Genre1*
6. Genre2*
7. Genre3*
8. Release date
9. Poster link
10. Short summary

*Groups 5-7 might not always exist, only when the movie has 3 genres listed those are matched. The same goes for 2 and 1 genres.

### Pattern

```regex
\/title\/(tt\d+)\/.+?itemprop=\"ratingValue\">((?:\d+?\.?)+).+?itemprop="name".+?\>(.+?)&nbsp;.+?\/year\/(\d{4}).+?(\d+?h\s\d+?min|\d+?min|\d+?h)(?:.+?itemprop="genre">(.+?)<\/span.+?itemprop="genre">(.+?)<\/span)?(?:.+?itemprop="genre">(.+?)<\/span)?.+datePublished.+?content="(\d{4}(?:\-\d{2}){2}).+?class="poster".+?src=\"(.+?)\"\sitemprop="image.+?itemprop="description">\s{21}(.+?\.).+?\<\/div>
```

#### Example

<https://regex101.com/r/wU0rQ2/2>

---
<br>
