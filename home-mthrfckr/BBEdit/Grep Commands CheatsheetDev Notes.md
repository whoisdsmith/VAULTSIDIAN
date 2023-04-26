# Grep Commands Cheatsheet | Dev Notes

---

Grep is a handy command-line utility that enables you to search text or files.

More formally: Grep (Global Regular Expression Print) is a utility for searching plain-text datasets for lines that match a given regular expression.

Grep was developed for Unix, but is now available for all unix-like systems (e.g. Linux).

## Basic Command Syntax

```
# Output all lines that contain 'target string' in filename.log
grep 'target string' /var/log/filename.log

# Output all lines that contain 'target string' in multiple files
grep 'target string' filename1 filename2 filename3
```

## Ignore Case

Use `-i`:

```
# Return lines containing 'David', 'david', 'DAVID' etc
grep -i 'david' /var/log/auth.log
```

## Recursive Search

Use `-r`:

```
# Search all apache log files for example.com/about
grep -r "example.com/about" /var/log/apache2

# Sample Output:
/var/log/apache2/example.com.access.log.1:88.87.168.109 - - [12/Oct/2016:21:33:16 +0100] "GET /uploads/2015/08/example.jpg HTTP/1.1" 200 628726 "http://example.com/about/" "Mozilla/5.0 (Linux; Android 6.0.1; SM-G920F Build/MMB29K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/53.0.2785.124 Mobile Safari/537.36"
```

To suppress the filename. use the `-h` option. This example shows suppressed filenames and sends the result output to a file:

```
grep -h -r "example.com/about" /var/log/apache2 > ~/about-log
```

## Search for Whole Words

Grep will return lines that contain the target string - it may be a fragment of another string. To return only lines containing the target string as a distinct word, use the `-w` option:

```
# Return lines containing 'example' as a distinct word
grep -w 'example' /var/log/logfile.log
```

Search for many words requires `egrep` (extended grep), or escaping the pipe character:

```
# Returns lines that contain either specified word using egrep
egrep -w "david|elaine" /var/log/auth.log

# Same:
grep -w "david\|elaine" /var/log/auth.log

# Recursively search apache logs for either specified string:
egrep -Rwi --color 'example.com/about|example.com/contact' /var/log/apache2
```

## References

-   [Grep Definition](https://en.wikipedia.org/wiki/Grep)
-   [http://www.cyberciti.biz/faq/searching-multiple-words-string-using-grep/](http://www.cyberciti.biz/faq/searching-multiple-words-string-using-grep/)
-   [https://www.howtoforge.com/tutorial/linux-grep-command/](https://www.howtoforge.com/tutorial/linux-grep-command/)
