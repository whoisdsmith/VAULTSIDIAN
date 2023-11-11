# Text Processing Tools

---

## Overview

-   [Tools for Extracting Text](https://miteshshah.github.io/linux/basics/text-processing-tools/#tools-for-extracting-text)
    -   [1\. Viewing File Contents](https://miteshshah.github.io/linux/basics/text-processing-tools/#1-viewing-file-contents)
        -   [cat command](https://miteshshah.github.io/linux/basics/text-processing-tools/#cat-command)
        -   [less command](https://miteshshah.github.io/linux/basics/text-processing-tools/#less-command)
    -   [2\. Viewing File Excerpts](https://miteshshah.github.io/linux/basics/text-processing-tools/#2-viewing-file-excerpts)
        -   [head command](https://miteshshah.github.io/linux/basics/text-processing-tools/#head-command)
        -   [tail command](https://miteshshah.github.io/linux/basics/text-processing-tools/#tail-command)
    -   [3\. Extracting Text by Keyword - grep command](https://miteshshah.github.io/linux/basics/text-processing-tools/#3-extracting-text-by-keyword---grep-command)
    -   [4\. Extract by Column or Field - cut command](https://miteshshah.github.io/linux/basics/text-processing-tools/#4-extract-by-column-or-field---cut-command)
-   [Tools for Analyzing Text](https://miteshshah.github.io/linux/basics/text-processing-tools/#tools-for-analyzing-text)
    -   [wc command](https://miteshshah.github.io/linux/basics/text-processing-tools/#wc-command)
    -   [sort command](https://miteshshah.github.io/linux/basics/text-processing-tools/#sort-command)
    -   [diff command](https://miteshshah.github.io/linux/basics/text-processing-tools/#diff-command)
    -   [aspell command](https://miteshshah.github.io/linux/basics/text-processing-tools/#aspell-command)
-   [Tools for Manipulating Text](https://miteshshah.github.io/linux/basics/text-processing-tools/#tools-for-manipulating-text)
    -   [tr command](https://miteshshah.github.io/linux/basics/text-processing-tools/#tr-command)
    -   [sed command](https://miteshshah.github.io/linux/basics/text-processing-tools/#sed-command)
    -   [regex command](https://miteshshah.github.io/linux/basics/text-processing-tools/#regex-command)

1.  File Contents: `cat` and `less`
2.  File Excerpts: `head` and `tail`
3.  Extract by Keyword: `grep`
4.  Extract by Column or Field: `cut`

### 1\. Viewing File Contents

#### Cat Command

-   `cat` - Dump one or more file to STDOUT
-   `cat` command is most useful for viewing the short files
-   Multiple files are concatenated together

**OPTIONS:**

-   `-A` Show all characters, including control characters and non-printing characters
-   `-s` Squeeze (multiple adjacent blank lines into a single black line)
-   `-b` Number each (non-blank) line of output

**NOTE!:** If you dump the content of a binary file with cat to a terminal, you will make it unusable. You can use reset command to clean up your garbled terminal and go on with it.  
When you type `reset`, it won’t be correctly echo-ed.

#### Less Command

-   `less` View file or STDIN one page at a time.
-   `less` command is more useful for viewing the larger files.

**Navigating Text with less**

-   `Space` Moves ahead one full screen
-   `b` Moves back one full screen
    
-   `Enter` Moves ahead one line
-   `k` Moves back one line
    
-   `g` Moves to the top of the file
-   `G` Moves to the bottom of the file
    
-   `/text` Searches for text
-   `n` Repeats the last search
-   `N` Repeats the last search, but in the opposite direction
    
-   `v` Opens the file in (vi by default)
-   `q` quits

### 2\. Viewing File Excerpts

#### Head Command

-   `head`: Display the first 10 lines of a file
-   `-n`: Specify the number of lines to display

**Examples:**

```
[mitesh@Matrix ~]$ head /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
uucp:x:10:14:uucp:/var/spool/uucp:/sbin/nologin

[mitesh@Matrix ~]$ head -n 2 /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
```

#### Tail Command

-   `tail`: Display the last 10 lines of a file
-   `-n`: Specify the number of lines to display
-   `-f`: Follow subsequent additions to the file
    -   Continue to display the file in REAL TIME
    -   Very useful for monitoring log files!
    -   System Administrators use this feature to keep an eye on the system log.

**Examples:**

```
[root@Matrix ~]# tail -n 2 /var/log/messages
[root@Matrix ~]# tail -f /var/log/messages
```

### 3\. Extracting Text by Keyword - Grep Command

-   `grep`: Prints lines of files or STDIN where the pattern is matched
-   The patterns contain regular expression metacharacters and so it is considered good practice to always quote your regular expressions.

**Options:**

-   `-i`: Search case insensitively
-   `-n`: Print line numbers of matches
-   `-v`: Print lines that does not contain the pattern
    
-   `-Ax`: Include x lines after each match
-   `-Bx`: Include x lines before each match
    
-   `-r`: Recursively search a directory
-   `-c`: Counts the number of lines where the pattern matched
-   `-l`: Only return the name of the file that have at least one line containing the pattern
    
-   `--color=auto`: Highlight the match in color

**Examples:**

```
[mitesh@Matrix ~]$ grep 'bash' /etc/passwd
root:x:0:0:root:/root:/bin/bash
neo:x:500:500:Neo:/home/neo:/bin/bash
mitesh:x:501:501:mitesh:/home/mitesh:/bin/bash

[mitesh@Matrix ~]$ grep '[Cc]at' pets
cat
Cat

[mitesh@Matrix ~]$ ps ax | grep 'init'
1 ?        Ss     0:01 /sbin/init
2701 pts/1    S+     0:00 grep init

[mitesh@Matrix ~]$ date --help | grep 'year'
```

### 4\. Extract by Column or Field - Cut Command

-   `cut`: Display specific columns of file or STDIN

**Options:**

-   `-d`: Specify the column delimiter (Default is TAB)
-   `-f`: Specify the column to print
-   `-c`: Cut by characters

**Examples:**

```
# Display the list of users from /etc/passwd
[mitesh@Matrix ~]$ cut -d: -f1 /etc/passwd
root
bin
...output truncated...

# Display the Login Shell of root user
[mitesh@Matrix ~]$ grep 'root' /etc/passwd | cut -d: -f7
/bin/bash

# Display the list of UID from /etc/passwd
[mitesh@Matrix ~]$ cut -f3 -d: /etc/passwd
0
1
...output truncated...

# Cut by characters
[mitesh@Matrix ~]$ cut -c2-5 /usr/share/dict/words

# System's IP Address
[mitesh@Matrix ~]$ ifconfig | grep 'inet addr' | cut -d: -f2 | cut -d' ' -f1
127.0.0.1
```

## Tools for Analyzing Text

1.  Text Stats: `wc`
2.  Sorting Text: `sort`
3.  Comparing Files: `diff` and `patch`
4.  Spell Check: `aspell`

### Wc Command

-   `wc` command counts the Number of Lines, Words, Bytes and/or Characters in a File or STDIN.
-   On traditional UNIX system every character in a text file took up exactly 1 byte.
-   However, with the advent of internationalization and larger character sets like Unicode some characters can take up to 4 bytes.

**Options:**

-   `-l`: Only for line count
-   `-w`: Only for word count
-   `-c`: Only for byte and/or chatacter count
-   `-m`: Get an accurate charcter count

**Examples:**

```
[mitesh@Matrix ~]$ wc story.txt
39  237  1901 story.txt

[mitesh@Matrix ~]$ wc .bash*
66  264 1533 .bash_history
2    2   18 .bash_logout
12   27  176 .bash_profile
8   21  124 .bashrc
88  314 1851 total

[mitesh@Matrix ~]$ ls /tmp | wc -l
18
```

### Sort Command

-   `sort` - Sorts Text to STDOUT - Original File Unchanged

**Syntax:**

```
sort [OPTION]... [FILE]...
```

**Options:**

-   `-r`: Perform a Reverse (Descending) sort
-   `-n`: Perform a Numerical sort
    
-   `-f`: Ignore (Folds) case of character in string
-   `-u`: Unique (Remove duplicate lines in output)
    
-   `-t`: Specify the column delimiter
-   `-k`: Specify the column to print

**Examples:**

```
[mitesh@Matrix ~]$ grep 'bash' /etc/passwd | sort
neo:x:500:500:Neo:/home/neo:/bin/bash
root:x:0:0:root:/root:/bin/bash
mitesh:x:501:501:mitesh:/home/mitesh:/bin/bash

# Display the list of sorted UID from /etc/passwd
[mitesh@Matrix ~]$ sort -t : -k 3 -n /etc/passwd
[mitesh@Matrix ~]$ sort -t : -k 3.2 -n /etc/passwd
```

**NOTE!:** The argument to the `-k` option can be two numbers separated by a dot. In this case, The number before the dot is the field number  
The number after the dot is the character within that field with which to begin sort

**Eliminating Duplicate Lines**

-   `sort-u`: Removes duplicate lines from input
-   `uniq`: Removes duplicate adjacent lines from input To print only unique line occurrences in a file (Remove all duplicate lines), input to uniq must be first sorted.

**Options:**

-   `-c`: Produce a frequency listing - count no of occurrences. Each line will be prepended with a number indicating how many times it appears in the input
    
-   `-d`: Print one copy of the lines that are repeated in the input.
-   `-u`: Output only the lines that are truely unique - only occurring once in the input.
    
-   `-fn`: Avoid comparing the first n fields in each line.
-   `-sn`: Avoid comparing the first n characters in each line.

**Examples:**

```
# Use with sort for best result
[mitesh@Matrix ~]$ sort userlist.txt | uniq -c

[mitesh@Matrix ~]$ cut -d: -f7 /etc/passwd | sort | uniq -c
3 /bin/bash
1 /bin/sync
1 /sbin/halt
32 /sbin/nologin
1 /sbin/shutdown
```

### Diff Command

-   `diff`: Compare two files for difference.
-   Use `gvimdiff` for graphical diff - Provided by vim-X11 package.

**Examples:**

```
# Denotes a difference (change) on line 5
[mitesh@Matrix ~]$ diff foo.conf-broken foo.conf-works
5c5
< use_widgets = no
---
> use_widgets = yes
```

-   Suppose a service on station1 is malfunctioning but the same service works on station2.
-   Thanks to `diff` and the use of simple, text-based configuration files,
-   We can easily compare the working and non-working configurations.

```
[mitesh@Matrix ~]$ cat file.conf-station1
Hostname = station1
Setting1 = a
Setting3 = C
Setting4 = D

[mitesh@Matrix ~]$ cat file.conf-station2
Hostname = station2
Setting1 = A
Setting2 = B
Setting3 = C


[mitesh@Matrix ~]$ diff file.conf-station1 file.conf-station2
1,2c1,3
< Hostname = station1
< Setting1 = a
---
> Hostname = station2
> Setting1 = A
> Setting2 = B
4d4
< Setting4 = D
```

**Duplicating File Changes**

-   `diff-u`: Unified Diff (An alternate way of displaying the same information), Best for patch utility.
-   `patch`: Duplicate changes in other files (use with care!)

**Options:**

-   `-b`: Automatically backup changed files.

**Examples:**

```
[mitesh@Matrix ~]$ diff -u file.conf-station1 file.conf-station2
--- file.conf-station12011-08-22 12:22:37.648426983 +0530
+++ file.conf-station22011-08-22 12:23:36.775147621 +0530
@@ -1,4 +1,4 @@
-Hostname = station1
-Setting1 = a
+Hostname = station2
+Setting1 = A
+Setting2 = B
Setting3 = C
-Setting4 = D
```

-   To use `patch`, simply store the output of a `diff -u` in a file;
-   And run the following command, which would make file.conf-station1 looks like file.conf-station2

```
[mitesh@Matrix ~]$ diff -u file.conf-station1 file.conf-station2 > file.conf.patch
```

**Beware!:**

-   Do you actually want all of the changes above to be made?
-   It would be advisable to first edit `file.conf.patch`
-   And remove the two lines describing the Hostname variable, since those should remain different between systems.
-   If anything terrible happens, `patch -b` automatically creates a backup of each file it changes.
-   backups are given the `.orig` extension.

```
[mitesh@Matrix ~]$ patch -b file.conf-station1 file.conf.patch
```

### Aspell Command

-   `aspell`: A aspell is an interactive spell checker.
-   It offers suggestions for corrections via a simple menu-driven interface.

```
[mitesh@Matrix ~]$ aspell check file.txt
Some times *peple* type stuff wrong.
1) people6) peel
2) Pele7) Pelee
3) Peale8) peopled
4) purple9) peoples
5) Peel0) pep
i) IgnoreI) Ignore all
r) ReplaceR) Replace all
a) Addx) Exit
?

# A aspell list will non-interactively list the misspelled words in a file read from STDIN.
[mitesh@Matrix ~]$ aspell list < standfast.txt
Carcrashes
Braincheck
Morningcharm

# A quick spelling dictionary look-up can be performed with the look command.
[mitesh@Matrix ~]$ look exer
exerce
exercent
exercisable
exercise
exercised
exerciser
exercisers
exercises
exercising
...output truncated...
```

## Tools for Manipulating Text

### Tr Command

-   `tr`: Translate (Alter) Characters.
-   Only reads data from STDIN.
-   Converts characters in one set to corresponding characters in another set.

```
[mitesh@Matrix ~]$ tr 'a-z' 'A-Z' < lowercase.txt

# This command is commonly used in shell scripts to ensure that data is in an expected case
echo -n "Enter yes or no: "
read answer
answer="$(echo $answer | tr 'A-Z' 'a-z')"
```

### Sed Command

-   `sed`: Stream Editor
-   Performs search/replace operations on a stream of data
-   As with grep, it is considered good practice to always quote sed’s search/replace string
    
-   By Default: sed make maximum one change per line
-   If you want make multiple changes per line then append `g` (Globle) at the end of search/replace pattern.
    
-   sed searches are case-sensitive
-   If you want to search case-insensitively then append `i` (case insensitive) to the pattern.
    
-   sed operates on all the lines of the file.
-   It is possible to provide sed with address limiting.
    
-   Normally does not alter the source file
-   use `-i.bak` to backup and alter the source file

**Examples:**

```
[mitesh@Matrix ~]$ cat pets
cat cat cat Cat CAT
cat cat cow coW COW
Cat cat cat CAR car

[mitesh@Matrix ~]$ sed 's/cat/dog/' pets
dog cat cat Cat CAT
dog cat cow coW COW
Cat dog cat CAR car

[mitesh@Matrix ~]$ sed 's/cat/dog/gi' pets
dog dog dog dog dog
dog dog cow coW COW
dog dog dog CAR car

# sed search/replace pattern starts working on all the lines of the file called pets.
[mitesh@Matrix ~]$ sed 's/cat/dog/g' pets

# sed search/replace pattern starts working between the lines of 1 to 50.
[mitesh@Matrix ~]$ sed '1,50s/cat/dog/g' pets

# sed search/replace pattern starts working on the line that contains the
# string digby and continuing through the line that contain the string duncan.
[mitesh@Matrix ~]$ sed '/digby/,/duncan/s/cat/dog/g' pets

# Multiple sed instruction:
sed -e 's/cat/dog/' -e 's/hi/hello/' pets
sed -f myedits pets


# Delete Last Empty New Line
[mitesh@Matrix ~]$ sed '/^$/d' file.txt

# Insert New Line Above Last Line
[mitesh@Matrix ~]$ sed '$ c\\t\include /etc/nginx/common/*.conf;\n}' file.txt
```

### Regex Command

-   `regex`: Regular Expressions
-   For more details see `man 7 regex`
-   `man grep`

```
/-----------------------------------------------------------------------\
|Metachracter|Meaning|
|------------------------------------------------------------------------
|^|Line Begin|
|$|Line Ends|
|[xyz]|A character that is x, y or z|
|[^xyz]|A character that is not x, y or z|
\-----------------------------------------------------------------------/

```

**Examples:**

```
[mitesh@Matrix ~]$ grep 'root' /etc/passwd
root:x:0:0:root:/root:/bin/bash
operator:x:11:0:operator:/root:/sbin/nologin

[mitesh@Matrix ~]$ grep '^root' /etc/passwd
root:x:0:0:root:/root:/bin/bash
```

## Post Navigation

[Standard IO & Pipes](https://miteshshah.github.io/linux/basics/standard-io-and-pipes/) [VIM - an Advance Text Editor](https://miteshshah.github.io/linux/basics/vim-an-advance-text-editor/)

---
