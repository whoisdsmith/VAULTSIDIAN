# Text Processing in the Shell

---

This article is part of a self-published book project by Balthazar Rouberol and [Etienne Brodu](https://etnbrd.com/), ex-roommates, friends and colleagues, aiming at empowering the up and coming generation of developers. We currently are hard at work on it!

If you are interested in the project, we invite you to join the [mailing list](https://balthazar-rouberol.us4.list-manage.com/subscribe?u=1f6080d496af07a836270ff1d&id=81ebd36adb)!

## Table of Contents

- [`cat`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#cat)
- [`head`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#head)
- [`tail`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#tail)
- [`wc`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#wc)
- [`grep`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#grep)
- [`cut`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#cut)
- [`paste`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#paste)
- [`sort`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#sort)
- [`uniq`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#uniq)
- [`awk`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#awk)
- [`tr`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#tr)
- [`fold`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#fold)
- [`sed`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#sed)
- [Real-life examples](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#real-life-examples)
- [Going further: `for` loops and `xargs`](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#going-further-for-loops-and-xargs)
- [Summary](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#summary)
- [Going further](https://blog.balthazar-rouberol.com/text-processing-in-the-shell#going-further)

## Text Processing in the Shell

One of the things that makes the shell an invaluable tool is the amount of available text processing commands, and the ability to easily pipe them into each other to build complex text processing workflows. These commands can make it trivial to perform text and data analysis, convert data between different formats, filter lines, etc.

When working with text data, the philosophy is to break any complex problem you have into a set of smaller ones, and to solve each of them with a specialized tool.

> Make each program do one thing well.<sup id="fnref:1"><a href="https://blog.balthazar-rouberol.com/text-processing-in-the-shell#fn:1">1</a></sup>

The examples in that chapter might seem a little contrived at first, but this is also by design. Each one of these tools was designed to solve one small problem. They however become extremely powerful when combined.

We will go over some of the most common and useful text processing commands the shell has to offer, and will demonstrate real-life workflows piping them together. I suggest you take a look at the `man` of these commands to see the full breadth of options at your disposal.

The example CSV (comma-separated values) file is available online.<sup id="fnref:2"><a href="https://blog.balthazar-rouberol.com/text-processing-in-the-shell#fn:2">2</a></sup> Feel free to download it yourself to test these commands.

## `cat`

As seen in the previous chapter, `cat` is used to concatenate a list of one or more files and displays their content on screen.

```
$ cat Documents/readme
Thanks again for reading this book!
I hope you're following so far!

$ cat Documents/computers
Computers are not intelligent
They're just fast at making dumb things.
$ cat Documents/readme Documents/computers
Thanks again for reading this book!
I hope you are following so far!

Computers are not intelligent
They're just fast at making dumb things.

```

## `head`

`head` prints the first n lines in a file. It can be very useful to peek into a file of unknown structure and format without burying your shell under a wall of text.

```
$ head -n 2 metadata.csv
metric_name,metric_type,interval,unit_name,per_unit_name,description,orientation,integration,short_name
mysql.galera.wsrep_cluster_size,gauge,,node,,The current number of nodes in the Galera cluster.,0,mysql,galera cluster size

```

If `-n` is unspecified, `head` will print the first 10 lines in its argument file or input stream.

## `tail`

`tail` is `head`’s counterpart. It prints the last n lines in a file.

```
$ tail -n 1 metadata.csv
mysql.performance.queries,gauge,,query,second,The rate of queries.,0,mysql,queries

```

If you want to print all lines in a file located after the nth line (included), you can use the `-n +n` argument.

```
$ tail -n +42 metadata.csv
mysql.replication.slaves_connected,gauge,,,,Number of slaves connected to a replication master.,0,mysql,slaves connected
mysql.performance.queries,gauge,,query,second,The rate of queries.,0,mysql,queries

```

Our file has 43 lines, so `tail -n +42` only prints the 42nd and 43rd line in our file.

If `-n` is unspecified, `tail` will print the last 10 lines in its argument file or input stream.

`tail -f` or `tail --follow` displays the last lines in a file and displays each new line as the file is being written to. It is very useful to see real time activity that is written to a log file, for example a web server log file, etc.

## `wc`

`wc` (for *word count*) prints either the number of characters (when using `-c`), words (when using `-w`) or lines (when using `-l`) in its argument files or input stream.

```
$ wc -l metadata.csv
43  metadata.csv
$ wc -w metadata.csv
405 metadata.csv
$ wc -c metadata.csv
5094 metadata.csv

```

By default, `wc` prints all of the above.

```
$ wc metadata.csv
43     405    5094 metadata.csv

```

Only the count will be printed out if the text data is piped in or redirected into `stdin`.

```
$ cat metadata.csv | wc
43     405    5094
$ cat metadata.csv | wc -l
43
$ wc -w < metadata.csv
405

```

## `grep`

`grep` is the Swiss Army knife of line filtering. It allows you to filter lines matching a given pattern.

For example, we can use `grep` to find all occurrences of the word *mutex* in our `metadata.csv` file.

```
$ grep mutex metadata.csv
mysql.innodb.mutex_os_waits,gauge,,event,second,The rate of mutex OS waits.,0,mysql,mutex os waits
mysql.innodb.mutex_spin_rounds,gauge,,event,second,The rate of mutex spin rounds.,0,mysql,mutex spin rounds
mysql.innodb.mutex_spin_waits,gauge,,event,second,The rate of mutex spin waits.,0,mysql,mutex spin waits

```

`grep` can either filter files passed as arguments, or a stream of text passed to its `stdin`. We can thus chain multiple `grep` commands to further filter our text. In the next example, we filter lines in our `metadata.csv` file that contain both the *mutex* and *OS* words.

```
$ grep mutex metadata.csv | grep OS
mysql.innodb.mutex_os_waits,gauge,,event,second,The rate of mutex OS waits.,0,mysql,mutex os waits

```

Let’s go over some of the options you can pass to grep and their associated behavior.

`grep -v` performs an invert matching: it filters the lines that do *not* match the argument pattern.

```
$ grep -v gauge metadata.csv
metric_name,metric_type,interval,unit_name,per_unit_name,description,orientation,integration,short_name

```

`grep -i` performs a case-insensitive matching. In the next example `grep -i os` matches both *OS* and *os*.

```
$ grep -i os metadata.csv
mysql.innodb.mutex_os_waits,gauge,,event,second,The rate of mutex OS waits.,0,mysql,mutex os waits
mysql.innodb.os_log_fsyncs,gauge,,write,second,The rate of fsync writes to the log file.,0,mysql,log fsyncs

```

`grep -l` only lists files containing a match.

```
$ grep -l mysql metadata.csv
metadata.csv

```

`grep -c` counts the number of times a pattern was found.

```
$ grep -c select metadata.csv
3

```

`grep -r` recursively searches files in the current working directory and all subdirectories below it.

```
$ grep -r are ~/Documents
/home/br/Documents/computers:Computers are not intelligent
/home/br/Documents/readme:I hope you are following so far!

```

`grep -w` only matches whole words.

```
$ grep follow ~/Documents/readme
I hope you are following so far!
$ grep -w follow ~/Documents/readme
$

```

## `cut`

`cut` cuts out a portion of a file (or, as always, its input stream). `cut` works by defining a field delimited (what separates two columns) with the `-d` option, and what column(s) should be extracted, with the `-f` option.

For example, the following command extracts the first column of the last 5 lines our CSV file.

```
$ tail -n 5 metadata.csv | cut -d , -f 1
mysql.performance.user_time
mysql.replication.seconds_behind_master
mysql.replication.slave_running
mysql.replication.slaves_connected
mysql.performance.queries

```

As we are dealing with a CSV file, we can extract each column by cutting over the `,` character, and extract the first column with `-f 1`.

We could also select both the first and second columns by using the `-f 1,2` option.

```
$ tail -n 5 metadata.csv | cut -d , -f 1,2
mysql.performance.user_time,gauge
mysql.replication.seconds_behind_master,gauge
mysql.replication.slave_running,gauge
mysql.replication.slaves_connected,gauge
mysql.performance.queries,gauge

```

## `paste`

`paste` can merge together two different files into one multi-column file.

```
$ cat ingredients
eggs
milk
butter
tomatoes
$ cat prices
1$
1.99$
1.50$
2$/kg
$ paste ingredients prices
eggs    1$
milk    1.99$
butter  1.50$
tomatoes    2$/kg

```

By default, `paste` uses a tab delimiter, but you can change that using the `-d` option.

```
$ paste ingredients prices -d:
eggs:1$
milk:1.99$
butter:1.50$
tomatoes:2$/kg

```

Another common use of `paste` it to join all lines within a stream or a file using a given delimiter, using a combination of the `-s` and `-d` argument.

```
$ paste -s -d, ingredients
eggs,milk,butter,tomatoes

```

If `-` is specified as an input file, `stdin` will be read instead.

```
$ cat ingredients | paste -s -d, -
eggs,milk,butter,tomatoes

```

## `sort`

`sort`, well, sorts argument files or input.

```
$ cat ingredients
eggs
milk
butter
tomatoes
salt
$ sort ingredients
butter
eggs
milk
salt
tomatoes

```

`sort -r` performs a reverse sort.

```
$ sort -r ingredients
tomatoes
salt
milk
eggs
butter

```

`sort -n` performs a numerical sort, by sorting fields by their arithmetic value.

```
$ cat numbers
0
2
1
10
3
$ sort numbers
0
1
10
2
3
$ sort -n numbers
0
1
2
3
10

```

## `uniq`

`uniq` detects or filters out adjacent identical lines in its argument file or input stream.

```
$ cat duplicates
and one
and one
and two
and one
and two
and one, two, three
$ uniq duplicates
and one
and two
and one
and two
and one, two, three

```

As `uniq` only filters out *adjacent* identical lines, we can still see more than one unique lines in its output. To filter out all identical lines from our `duplicates` file, we need to sort its content first.

```
$ sort duplicates | uniq
and one
and one, two, three
and two

```

`uniq -c` prepends all lines with its number of occurrences.

```
$ sort duplicates | uniq -c
   3 and one
   1 and one, two, three
   2 and two

```

`uniq -u` only displays the unique lines within its input.

```
$ sort duplicates | uniq -u
and one, two, three

```

`uniq` is particularly useful used in conjunction with `sort`, as `| sort | uniq` allows you to remove any duplicate line in a file or a stream.

## `awk`

`awk` is a little more than a text processing tool: it’s actually a whole programming language of its own<sup id="fnref:3"><a href="https://blog.balthazar-rouberol.com/text-processing-in-the-shell#fn:3">3</a></sup>. One thing `awk` is *really* good at is splitting files into columns, and it especially shines when these files contain a mix and match of spaces and tabs.

```
$ cat -t multi-columns
John Smith    Doctor^ITardis
Sarah-James Smith^I    Companion^ILondon
Rose Tyler   Companion^ILondon

```

`cat -t` displays tabs as `^I`.

We can see that these columns are either separated by spaces or tabs, and that they are not always separated by the same number of spaces. `cut` would be of no use there, because it only works on a single character delimiter. `awk` however, can easily make sense of that file.

`awk '{ print $n }'` prints the nth column in the text.

```
$ cat multi-columns | awk '{ print $1 }'
John
Sarah-James
Rose
$ cat multi-columns | awk '{ print $3 }'
Doctor
Companion
Companion
$ cat multi-columns | awk '{ print $1,$2 }'
John Smith
Sarah-James Smith
Rose Tyler

```

There is so much more we can do with `awk`, however, printing columns probably accounts for 99% of my personal usage.

`{ print $NF }` prints the last column in the line.

## `tr`

`tr` stands for *translate*, and it replaces characters into others. It either works on characters or character *classes*, such as lowercase, printable, spaces, alphanumeric, etc.

`tr <char1> <char2>` translates all occurrences of `<char1>` from its standard input into `<char2>`.

```
$ echo "Computers are fast" | tr a A
computers Are fAst

```

`tr` can also translate character classes by using the `[:class:]` notation. The full list of available classes is described in the `tr` man page, but we’ll demonstrate some of them here.

`[:space:]` represent all types of spaces, from a simple space, to a tab or a newline.

```
$ echo "computers are fast" | tr '[:space:]' ','
computers,are,fast,%

```

All spaces-like characters were translated into a comma. Note that the `%` character at the end of the output represents the lack of a trailing newline. Indeed, that newline was translated to a comma as well.

`[:lower:]` represents all lowercase characters, and `[:upper:]` represents all uppercase characters. Converting between cases is thus made very easy.

```
$ echo "computers are fast" | tr '[:lower:]' '[:upper:]'
COMPUTERS ARE FAST
$ echo "COMPUTERS ARE FAST" | tr '[:upper:]' '[:lower:]'
computers are fast

```

`tr SET1 SET2` will transform any character in SET1 into the characters in SET2. The following example replaces all vowels by spaces.

```
$ echo "computers are fast" | tr '[aeiouy]' ' '
c mp t rs  r  f st

```

`tr -c SET1 SET2` does the opposite: it transforms any character *not* in SET1 into the characters in SET2. The following example replaces all non vowels by spaces.

```
$ echo "computers are fast" | tr -c '[aeiouy]' ' '
 o  u e   a e  a

```

`tr -d` deletes the matched characters, instead of replacing them. It’s the equivalent of `tr <char> ''`.

```
$ echo "Computers Are Fast" | tr -d '[:lower:]'
C A F

```

`tr` can also replace character ranges, for example all letters between *a* and *e*, or all numbers between 1 and 8, by using the notation `s-e`, where `s` is the start character and `e` is the end one.

```
$ echo "computers are fast" | tr 'a-e' 'x'
xomputxrs xrx fxst
$ echo "5uch l337 5p34k" | tr '1-4' 'x'
5uch lxx7 5pxxk

```

`tr -s string1` compresses any multiple occurrences of the characters in `string1` into a single one. One of the most useful uses of `tr -s` is to replace multiple consecutive spaces by a single one.

```
$ echo "Computers         are       fast" | tr -s ' '
Computers are fast

```

## `fold`

`fold` wraps each input line to fit in a specified width. It can be useful to make sure an argument text fits in a small display size for example. `fold -w n` folds the lines at `n` characters.

```
$ cat ~/Documents/readme | fold -w 16
Thanks again for
 reading this bo
ok!
I hope you're fo
llowing so far!

```

`fold -s` will only break lines on a space character, and can be combined with `-w` to fold up to a given number of characters.

```
Thanks again
for reading
this book!
I hope you're
following so
far!

```

## `sed`

`sed` is a non-interactive stream editor, used to perform text transformation on its input stream, on a line-per-line basis. It can take its output from a file our its `stdin` and will output its result either in a file or its `stdout`.

It works by taking one or many optional *addresses*, a *function* and *parameters*. A `sed` command thus looks like this:

```
[address[,address]]function[arguments]

```

While `sed` can perform many functions, we will cover only substitution, as it is probably `sed`’s most common use.

### Substituting Text

A `sed` substitution command looks like this:

```
s/PATTERN/REPLACEMENT/[options]

```

**Example**: replacing the first instance of a word for each line in a file

```
$ cat hello
hello hello
hello world!
hi
$ cat hello | sed 's/hello/Hey I just met you/'
Hey I just met you hello
Hey I just met you world
hi

```

We can see that only the first occurrence of `hello` was replaced in the first line. To replace *all* occurrences of `hello` in each line, we can use the `g` (for *global*) option.

```
$ cat hello | sed 's/hello/Hey I just met you/g'
Hey I just met you Hey I just met you
Hey I just met you world
hi

```

`sed` allows you to specify any other separator than `/`, which is especially useful to keep the command readable if the search of replacement pattern contains forward slashes.

```
$ cat hello | sed 's@hello@Hey I just met you@g'
Hey I just met you Hey I just met you
Hey I just met you world
hi

```

By specifying an address, we can tell sed on which line or line-range to actually perform the substitution.

```
$ cat hello | sed '1s/hello/Hey I just met you/g'
Hey I just met you hello
hello world
hi
$ cat hello | sed '2s/hello/Hey I just met you/g'
hello hello
Hey I just met you  world
hi

```

The address `1` tells `sed` to only replace `hello` by `Hey I just met you` on line 1. We can specify an address range with the notation `<start>,<end>` where `<end>` can either be a line number or `$`, meaning the last line in the file.

```
$ cat hello | sed '1,2s/hello/Hey I just met you/g'
Hey I just met you Hey I just met you
Hey I just met you world
hi
$ cat hello | sed '2,3s/hello/Hey I just met you/g'
hello hello
Hey I just met you world
hi
$ cat hello | sed '2,$s/hello/Hey I just met you/g'
hello hello
Hey I just met you world
hi

```

By default, `sed` displays its result in its `stdout`, but it can also edit the initial file in-place, with the use of the `-i` option.

```
$ sed -i '' 's/hello/Bonjour/' sed-data
$ cat sed-data
Bonjour hello
Bonjour world
hi

```

On Linux, only `-i` needs to be specified. However, due to the fact that `sed`’s behavior on macOS is slightly different, the `''` needs to be added right after `-i`.

## Real-life Examples

### Filtering a CSV Using `grep` and `awk`

```
$ grep -w gauge metadata.csv | awk -F, '{ if ($4 == "query") { print $1, "per", $5 } }'
mysql.performance.com_delete per second
mysql.performance.com_delete_multi per second
mysql.performance.com_insert per second
mysql.performance.com_insert_select per second
mysql.performance.com_replace_select per second
mysql.performance.com_select per second
mysql.performance.com_update per second
mysql.performance.com_update_multi per second
mysql.performance.questions per second
mysql.performance.slow_queries per second
mysql.performance.queries per second

```

This example filters the lines containing the word `gauge` in our `metadata.csv` file using `grep`, then the filters the lines with the string `query` as their 4th column, and displays the metric name (1st column) with its associated `per_unit_name` value (5th column).

### Printing the IPv4 Address Associated with a Network Interface

```
$ ifconfig en0 | grep inet | grep -v inet6 | awk '{ print $2 }'
192.168.0.38

```

`ifconfig <interface name>` prints details associated with the argument network interface name. For example:

```
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
    ether 19:64:92:de:20:ba
    inet6 fe80::8a3:a1cb:56ae:7c7c%en0 prefixlen 64 secured scopeid 0x7
    inet 192.168.0.38 netmask 0xffffff00 broadcast 192.168.0.255
    nd6 options=201<PERFORMNUD,DAD>
    media: autoselect
    status: active

```

We then `grep` for `inet`, which will match 2 lines.

```
$ ifconfig en0 | grep inet
    inet6 fe80::8a3:a1cb:56ae:7c7c%en0 prefixlen 64 secured scopeid 0x7
    inet 192.168.0.38 netmask 0xffffff00 broadcast 192.168.0.255

```

We then exclude the line with `ipv6` by using a `grep -v`.

```
$ ifconfig en0 | grep inet | grep -v inet6
inet 192.168.0.38 netmask 0xffffff00 broadcast 192.168.0.255

```

We finally use `awk` to get the 2nd column in that line: the IPv4 address associated with our `en0` network interface.

```
$ ifconfig en0 | grep inet | grep -v inet6 | awk '{ print $2 }'
192.168.0.38

```

It has been [suggested](https://www.reddit.com/r/bash/comments/finbd2/beginner_friendly_introduction_to_the_shell_text/fki8523/?context=3) to me that `grep inet | grep -v inet6` could be replaced by the following future-proof `awk` command:

```
$ ifconfig en0 | awk ' $1 == "inet" { print $2 }'
192.168.0.38

```

It is shorter and specifically targets IPv4 using the `$1 == "inet"` condition.

### Extracting a Value From a Config File

```
$ grep 'editor =' ~/.gitconfig  | cut -d = -f2 | sed 's/ //g'
/usr/bin/vim

```

We look for the `editor =` value in the current user’s git configuration file, then cut over the `=` sign, get the second column and remove any space around that column.

```
$ grep 'editor =' ~/.gitconfig
     editor = /usr/bin/vim
$ grep 'editor =' ~/.gitconfig  | cut -d'=' -f2
 /usr/bin/vim
$ grep 'editor =' ~/.gitconfig  | cut -d'=' -f2 | sed 's/ //'
/usr/bin/vim

```

### Extracting IP Addresses From a Log File

The following real life example looks for the message `Too many connections from` in a database log file (which is followed by an IP address) and displays the 10 biggest offenders.

```
$ grep 'Too many connections from' db.log | \
  awk '{ print $12 }' | \
  sed 's@/@@' | \
  sort | \
  uniq -c | \
  sort -rn | \
  head -n 10 | \
  awk '{ print $2 }'
   10.11.112.108
   10.11.111.70
   10.11.97.57
   10.11.109.72
   10.11.116.156
   10.11.100.221
   10.11.96.242
   10.11.81.68
   10.11.99.112
   10.11.107.120

```

Let’s break down what this pipeline of command does. First, let’s look at what a log line looks like.

```
$ grep "Too many connections from" db.log | head -n 1
2020-01-01 08:02:37,617 [myid:1] - WARN  [NIOServerCxn.Factory:1.2.3.4/1.2.3.4:2181:NIOServerCnxnFactory@193] - Too many connections from /10.11.112.108 - max is 60

```

`awk '{ print $12 }'` then extracts the IP from the line.

```
$ grep "Too many connections from" db.log | awk '{ print $12 }'
/10.11.112.108
...

```

`sed 's@/@@'` removes the trailing slash from the IPs.

```
$ grep "Too many connections from" db.log | awk '{ print $12 }' | sed 's@/@@'
10.11.112.108
...

```

As we have previously seen, we can use whatever separator we want for `sed`. While `/` is commonly used as a separator, we are currently replacing that very character, which would make the substitution expression sightly less readable.

`sort | uniq -c` sorts the IPs lexicographically, and then removed duplicates while prefixing IPs by their associated number of occurrences.

```
$ grep 'Too many connections from' db.log | \
  awk '{ print $12 }' | \
  sed 's@/@@' | \
  sort | \
  uniq -c
   1379 10.11.100.221
   1213 10.11.103.168
   1138 10.11.105.177
    946 10.11.106.213
   1211 10.11.106.4
   1326 10.11.107.120
   ...

```

`sort -rn | head -n 10` sorts the lines by the number of occurrences, numerically and in the reversed order, which displays the biggest offenders first, 10 of which are displayed. The final `awk { print $2 }` extracts the IPs themselves.

```
$ grep 'Too many connections from' db.log | \
  awk '{ print $12 }' | \
  sed 's@/@@' | \
  sort | \
  uniq -c | \
  sort -rn | \
  head -n 10 | \
  awk '{ print $2 }'
  10.11.112.108
  10.11.111.70
  10.11.97.57
  10.11.109.72
  10.11.116.156
  10.11.100.221
  10.11.96.242
  10.11.81.68
  10.11.99.112
  10.11.107.120

```

### Renaming a Function in a Source File

Let’s imagine that we are working a code project, and we would like to rename rename a poorly named function (or class, variable, etc) in a code file. We can do this by using `sed -i`, which performs an in-place replacement in a file.

```
$ cat izk/utils.py
def bool_from_str(s):
    if s.isdigit():
        return int(s) == 1
    return s.lower() in ['yes', 'true', 'y']

```

```
$ sed -i 's/def bool_from_str/def is_affirmative/' izk/utils.py
$ cat izk/utils.py
def is_affirmative(s):
    if s.isdigit():
        return int(s) == 1
    return s.lower() in ['yes', 'true', 'y']

```

Use `sed -i ''` instead of `sed -i` on macOs, as the `sed` version behaves slightly differently.

We’ve however only renamed this function in the file it was defined in. Any other file we import `bool_from_str` will now be broken, as this function is not defined anymore. We’d need a way to rename `bool_from_str` everywhere it is found in our project. We can achieve just that by using `grep`, `sed`, and either `for` loops or `xargs`.

## Going Further: `for` Loops and `xargs`

To replace all occurrences of `bool_from_str` in our project, we first need to recursively find them using `grep -r`.

```
$ grep -r bool_from_str .
./tests/test_utils.py:from izk.utils import bool_from_str
./tests/test_utils.py:def test_bool_from_str(s, expected):
./tests/test_utils.py:    assert bool_from_str(s) == expected
./izk/utils.py:def bool_from_str(s):
./izk/prompt.py:from .utils import bool_from_str
./izk/prompt.py:                    default = bool_from_str(os.environ[envvar])

```

As we are only interested in the matching files, we also need to use the `-l/--files-with-matches` option:

```
-l, --files-with-matches
        Only the names of files containing selected lines are written to standard out-
        put.  grep will only search a file until a match has been found, making
        searches potentially less expensive.  Pathnames are listed once per file
        searched.  If the standard input is searched, the string ``(standard input)''
        is written.

```

```
$ grep -r --files-with-matches bool_from_str .
./tests/test_utils.py
./izk/utils.py
./izk/prompt.py

```

We can then use the `xargs` command to perform an action on each line in the output (each file containing the `bool_from_str` string).

```
$ grep -r --files-with-matches bool_from_str . | \
  xargs -n 1 sed -i 's/bool_from_str/is_affirmative/'

```

`-n 1` tells `xargs` that each line in the output should cause a separate `sed` command to be executed.

The following commands are then executed:

```
$ sed -i 's/bool_from_str/is_affirmative/' ./tests/test_utils.py
$ sed -i 's/bool_from_str/is_affirmative/' ./izk/utils.py
$ sed -i 's/bool_from_str/is_affirmative/' ./izk/prompt.py

```

If the command you call with `xargs` (`sed`, in our case) support multiple arguments, you can (and shoud, as a single command will execute faster) drop the `-n 1` argument and run

```
$ grep -r --files-with-matches bool_from_str . | xargs sed -i 's/bool_from_str/is_affirmative/'

```

which will then execute

```
$ sed -i 's/bool_from_str/is_affirmative/' ./tests/test_utils.py ./izk/utils.py ./izk/prompt.py

```

We can see that `sed` can take multiple arguments by looking at its synopsis, in its `man` page.

```
SYNOPSIS
     sed [-Ealn] command [file ...]
     sed [-Ealn] [-e command] [-f command_file] [-i extension] [file ...]

```

Indeed, as we’ve seen in the previous chapter, `file …` means that multiple arguments representing file names are accepted.

We can see that all `bool_from_str` occurrences have been replaced.

```
$ grep -r is_affirmative .
./tests/test_utils.py:from izk.utils import is_affirmative
./tests/test_utils.py:def test_is_affirmative(s, expected):
./tests/test_utils.py:    assert is_affirmative(s) == expected
./izk/utils.py:def is_affirmative(s):
./izk/prompt.py:from .utils import is_affirmative
./izk/prompt.py:                    default = is_affirmative(os.environ[envvar])

```

As it is often the case, there are multiple ways of achieving the same result. Instead of using `xargs`, we could have used `for` lops, which allow you to iterate over a list of lines and perform an action on each element. These `for` loops have the following syntax:

```
for item in list; do
    command $item
done

```

By wrapping our `grep` command by `$()`, it will cause the shell to execute the it in a *subshell*, which result will then be iterated on by the `for` loop.

```
$ for file in $(grep -r --files-with-matches bool_from_str .); do
  sed -i 's/bool_from_str/is_affirmative/' $file
done

```

which will execute

```
$ sed -i 's/bool_from_str/is_affirmative/' ./tests/test_utils.py
$ sed -i 's/bool_from_str/is_affirmative/' ./izk/utils.py
$ sed -i 's/bool_from_str/is_affirmative/' ./izk/prompt.py

```

I tend to find the for loop syntax clearer than `xargs`’s. `xargs` can however execute the commands in parallel using its `-P n` options, where `n` is the maximum number of parallel commands to be executed at a time, which can be a performance win if your command takes time to run.

## Summary

All these tools open up a world of possibilities, as they allow you to extract data and transform its format, to make it possible to build entire workflows of commands that were possibly never intended to work together. Each of these commands accomplishes has a relatively small function (`sort` sorts, `cat` concatenates, `grep` filters, `sed` edits, `cut` cuts, etc).

Any given task involving text, can then be reduced to a pipeline of smaller tasks, each of them performing a simple action and piping its output into the next task.

For example, if we wanted to know how many unique IPs could be found in a log file, and that these IPs always appeared at the same column, we could:

- `grep` lines on a pattern specific to lines containing an IP address
- locate the column the IPs appear, and extract them with `awk`
- sort the list of IPs with `sort`
- compute the list of *unique* IPs with `uniq`
- count the number of lines (aka, of unique IPs) with `wc -l`

As there is a plethora of text processing tools, either available by default or installable, there is bound to be many ways to solve any given task.

The examples in this article were contrived, but I suggest you read the amazing article “Command-line Tools can be 235x Faster than your Hadoop Cluster”<sup id="fnref:4"><a href="https://blog.balthazar-rouberol.com/text-processing-in-the-shell#fn:4">4</a></sup> to get a sense of how useful and powerful these text processing commands really are, and what real-life problems they can solve.

## Going Further

**2.1**: Count the number of files and directories located in your home directory.

**2.2**: Display the content of a file in all caps.

**2.3**: Count how many times each word was found in a file.

**2.4**: Count the number of vowels present in a file. Display the result from the most common to the least.

# The Shell's Building Blocks

---

![](https://p1.pxfuel.com/preview/880/869/94/lego-build-building-blocks-toys.jpg)

This article is part of a self-published book project by Balthazar Rouberol and [Etienne Brodu](https://etnbrd.com/), ex-roommates, friends and colleagues, aiming at empowering the up and coming generation of developers. We currently are hard at work on it!

If you are interested in the project, we invite you to join the [mailing list](https://balthazar-rouberol.us4.list-manage.com/subscribe?u=1f6080d496af07a836270ff1d&id=81ebd36adb)!

## Table of Contents

- [Environment variables](https://blog.balthazar-rouberol.com/the-shells-building-blocks#environment-variables)
- [Aliases](https://blog.balthazar-rouberol.com/the-shells-building-blocks#aliases)
- [Functions](https://blog.balthazar-rouberol.com/the-shells-building-blocks#functions)
- [Real life examples](https://blog.balthazar-rouberol.com/the-shells-building-blocks#real-life-examples)
- [Summary](https://blog.balthazar-rouberol.com/the-shells-building-blocks#summary)
- [Going further](https://blog.balthazar-rouberol.com/the-shells-building-blocks#going-further)

## The Shell's Building Blocks

As we have seen in the [previous chapters](https://blog.balthazar-rouberol.com/discovering-the-terminal), the shell is a program allowing you to run other programs. It is an invaluable tool in the life of a software engineer, as it provides you with a simple text-based interface to control your computer and any program you might install or write.

Something I still find striking after years of using a shell almost daily is how simple yet powerful its building blocks are.

[Chapter 1](https://blog.balthazar-rouberol.com/discovering-the-terminal) covered commands, I/O streams and pipes. This chapter will cover environment variables, aliases and functions.

## Environment Variables

Environment variables are key/value pairs that affect how running programs behave. Another way to say that would be that environment variables can allow you to tweak and personalize how certain programs, amongst which your shell, work. They can also define what programs will be called to perform a certain task.

Here are a few examples:

- `SHELL` defines what shell your terminal runs (‘/bin/bash', `/bin/zsh`, `/bin/fish`, etc)
- `HOME` defines where your home directory is located
- `EDITOR` defines what text editor program should be used to edit text within your terminal (eg `nano`, `vim`, `emacs`, etc)

### Displaying an Environment Variable's Value

To display the value of given environment variable, you can use the `echo` command, followed by a dollar sign and the name of the variable:

You can use the `printenv` command to list all environment variables along with their value.

```
$ printenv
USER=br
HOME=/home/br
LC_TERMINAL=terminator
SHELL=/bin/zsh
EDITOR=vim
PWD=/home/br/
PAGER=less

```

For the sake of brevity, I've only displayed a subset of the environment variables defined on my computer. These variables tell the following story:

- my username is `br`
- all my personal data is stored in my *home directory*, located at `/home/br`
- my default terminal is called `terminator`
- and whenever I open `terminator`, it runs the commands via the `zsh` shell
- my default text editor is `vim`
- I am currently located in my home directory
- my default pager program is `less`

### Changing an Environment Variable

What is interesting about these environment variables is that they can be changed, and with them, the behavior of other programs.

For example, let's change the value of our `HOME` environment variable, defining where our home directory is.

```
$ HOME=/tmp
$ cd
$ pwd
/tmp

```

In the first line, I redefined the value of my `HOME` environment variable from `/home/br` to `/tmp`. Remember when you learned that running `cd` without arguments would take you back to your home directory? Well, it's actually using the `HOME` environment variable to figure out where your home directory is. Now that `HOME` has changed, so has `cd`'s behavior.

Another example is `PAGER`. We saw that my environment had `PAGER=less` defined by default, which explains why you find yourself reading text within `less` when you open a man page. `man` fetches the actual documentation and displays it in a pager, which itself is specified by the `PAGER` environment variable. If you were to change that variable to something else, like `more` or `bat`,<sup id="fnref:1"><a href="https://blog.balthazar-rouberol.com/the-shells-building-blocks#fn:1">1</a></sup> it would then change `man`'s behavior.

There is a difference between `SHELL` and `$SHELL`. The first one is the name of an environment variable, and the latter represents its value. Consequently, when we executed `echo $SHELL`, we told our shell to lookup what value was associated with the `SHELL` environment variable, and then display it to the screen via the `echo` command. `$` is what we call a *dereference operator* in that context.

### Defining New Variables

Not only can you change an existing environment variable, but you can also define a new one. If a non-existing variable is `echo`\-ed, it will simply be replaced by an empty string.

```
$ echo $NEW_VAR

$ NEW_VAR=my-new-env-var
$ echo $NEW_VAR
my-new-env-var

```

If you define an environment variable this way, it will only be visible by the shell itself, but not by any command executed by your shell (also called *subprocesses*). To make an environment variable visible by a subprocess, you need to define it after the `export` keyword.

To illustrate that, we will create our first *shell script*: a program executing shell commands one after the others.

```
$ cat <<EOF > echo_var.sh
echo $NEW_VAR
EOF
$ cat echo_var.sh
echo $NEW_VAR

```

As you can see, the `echo_var.sh` *script* only contains one shell command: `echo $NEW_VAR`.

To execute that bash script, we can run `bash echo_var.sh`, and all instructions within that script will be executed by `bash`. Let's have a look at what executing that script displays on the screen with and without `export`\-ing that variable.

```
$ NEW_VAR=my-new-var
$ echo $NEW_VAR
my-new-var
$ bash echo_var.sh

$ export NEW_VAR=my-new-var
$ echo $NEW_VAR
my-new-var
$ bash echo_var.sh
my-new-var

```

As you can see, the `echo_var.sh` subprocess can see the `NEW_VAR` environment variable after it has been `export`\-ed by its parent shell.

This can very useful if you write programs: some parameters can have a sane default value but can also be overridden by specifying an environment variable. `grep` does this for example: reading the `grep` `man` page, we see:

> `GREP_OPTIONS` May be used to specify default options that will be placed at the beginning of the argument list.

### Removing Environment Variables

You can remove an environment variable by using the `unset` keyword:

```
$ unset NEW_VAR
$ bash echo_var.sh

$ echo $NEW_VAR

$

```

### The Case of `PATH`

Until that point, we've executed commands in the shell, and things happened. It was a simple world and it was nice. You might wonder *what would happen if I gave the shell a non-existent command though?*. Well, I'm glad you asked. Ten points for Gryffindor.

```
$ cmdnotfound
zsh: command not found: cmdnotfound

```

The `cmdnotfound` command, like its name implies, is not found. But what makes a command be found then? What makes the shell happily comply when we type `ls`, and makes it complain when we type `cmdnotfound`? It turns out that this is due to an environment variable called `PATH`, listing all directories in which executable programs can be found.

```
$ echo $PATH
/home/br/bin:/home/br/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games

```

This means that for any command passed to the shell, it will look into these directories (separated by a colon) in search for the program I'm trying to run.

For example, if I type

into my shell, it will look into `/home/br/bin`, `/home/br/.local/bin`, `/usr/local/sbin`, etc, until it finds it in `/bin`.

```
$ ls /bin
...
chmod      dd         ed        ls         ps         sh         tcsh       zsh

```

If the command is not found in any of the directories listed in `PATH`, then it is not found.

This means that you can also redefine `PATH` to force your shell to look into new directories. In fact, this is exactly what I've done to make it look into `/home/br/bin`, where I store tools of my making.

You can mess with up your shell by running `unset PATH`.

```
$ unset PATH
$ ls
zsh: command not found: ls

```

However, calling a command by using its absolute or relative path still works, as `PATH` is only used to look for commands that only have been invoked by name.

```
$ unset PATH
$ /bin/ls
bin    code    Documents  ..
...

```

There is a useful command you can use to know what a program is and where it is found: `which`.

```
$ which less
/usr/bin/less
$ which bash
/usr/local/bin/bash
$ which ls
ls: aliased to ls -G

```

Wait. What? What's an alias?

## Aliases

An *alias* allows you to define custom commands. In the previous example, running `ls` would actually run `ls -G`, which enables colorized output.

You can define an alias by using the `alias` keyword.

There are a couple of reasons you might want to define aliases:

- redefining a command's behavior (ex: always using `ls` with the `-G` option)
- shortening a command's name to make it quicker to type (ex: `alias ..='cd ..'`)
- creating new commands altogether (ex: `alias filesize='ls --size --human-readable -1'`)

To see the underlying command that will be executed by an alias, you can type `alias <name>`.

```
$ alias filesize='ls --size --human-readable -1'
$ alias filesize
alias filesize='ls --size --human-readable -1'

```

Aliases are very simple yet powerful. They allow you to customize your shell to your liking, create new commands without having to remember a lot of options, and decrease the time you spend typing, all of which should make you feel more productive.

Aliases can be “nested”. If you define `ls` as an alias of `ls -G` and `filesize` as an alias of `ls --size --human-readable -1`, your shell will unwrap both aliases and execute `ls -G --size --human-readable -1` when you type `filesize`.

When we're executing `filesize bin`, the shell will see that `filesize` is an alias for `ls --size --human-readable -1` and will actually execute the command `ls --size --human-readable -1 bin` behind the scenes. This simply is done by replacing the alias by its definition in the command itself. Aliases can however fall short if we want to do something a more complex than this.

For example, one of my favorite productivity tools is `mkcd`, which creates a directory and steps into it right after. It saves you from typing

```
$ mkdir new-dir
$ cd new-dir

```

where you can just type

An alias can't really help here, because we are talking about aliasing two commands with a single alias, which does not work. Enter *functions*.

## Functions

According to the `bash` `man` page:

> A shell function is an object that is called like a simple command and executes a compound command with a new set of positional parameters.

Let's see what that looks like in practice. A function is declared this way.

If your function is expecting arguments, these can be accessed by using `$n` where `n` is a number. For example, `$1` is the first function argument, `$2` its second argument, etc. With that in mind, we can now declare our `mkcd` function.

```
function mkcd {
    mkdir -p $1
    cd $1
}

```

Let's now see `mkcd` in action!

```
$ function mkcd {
    local target=$1
    mkdir -p $target
    cd $target
}
$ pwd
/home/br
$ mkcd test
$ pwd
/home/br/test

```

You can use the `typeset -f` command to see how a function was defined (or `which <function-name>`, although that only works in `zsh`).

```
$ typeset -f mkcd
mkcd () {
    mkdir -p $1
    cd $1
}

```

## Real Life Examples

These are some of the environment variables, aliases and functions I have defined for myself.

### Shorter Navigation Aliases

```
alias ..='cd ..'
alias ...='cd ../..'

```

### Colorize Commands Output

```
alias ls='ls --color=auto'
alias grep='grep --color=auto'
alias ip='ip --color'

```

### Alias Commands I Never Remember

```
# https://xkcd.com/1168/
alias untar='tar -zxvf'

```

### Have `$HOME/bin` Be Part of `PATH`

```
export PATH=$PATH:$HOME/bin

```

By extending my `PATH` this way, I can then put every single tool I create into `$HOME/bin` and have it be usable right-away.

### A Backup Function

```
function bak {
    cp -r $1 $1.bak
}

```

This function can be used to backup a file or directory. I regularly use this when I'm about to edit a critical file and I want to make sure I can revert my changes if needed.

### Password Generation Function

This function generate a password composed of alphanumeric characters, of default length 32.

```
$ function genpass {
    local passlen=${1:-32}
    # Note: LC_ALL=C is needed for macos compatibility
    LC_ALL=C tr -cd '[:alnum:]' < /dev/urandom | fold -w $passlen | head -n1
}
$ genpass
GQROc0tnABqfYH0qpMMwSPYFgcY7OANB
$ genpass 50
WkeQ14E8FIQZN7XlN7yPkYK4yhMOvpAuNzZivKwODNkskh0uq0

```

### The Weather in Your Terminal

```
function weather {
    curl "wttr.in/${1:-lyon}?m"
}

```

This function uses `curl` to send an HTTP request to the `http://wttr.in` website, that displays weather forecasts in a terminal-friendly way. So I can just type `weather mycity` and *voila*:

```
$ weather lyon
Weather report: lyon

     \   /     Sunny
      .-.      17 °C
   ― (   ) ―   ↖ 6 km/h
      `-'      10 km
     /   \     0.0 mm
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤  Sat 04 Apr ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│    \  /       Partly cloudy  │    \  /       Partly cloudy  │    \  /       Partly cloudy  │    \  /       Partly cloudy  │
│  _ /"".-.     7..8 °C        │  _ /"".-.     13 °C          │  _ /"".-.     13 °C          │  _ /"".-.     10..11 °C      │
│    \_(   ).   ← 5-6 km/h     │    \_(   ).   ↙ 5 km/h       │    \_(   ).   ← 5-10 km/h    │    \_(   ).   ↖ 8-17 km/h    │
│    /(___(__)  10 km          │    /(___(__)  10 km          │    /(___(__)  10 km          │    /(___(__)  10 km          │
│               0.0 mm | 0%    │               0.0 mm | 0%    │               0.0 mm | 0%    │               0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤  Sun 05 Apr ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│     \   /     Sunny          │     \   /     Sunny          │     \   /     Sunny          │    \  /       Partly cloudy  │
│      .-.      10..12 °C      │      .-.      16 °C          │      .-.      14..15 °C      │  _ /"".-.     10..12 °C      │
│   ― (   ) ―   ↖ 14-18 km/h   │   ― (   ) ―   ↑ 23-27 km/h   │   ― (   ) ―   ↑ 15-25 km/h   │    \_(   ).   ↑ 13-26 km/h   │
│      `-'      10 km          │      `-'      10 km          │      `-'      10 km          │    /(___(__)  10 km          │
│     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │               0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤  Mon 06 Apr ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│     \   /     Sunny          │     \   /     Sunny          │     \   /     Sunny          │     \   /     Clear          │
│      .-.      12..13 °C      │      .-.      16 °C          │      .-.      14..15 °C      │      .-.      11 °C          │
│   ― (   ) ―   ↖ 18-22 km/h   │   ― (   ) ―   ↑ 22-28 km/h   │   ― (   ) ―   ↑ 14-24 km/h   │   ― (   ) ―   ↑ 8-16 km/h    │
│      `-'      10 km          │      `-'      10 km          │      `-'      10 km          │      `-'      10 km          │
│     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
Location: Lyon, Métropole de Lyon, Circonscription départementale du Rhône, Auvergne-Rhône-Alpes, France [45.7578137,4.8320114]

```

## Summary

Environment variables, aliases and functions are simple yet powerful to change the shell's behavior into something that feels more intuitive. You feel like `nano` is not shiny enough and prefer using `vim` instead? Sure. Define `EDITOR=vim`. Any command interacting with an editor would then use `vim` instead of `nano`.

Aliases are a great way to reduce mental friction in the shell by hiding away complex commands, or just reducing the amount of typing you have to do. When aliases start being not powerful enough because you want to execute multiple commands, you can then have a look at functions instead.

Everything we have seen so far however had an ephemeral effect, as changes you made would disappear when you close your shell session. In the next chapter, we will go dive into how to persistently configure your shell to improve your day-to-day experience and productivity.

## Going Further

**3.1**: Write a `cat` alias that displays `meow` on screen.

**3.2**: Write a `restorebak` function that takes a filename as only argument and renames `$1.bak` into `$1`.

**3.3**: Unset the `PATH` environment variable and then export it back so that you can use `ls` again.

# Customizing Your Shell

---

![](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/header.jpg)

This article is part of a self-published book project by Balthazar Rouberol and [Etienne Brodu](https://etnbrd.com/), ex-roommates, friends and colleagues, aiming at empowering the up and coming generation of developers. We currently are hard at work on it!

If you are interested in the project, we invite you to join the [mailing list](https://balthazar-rouberol.us4.list-manage.com/subscribe?u=1f6080d496af07a836270ff1d&id=81ebd36adb)!

## Table of Contents

- [Which terminal should I use?](https://blog.balthazar-rouberol.com/customizing-your-shell#which-terminal-should-i-use)
- [What font should I use?](https://blog.balthazar-rouberol.com/customizing-your-shell#what-font-should-i-use)
- [What shell should I use?](https://blog.balthazar-rouberol.com/customizing-your-shell#what-shell-should-i-use)
- [Configuring your shell](https://blog.balthazar-rouberol.com/customizing-your-shell#configuring-your-shell)
- [Configuring your prompt](https://blog.balthazar-rouberol.com/customizing-your-shell#configuring-your-prompt)
- [Shell configuration frameworks](https://blog.balthazar-rouberol.com/customizing-your-shell#shell-configuration-frameworks)
- [Summary](https://blog.balthazar-rouberol.com/customizing-your-shell#summary)
- [Going further](https://blog.balthazar-rouberol.com/customizing-your-shell#going-further)

## Customizing Your Shell

It is very common for programmers to tweak and customize their terminal and shell for hours, add or write new plug-ins, all in pursuit of the “perfect environment” and an increase of productivity. Others, on the contrary, avoid tweaking their shell altogether in order to always get the same experience on every machine.

On a personal note, I tend to favor having a personalized shell as much as possible. I feel that sharing files between different computers is now a solved issue, and the benefits I get from having personalized my work environments are so great that I gladly pay the small price of synchronizing that configuration between my computers.

In that chapter, we will learn more about the shell and how to configure your terminal environment to make it work *for* you. Please note that some of the recommendations come from personal taste, and might not work for you nor suit you. We encourage you to explore and find what feels right, but we hope to at least nudge you in the right direction.

## Which Terminal Should I Use?

First off, if you are new to using the terminal, you might not have realized that it exists *multiple* terminal applications. MacOS comes with Terminal pre-installed, and most Linux distributions come with either xterm, Gnome-terminal or Konsole pre-installed, and there is a vast number of available alternatives.

I don't think there is a good, absolute and definitive answer when it comes to picking the “right” terminal application. You might get various answers depending who you ask. That being said, I can at least mention my own personal recommendations and preferences.

Whatever terminal you end up using, I think that it is really important you configure it to your liking and preferences. As a programmer, you will probably spend a great deal of time in your terminal, and for you to feel productive and empowered, it needs to work *for* you.

### Terminator

If you are running Linux, I personally favor Terminator<sup id="fnref:1"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:1">1</a></sup> over the default choices. It has several features I find useful:

- a tab system, allowing you to have multiple tab of terminal(s) within the same window
- a grid system, allowing you to have multiple terminals in the same tab

![I can work in multiple panes within the same tab, and have one tab per project](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/terminator.png) I can work in multiple panes within the same tab, and have one tab per project

Here are the terminator keyboard shortcuts I find the most useful:

| Shortcut | Action |
| --- | --- |
| Ctrl - Shift - E | split the screen vertically |
| Ctrl - Shift - O | split the screen horizontally |
| Ctrl - Shift - T | open a new tab |
| Ctrl - PageUp | switch to the next tab |
| Ctrl - PageDown | switch to the previous tab |
| Ctrl - N | open a new window |
| Ctrl - Shift - + | zoom in |
| Ctrl - Shift - \- | zoom out |
| Ctrl - D | close the current terminal |

### iTerm2

As far as macOS is concerned, I find the default terminal (plainly named Terminal) to be hard to use. The terminal that seems to be widely accepted by the macOS programming community is iTerm2<sup id="fnref:2"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:2">2</a></sup>. It has all of the features cited above, and many (many) more!

![iTerm2 looks similar to Terminator but can do much, much more](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/iterm2.png) iTerm2 looks similar to Terminator but can do much, much more

The iTerm2 keyboard shortcuts I find the most useful are:

| Shortcut | Action |
| --- | --- |
| Cmd - D | split the screen vertically |
| Cmd - Shift - D | split the screen horizontally |
| Cmd - T | open a new tab |
| Cmd - Shift - + | zoom in |
| Cmd - Shift - \- | zoom out |
| Cmd - N | open a new window |
| Ctrl - D | close the current terminal |

The following sections go over some non-default iTerm2 settings that I find convenient. Again, these are my preference and are in no way prescriptive. Feel free to discard them if you want.

#### Open File Shortcut

One of the iTerm2 features I enjoy is the ability of using Cmd + mouse click on a file path or an URL, to open the resource with the default associated program. For example, it will open an URL in your browser, a path to a local PDF file with Preview, a text file with your preferred text editor, etc.

![By enabling this feature, you will be able to open a file using a graphical application from your terminal](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/iterm2-pointer-pref.png) By enabling this feature, you will be able to open a file using a graphical application from your terminal

#### Intuitive Location for New Terminals

Another tweak I've done to iTerm2 was changing the working directory new terminals will open into by default. What I wanted was

- open a new terminal window in my home directory
- open a new terminal tab in my home directory
- open a new terminal split pane in the previous session's directory

I did this because I oftentimes found myself splitting the current tab when I want to run multiple commands within the same project, and I had to `cd` into the project directory every time I did a pane split.

![I reduced the time I spent cd-ing into project directories with these settings. Preferences > Profiles > General > Working Directory > Advanced Configuration > Edit](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/iterm2-advanced-pref.png) I reduced the time I spent `cd`\-ing into project directories with these settings. Preferences > Profiles > General > Working Directory > Advanced Configuration > Edit

## What Font Should I Use?

Using a font you enjoy is paramount. If you spend a lot of time reading and writing in your terminal, you might as well do it using a font that feels right to you.

I personally really enjoy the Fira Code<sup id="fnref:3"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:3">3</a></sup> font, both in my text editor and my terminal. Not only does it look really nice on the eye, but it also contains a set of *ligatures* for multi character combinations, such as `!` and `=` rendered in a single character, allowing you to read code and decode symbols more easily.

![Example of rendered character ligatures](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/ligature-code-example.png) Example of rendered character ligatures

Note that not all terminals support fonts with ligatures. For example, iTerm2 does but Terminator does not.

While Fira Code has my preference, there are other well-designed fonts including ligatures, such as JetBrains Mono.<sup id="fnref:4"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:4">4</a></sup>

## What Shell Should I Use?

We have hinted at it until now: `bash` is not the only shell out there. You are free to use other shells if you want, such as `zsh`, `fish`, `nushell`, … As it was the case with terminals, the “good” terminal really depends on your definition of “good”. If you deeply care about using the same shell on every machine you work on, then `bash` is possibly for you. It has been around since 1989, is stable, mature and is the default shell on almost<sup id="fnref:5"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:5">5</a></sup> every UNIX system out there.

When researching this book, I was surprised to learn that `zsh` (or the Z-shell) wasn't really the last “kid on the block” either, as it was first released in 1990, just a year after the first stable bash release! You can expect the same level of stability, maturity and even syntax (to a large extent, except when it comes to configuration) than bash.

I personally think `zsh` really shines by providing a powerful default auto-completion experience, as well as more configuration options. As `zsh` is compatible with `bash`'s own syntax, I encourage you to try them until you feel comfortable with one or the other.

The `fish`<sup id="fnref:6"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:6">6</a></sup> shell takes a radical turn from `bash` or `zsh` by providing an incompatible but “simple and clean” syntax, an extremely powerful command suggestion system, and an interactive configuration wizard.

If you are getting started with using the shell, my personal recommendation is to stick to `bash` or `zsh` and experiment with other shells to see what value they bring once you feel more confident.

### Changing Your Default Shell

The `chsh` (standing for *change shell*) command allows you to change your default shell.

**Examples**:

```
# Switching to bash by default
$ chsh -s /bin/bash

```

```
# Switching to zsh by default
$ chsh -s /bin/zsh

```

Once you have run `chsh`, any new terminal window you open will run your new default shell.

## Configuring Your Shell

Up until now, every example we have seen have defined environment variables, aliases and functions directly in the shell. However, if we closed that shell, all of these changes would be undone and we would have to start again the next time we open a new one. Fortunately, all of these settings can be persisted in a *configuration file*. Adding aliases, environment variables and functions to that file will make sure they get imported every time you open a new shell.

These files usually reside in your home directory, and are named `.bashrc` for bash, and `.zshrc` for zsh.

```
$ cat ~/.zshrc
export EDITOR=vim
export PATH=$HOME/bin:$PATH

alias ls='ls -G'
alias ..='cd ..'
alias ...='cd ../..'

function mkcd {
    local target=$1
    mkdir -p "$target"
    cd $target
}

```

After adding anything to your shell configuration file, you need to run `source ~/.zshrc` (or `source ~/.bashrc`, depending on your shell). The `source` built-in command reads and executes commands from the argument file name in the current shell environment. Said in another way, running `source ~/.<file>` will cause the shell to reload its configuration.

`rc` stands for *run commands*. Indeed, when you `source` your configuration file, you will run the commands it contains. The subtlety with `source` is that it executes the argument script within your *current* shell, meaning any sourced commands will have a side-effect on your running shell.

If you can never remember a given command's options, or if you always find yourself typing a group of commands, I encourage you to define aliases and functions in your shell configuration file. They will allow you to feel more productive day after day, especially so if the alias and tools are abstracting complex commands.

The previous chapter ended with some real-life examples of alias and functions. Feel free to add them to your shell configuration file.

## Configuring Your Prompt

Configuring your prompt is a very good way to make the shell work for you as much as possible, by providing you with useful context, such as the time of day, whether the last command was successful, your current working directory… While they can provide context and information to you, they will carry that context to anyone you copy and paste a command and associated output to.

Configuring your prompt is done by changing the value of the `PS1` environment variable.

```
$ export PS1="MY COOL PROMPT $"
MY COOL PROMPT $

```

I think we can agree that `MY COOL PROMPT` is not as informative as it could, so let's change it to put our prompt to work. As the prompt configuration work slightly different between `bash` and `zsh`, we will address both cases in two different sections.

### Configuring Your Bash Prompt

The `PS1` environment variable can be defined by using a mix and match of both regular and special characters. The regular characters are just displayed as-is, whereas the backslash-escaped special characters are interpreted by bash at the time `PS1` is displayed and replaced by the associated value. The most useful special characters are defined as follows.

| Character | Meaning |
| --- | --- |
| `\h` | The hostname up to the first dot |
| `\t` | The current time, in 24-hour HH:MM:SS format |
| `\u` | The current user's username |
| `\w` | The full current working directory (`$HOME` rendered as `~`) |
| `\W` | The basename of the current working directory (`$HOME` rendered as `~`) |
| `\n` | A new line |

These special characters are evaluated every-time the prompt is displayed to make sure you always get the most up-to-date context.

The `PROMPTING` section of the `bash` manual contains the full list of backslash-escaped special characters.

**Examples**

```
$ export PS1='\u@\h \W $'
br@morenika ~ $

```

```
$ export PS1='[\t] \u@\h \W $'
[13:33:55] br@morenika ~ $

```

```
$ export PS1='[\t \u@\h:\w]\n>>> '
[13:57:55 br@morenika:~/code]
>>>

```

You can use online tools such as ezprompt<sup id="fnref:7"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:7">7</a></sup> to try different configurations until you find something you like.

Whatever `PS1` value you settle with should be persisted and exported in your `.bashrc` configuration file.

### Configuring Your Zsh Prompt

`zsh` exposes a bit more options than `bash` when it comes to prompt configuration. Both `PS1` and `PROMPT` environment variable can be set to the same effect, if you find `PROMPT` more explicit.

Instead of being backslash-escaped, zsh's special characters are prefixed by `%`, and are called *prompt sequences*. The most useful are detailed here.

| Sequence | Meaning |
| --- | --- |
| `%m` | The hostname up to the first dot |
| `%*` | The current time, in 24-hour HH:MM:SS format |
| `%n` | The current user's username |
| `%~` | The full current working directory (`$HOME` rendered as `~`) |
| `%1~` | The basename of the current working directory (`$HOME` rendered as `~`) |
| `%?` | The exit status of the last command executed |
| `%%` | A % |
| `$'\n'` | A new line |
| `%B (%b)` | Start (stop) bold font mode |
| `%F (%f)` | Start (stop) using a given foreground color, if supported by the terminal |

You will find the full list of prompt sequences in the zsh documentation<sup id="fnref:8"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:8">8</a></sup>.

**Examples**

```
$ export PROMPT='%n@%m %~ $ '
br@morenika ~/code $

```

```
$ export PROMPT='[%*] %n@%m %~ $ '
[23:38] br@morenika ~/code $

```

```
$ export PROMPT="[%* %n@%m %~]"$'\n'">>> "
[23:41 br@morenika ~/code/izk]
>>>

```

```
$ export PROMPT="[%* %n@%m %1~]"$'\n'"%% "
[23:41 br@morenika izk]
%

```

`zsh` goes even further by letting you define the content of a right-sided prompt, through the `RPROMPT` environment variable, which uses the same syntax as `PROMPT`.

**Example**

```
$ export PROMPT='%~ $ '; export RPROMPT='%*'
~/code $                                              21:04:00

```

To make sure your changes are persisted, `PROMPT` and `RPROMPT` should be exported in your `.zshrc` configuration file.

### Adding Colors

Adding color is a good way to spice up your prompt as well as providing some visual context. You can use color to indicate whether you are running with super-user privileges, if the last command succeeded or failed, or simply colorized each individual part of your prompt (username, hostname, etc) in a different way to make it even simpler to parse.

#### Adding Color to Your Bash Prompt

Bash allows you to style elements of your prompt by using 3-bit ANSI<sup id="fnref:9"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:9">9</a></sup> codes defining a zone associated with a potential effect, foreground color and background color.

Each effect, background or foreground color has an associated code, described in the following tables. The combination of these parameters is called Select Graphic Rendition, which is defined as a semicolon (;) separated list of codes.

| Effect | ANSI Code |
| --- | --- |
| Normal | `0` |
| Bold | `1` |
| Faint | `2` |
| Italic | `3` |
| Underline | `4` |
| Strike through | `9` |

| Background Color | ANSI Code |
| --- | --- |
| Red | `41` |
| Green | `42` |
| Brown | `43` |
| Blue | `44` |
| Purple | `45` |
| Cyan | `46` |
| White | `47` |
| Bright black | `100` |
| Bright red | `101` |
| Bright green | `102` |
| Bright brown | `103` |
| Bright blue | `104` |
| Bright purple | `105` |
| Bright cyan | `106` |
| Bright white | `107` |

| Foreground Color | ANSI Code |
| --- | --- |
| Black | `30` |
| Red | `31` |
| Green | `32` |
| Brown | `33` |
| Blue | `34` |
| Purple | `35` |
| Cyan | `36` |
| White | `37` |
| Bright black | `90` |
| Bright red | `91` |
| Bright green | `92` |
| Bright brown | `93` |
| Bright blue | `94` |
| Bright purple | `95` |
| Bright cyan | `96` |
| Bright white | `97` |

**Examples of SGRs**

- blue text: `34`
- bold green text: `1;32`
- purple text on a white background: `35;47`
- bold red text on a bright cyan background: `1;31;106`
- bold and striked-through brown text on a green background `1;9;33;42`

To define colorized zones in your bash prompt, use the following (granted, ugly) syntax:

**Examples**

```
$ export PS1='[\t] \u@\h \W \e[32m$\e[m '

```

![The $ sign is now displayed in green](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/green-prompt.png) The `$` sign is now displayed in green

```
$ export PS1='\e[31m\u\e[m@\e[32m\h\e[m \e[36m\W\e[m $ '

```

![The username is in red, the hostname in green and the path is in cyan. ](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/bash-colors-prompt.png) The username is in red, the hostname in green and the path is in cyan.

##### Color Palettes

Notice how an ANSI code only maps to a color name? That's because it is up to your *terminal* to interpret and render that color name into an actual color, meaning that the same prompt configuration could be rendered differently on two different terminals.

Mapping ANSI color names to actual RGB colors is done through what is called *color palettes*.

Following are two different color schemes, as well as the associated rendered prompt, both using the same `PS1` value, used in the previous example.

![](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/color-scheme-solarized-dark-ansi.png)

![The popular Solarized Dark color scheme](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/color-scheme-solarized-dark.png) The popular Solarized Dark color scheme

![](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/color-scheme-pastel-ansi.png)

![The Pastel (Dark Background) color scheme](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/color-scheme-pastel-dark-shell.png) The Pastel (Dark Background) color scheme

As you can see, these both look quite different from the prompt displayed in the previous screenshot, even though the underlying prompt configuration is exactly the same. This means that, even if using 16 colors can feel limiting, you actually can map these colors to any color you like. The ANSI color system just prevents you from having more than 16 *different* colors in your prompt.

I recommend you to have a look at the `mbadolato/iTerm2-Color-Schemes`<sup id="fnref:10"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:10">10</a></sup> project, showcasing popular color palettes and providing you with the configuration files allowing you to used them in many terminal applications (and not just iTerm2 contrary to what its name suggests).

##### Up to 256 Colors

As computers eventually started to have 256 colors graphics card, a 8 bit ANSI code scheme was introduced, allowing the user to render 256 colors in their terminal, instead of 16.

The 8-bit ANSI code syntax is `\e[38;5;n` where the colors associated with each value of `n` between 0 and 255 are represented in the following table<sup id="fnref:11"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:11">11</a></sup>.

![The 8-bit ANSI code allows you to render more than the initial 16 available colors](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/256col-table.png) The 8-bit ANSI code allows you to render more than the initial 16 available colors

**Examples**

```
# Using 256-bit ANSI codes
$ TIME="[\e[38;5;33m\t\e[m]"  # blue
$ USERNAME="\e[38;5;200m\u\e[m"  # pink
$ HOSTNAME="\e[38;5;139m\h\e[m"  # purple
$ WORKDIR="\W"  # no color
$ DOLLAR="\e[38;5;41m$\e[m"  # green
$ export PS1="${TIME} ${USERNAME}@${HOSTNAME} ${PTH} ${DOLLAR} "

```

![These ANSI codes sure are awful to read but they make for pretty colors ](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/256col-prompt.png) These ANSI codes sure are awful to read but they make for pretty colors

Not all terminals support 256 colors, but most of the modern ones should. To this day, GNOME Terminal, Konsole, Terminator, XFCE4 Terminal, iTerm2, Terminal (macOS) and tmux all support 256 colors.

Contrary to the 3-bit ANSI codes, the 8-bit codes are insensitive to color schemes changes, as shown in the following examples, both re-using the same `PS1` configuration than in the previous screenshot.

![](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/color-scheme-solarized-dark-256.png)

![The colors remain unchanged](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/color-scheme-pastel-dark-256.png) The colors remain unchanged

#### Adding Color to Your Zsh Prompt

Everything we've explained in the previous section is still valid for `zsh`: you can use 3 or 8 bit ANSI color codes just fine. However, `zsh` also provides you with a much easier and readable color system:

- each color can be represented as either `black`, `red`, `green`, `yellow`, `blue`, `magenta`, `cyan` or `white`, or a number between 0 and 255
- `%F{color}Text%f`: changes the `Text` foreground color to `color`
- `%K{color}Text%k`: changes the `Text` background color to `color`
- `%BText%b`: displays `Text` in boldface
- `%UText%u`: underlines `Text`

**Example**

![The current working directory in blue and the dollar sign in bold pink](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/zsh-colors-prompt.png) The current working directory in blue and the dollar sign in bold pink

### Displaying Dynamic Data in the Prompt

We can make our prompt display dynamic context to make it even more informative. To do this, we can execute a function as part of our `PS1` environment variable. The shell will call that function every time it renders the prompt.

The idea is to be able to have as much information as possible in your prompt at the ready, but *only when necessary*.

#### Displaying Dynamic Data in Bash

Let's say that we want to colorize the `$` of our prompt in green if the last command was successful, and in red if it failed. We can wrap that logic into the following `colorized_prompt` bash function, and have it called every time `PS1` is rendered by including `$(colorized_prompt)` in the environment variable.

The `$(colorized_prompt)` syntax means "call the `colorize_prompt` function", and will be expanded into the output of the function (what it prints), which will contain ASCII color codes colorizing the prompt.

```
function colorized_prompt {
    # Check if last command exit code equals 0
    if (($?)); then
        printf "\e[32m$\e[m"
    else
        printf "\e[31m$\e[m"
    fi

}
export PS1='[\t] \W $(colorized_prompt) '

```

`$?` is a special bash parameter that expands to the *exit status* of the previously executed command. The norm is to have an exit status of 0 if the command executed successfully, and any other exit status indicates an error.

```
$ pwd
/home/br
$ echo $?
0
$ cmdnotfound
bash: cmdnotfound: command not found
echo $?
127

```

The syntax `if (($?)); then` thus translates to “if the last command executed successfully, then…”.

![The prompt is green after a successful command and red after a failed one](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/red-green-prompt.png) The prompt is green after a successful command and red after a failed one

#### Displaying Dynamic Data in Zsh

Dynamic data can be injected in your prompt the same way than in bash, by executing functions at rendering time. `zsh` however provides you with *ternary conditionals*, that is to say expressions that either evaluate to one value or the other depending on a condition, to reach the same goal. A ternary conditional has the following syntax

```
%(<condition>.<success value>.<failure value>)

```

If the condition is true, then the expression is evaluated to the success value. On the other hand, if the condition is false, the expression will be evaluated to the failure value.

You can read a ternary conditional as *if condition, then, else*. It's actually a common pattern called *ternary expression* you might encounter in many programming languages.

Here is a list of useful built-in conditions provided by `zsh`.

| Condition | Meaning |
| --- | --- |
| `n?` | True if the previous command exited with the exit status *n* |
| `nd` | True if the day of the month is equal to n |
| `nw` | True if the day of the week is equal to n (Sunday = 0). |
| `!` | True if the shell is running with super-user privileges (as the `root` user) |

**Examples**

```
$ export PROMPT='%F{%(0?.green.red)}$ %f'

```

![Displays a dollar prompt in green if the last command was successful, or red if it failed](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/zsh-ternary-red-green.png) Displays a dollar prompt in green if the last command was successful, or red if it failed

```
$ export PROMPT='%* %1~ %(!.#.$) '

```

![Display a dollar sign if you run your regular user, and a hash if you are running in super-user mode](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/zsh-ternary-root.png) Display a dollar sign if you run your regular user, and a hash if you are running in super-user mode

The full list of ternary conditionals is available in the zsh documentation<sup id="fnref:12"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:12">12</a></sup>.

### Adding Emoji to Your Prompt

Modern terminal support non-ASCII characters, such as emoji. Like colors, they can be convenient to convey information in a very space-efficient fashion.

For example, during the process of writing that book, I displayed the associated total word count in my prompt to keep me motivated. That word count would however only be displayed when I was located in the root directory of the project, in the spirit of only displaying context when necessary.

![](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/word-count-emoji.png)

## Shell Configuration Frameworks

Up until now, we have seen how to tailor your prompt by adding colors, context, dynamic information computed on-the-fly. While you can certainly spend hours customizing up to “perfection” (trust me, I have been there…), you can also take another route and benefit from other people's work, using a shell configuration framework.

These frameworks provide you with a large choice of prompt themes, helpers, options, additional command auto-completions, plug-ins, and are regularly updated by a community of developers around the world.

To this day, the most famous `zsh` configuration frameworks are Oh My Zsh<sup id="fnref:13"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:13">13</a></sup> and Prezto.<sup id="fnref:14"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:14">14</a></sup> While we can't fully attribute `zsh`'s success to them (Oh My Zsh was first released around 2010, 20 years after zsh's first release), they certainly have helped in driving community adoption in the last couple of years<sup id="fnref:15"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:15">15</a></sup>.

![Comparison of Google Trends associated with zsh and Oh My Zsh](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/zsh-adoption.png) Comparison of Google Trends associated with zsh and Oh My Zsh

We will introduce you to the concepts behind Oh My Zsh, but it will then be up to you to explore, and select a theme as well as plug-ins you like (or even not use them at all!). After all, it is *your* development environment, and henceforth, your choice.

`bash` has a similar framework, inspired by Oh My Zsh, called `bash-it`.<sup id="fnref:16"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:16">16</a></sup> We won't cover it in details but we encourage you to look at it if don't feel like using `zsh` but still want to use a configuration framework.

### Oh My Zsh

Quoting the official website,

> Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plug-ins, themes, and a few things that make you shout…

To install it, run the following command in a shell, which will download an installation script, and run it on your computer.

```
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

```

Once the script has finished running, you should see a message stating that Oh My Zsh has been installed, and that plug-ins, themes and options should be enabled by changing the configuration living under `~/.zshrc`.

Before, we do, let's inspect our environment variables, to see how Oh My Zsh configures itself.

```
$ printenv | grep ZSH
ZSH=/home/br/.oh-my-zsh

```

That `ZSH` environment variable points to the Oh My Zsh installation directory. The framework also injected a couple of other variables defining specific configuration values.

```
$ set | grep ZSH
ZSH=/home/br/.oh-my-zsh
ZSH_ARGZERO=zsh
ZSH_CACHE_DIR=/home/br/.oh-my-zsh/cache
ZSH_COMPDUMP=/home/br/.zcompdump-morenika-5.7.1
ZSH_CUSTOM=/home/br/.oh-my-zsh/custom
ZSH_EVAL_CONTEXT=toplevel
ZSH_NAME=zsh
ZSH_PATCHLEVEL=zsh-5.7.1-0-g8b89d0d
ZSH_SPECTRUM_TEXT='Arma virumque cano Troiae qui primus ab oris'
ZSH_SUBSHELL=1
ZSH_THEME=robbyrussell
ZSH_VERSION=5.7.1

```

#### Picking a Theme

We can see that the default theme is `robbyrussell` (Robby Russell<sup id="fnref:17"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:17">17</a></sup> is the creator of Oh My Zsh). The full list of available themes is available online<sup id="fnref:18"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:18">18</a></sup>, along with screenshots.

You can also get the list by running the following command, as all themes are defined in `$ZSH/themes`.

```
$ ls -1 $ZSH/themes | sed 's/.zsh-theme//'
3den
adben
af-magic
afowler
...

```

I suggest you scroll through the themes wiki, or simply pick a theme at random from the previous command output, edit your `~/.zshrc` configuration file by updating the value of the `ZSH_THEME` variable, and run `source ~/.zshrc` to reload it. That will get you a whole new shell theme!

Feel free to rinse and repeat until you find a theme that suits you. In the case where no built-in theme finds grace in your eyes, you can also explore the external theme wiki<sup id="fnref:19"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:19">19</a></sup>. If you find an external theme you like, download its associated `.zsh-theme` file, and place it under `$ZSH/themes`, then edit `~/.zshrc`, and update the `ZSH_THEME` accordingly.

If you want to further personalize a theme using some of the techniques we covered in that chapter, I'd advise you clone it and maintain a separate version, as your tweaks might get overridden at the next theme update.

Export the `ZSH_CUSTOM` environment variable to `$ZSH/custom`, then run the following commands.

```
$ mkdir -p $ZSH/custom/themes
$ cp $ZSH/themes/$ZSH_THEME.zsh-theme $ZSH/custom/themes/$ZSH_THEME-custom.zsh-theme

```

Then add `ZSH_THEME=<old zsh theme>-custom` to your `~/.zshrc`.

#### Useful Configuration Options

Oh My Zsh has a couple of options you can enable or disable by editing `~/.zshrc`. I suggest you take a look at them and choose what to activate. Here are some personal recommendations.

##### Automatic Command Correction

zsh can suggest a command correction if it detects a mistyped command. To enable the automatic command correction, add `ENABLE_AUTO_CORRECTION='true'` to `~/.zshrc`.

```
$ sl
zsh: correct 'sl' to 'ls' [nyae]? y
Android                bin   Desktop    Downloads  Firefox_wallpaper.png  Pictures
AndroidStudioProjects  code  Documents  Dropbox    Music                  Videos

```

The 4 options are:

- `n` (no): run the mistyped command
- `y` (yes): run the suggested command
- `a` (abort): stop and do nothing
- `e` (edit): edit your command before re-running it

zsh's auto-correction feature can sometimes be over-zealous and is not to everyone's liking<sup id="fnref:20"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:20">20</a></sup>. If you end up repeatedly fighting it for a given command (e.g. `git status` wrongly autocorrected to `git stats`), you can define an alias for the command by prefixing it with `nocorrect`.

```
alias git status='nocorrect git status'

```

##### Automatic Oh My Zsh Updates

To make sure you regularly get new plug-ins and bug fixes, Oh My Zsh can automatically and regularly update itself. To do so, set the following options in `~/.zshrc`:

- `DISABLE_UPDATE_PROMPT=true`: update Oh My Zsh without asking for confirmation
- `UPDATE_ZSH_DAYS=30`: update Oh My Zsh every 30 days

#### Add Plug-ins

Oh My Zsh comes with more than 250 plug-ins, each of them either defining aliases or improved auto-completion for a given set of commands. Refer to the Oh My Zsh wiki page<sup id="fnref:21"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:21">21</a></sup> to see the full list of available plug-ins. To enable a given plug-in, add its name to the `plugins` list in `~/.zshrc`, then run `source ~/.zshrc`.

**Example**:

```
- plugins=(git)
+ plugins=(git python)

```

If you regularly use a command listed in the plug-in wiki page, you should probably try to enable the associated plug-in! I however suggest enabling the following general-purpose plug-ins.

- `common-aliases`<sup id="fnref:22"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:22">22</a></sup>: Collection of useful aliases, not enabled by default since they may change some user defined aliases
- `colored-man-pages`: colorize `man` pages

![Colorized man pages are much easier to read!](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/colored-man-pages.png) Colorized man pages are much easier to read!

- `extract`: define an `extract` alias that can extract any type of archive (.zip, .tar.gz, .bzip, etc)<sup id="fnref:23"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:23">23</a></sup>

The following plug-ins are not provided by default, I find them so useful that I suggest you install them and give them a try.

- `zsh-autosuggestions`<sup id="fnref:24"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:24">24</a></sup>: emulate the `fish` autosuggestion by suggesting commands as you type them, saving you from using Ctrl - R to look into your shell history. Any suggestion can be accepted by hitting → or ignored by just continuing typing.

![I just typed ls and I immediately get a completion suggestion](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/zsh-autosuggestion-before.png) I just typed `ls` and I immediately get a completion suggestion

![Suggestion accepted!](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/zsh-autosuggestion-after.png) Suggestion accepted!

- `zsh-syntax-highlighting`<sup id="fnref:25"><a href="https://blog.balthazar-rouberol.com/customizing-your-shell#fn:25">25</a></sup>: provide syntax highlighting within the zsh command line. It also colorizes the name of the command you type in green if it is found, and in red if not.

![ls is a valid command](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/zsh-syntax-highlight-prompt-cmd-green.png) `ls` is a valid command

![cmdnotfound is not](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/customize-shell/zsh-syntax-highlight-prompt-cmd-red.png) `cmdnotfound` is not

#### Uninstalling Oh My Zsh

If you find that Oh My Zsh isn't for you, you can uninstall it by running the `uninstall_oh_my_zsh` function. Your previous configuration will be restored.

## Summary

I strongly believe that learning how to configure and personalize your own shell is an important part of becoming a developer. I'd even go as far as calling it a ritual. On a personal level, it helped me overcome the almost mystic reputation of the terminal by making it my own.

Configuring your shell might never really be fully completed. Do you find yourself executing a long command repeatedly? Make it an alias. If an alias does not cut it, or if it should take arguments, write a shell function instead. Are you oftentimes wondering on which branch, project or profile you are currently running? Add it to your prompt. If your prompt starts to feel a little crowded, you might be able to condense it by using colors and emoji.

Making your own tools and customizing your shell is an investment, but it is also an inherent part of being a software developer, which will allow you to do more, faster, and will help you feel more at home in your shell. It's also quite a bit of fun!

## Going Further

**4.1**: Look into your terminal's preferences and try to change the color scheme, or remap ANSI colors to different RGB colors.

**4.2**: Try different fonts, such as `Source Code Pro`, `Fira Code Pro`, `Inconsolata` or `Jetbrains Mono` and pick the one you like most

**4.3**: Explore your terminal preferences, and experiment with different settings.

**4.4**: Try to change the colors of the different sections of your prompt

# Shell Productivity Tips and Tricks

---

![](https://balthazar-rouberol-blog.s3.eu-west-3.amazonaws.com/shell-productivity/header.jpg)

This article is part of a self-published book project by Balthazar Rouberol and [Etienne Brodu](https://etnbrd.com/), ex-roommates, friends and colleagues, aiming at empowering the up and coming generation of developers. We currently are hard at work on it!

If you are interested in the project, we invite you to join the [mailing list](https://balthazar-rouberol.us4.list-manage.com/subscribe?u=1f6080d496af07a836270ff1d&id=81ebd36adb)!

## Table of Contents

- [Tab completion](https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#tab-completion)
- [Keyboard shortcuts](https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#keyboard-shortcuts)
- [Navigating through history](https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#navigating-through-history)
- [Shell expansions](https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#shell-expansions)
- [Real-life examples](https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#real-life-examples)
- [Summary](https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#summary)
- [Going further](https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#going-further)

## Shell Productivity Tips

I estimate that I spend around 50% of my day working in my text editor and my terminal. Any way I can get more productive in these environments has a direct and measurable impact on my daily productivity as a whole.

If you spend a good chunk of your day repeatedly hitting the left and right arrow keys to navigate in long commands or correct typos, or hitting the up or down arrow keys to navigate your command history, this chapter should help you get more done quicker. We will cover some shell features you can leverage to make your shell do more of the work for you.

On a personal level, I probably use some of these up to 30 times a day, sometimes even without thinking about it, and it gives me a real sense of ownership of my tool.

In the immortal words of Kimberly “Sweet Brown” Wilkins:

> Ain't nobody got time for that.

## Tab Completion

When you are typing in your shell, I suggest you treat the Tab key as a superpower. Indeed, the same way your phone keyboard can autocomplete words for you, so can your shell. It can suggest completions of command names and even command arguments or options! This works by pressing Tab (twice for `bash` and once for `zsh`).

One of the reasons `zsh` might be favored over `bash` is its more powerful auto-completion system, giving more results out-of-the-box and allowing you to navigate through the auto-completion options.

Here is an example of `bash` auto-completing a command name:

Here is an example of `bash` auto-completing a command argument:

```
$ man mkd<Tab>
mkdir         mkdirat       mkdtemp       mkdtempat_np

```

And finally, an example of `bash` auto-completing a command option:

```
$ python -<Tab>
-    -3   -B   -E   -O   -OO  -Q   -R   -S   -V   -W
-b   -c   -d   -h   -i   -m   -s   -t   -u   -v   -x

```

I suggest you get used to using auto-completion as much as possible. It can save you keystrokes, as well as make you discover command options you didn't know about.

Pro-tip: if you are using bash, you can get install the `bash-completion`<sup id="fnref:1"><a href="https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#fn:1">1</a></sup> package (using your system package-manager) in order to enable auto-completion for a wide variety of commands that do not support it out-of-the-box.

## Keyboard Shortcuts

The shell uses a library called `readline`<sup id="fnref:2"><a href="https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#fn:2">2</a></sup> to provide you with many keyboard shortcuts to navigate, edit, cut, paste, search, etc, in the command line. Mastering these will help to dramatically increase your efficiency, instead of copying and pasting with your mouse, and navigating the command with the ↑ and ↓ arrow keys.

The default shortcuts are inspired by the `emacs`<sup id="fnref:3"><a href="https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#fn:3">3</a></sup> terminal-based text editor. If you are already familiar with it, a lot of the default `readline` shortcuts might feel familiar. `emacs` isn't the only famous text editor in the history of computers though: another one, dating back from 1976, is `vi`.<sup id="fnref:4"><a href="https://blog.balthazar-rouberol.com/shell-productivity-tips-and-tricks#fn:4">4</a></sup> `vi` and `emacs` are designed in two very different ways, and have two very different logics. It is possible that one might “click” more than the other for you. If you happen to be familiar with the `vi` editor and are accustomed to its navigation system, you can replicate it in your shell as well by adding `set -o vi` in your shell configuration file. If you are using `zsh` with the Oh My Zsh framework that we introduced in the previous chapter, you can also use the `vi-mode` plugin to do this.

The advantage of using the same navigation logic and shortcuts in your text editor and your terminal is that is blurs the line between both, and brings consistency to your terminal environment. If you have no clue how `emacs` or `vi` work though, I would probably suggest you don't worry about all this for now and experiment with the default terminal shortcuts.

### Navigating the Current Line

The following navigation shortcuts allow you to move quickly your cursor in the current command saving you from relying solely on the → and ← arrows.

| Navigation | Shortcut |
| --- | --- |
| Go to beginning of line | Ctrl - A |
| Go to end of line | Ctrl - E |
| Go to next word | Alt - F |
| Go to previous word | Alt - B |
| Toggle your cursor between its current position and the beginning of line | Ctrl - X - X |

If you however prefer using the `vi` navigation system, you will first need to type Esc to switch from the *Insertion* mode to an emulation of `vi`'s *normal* mode, in which you can navigate in your text using the following shortcuts:

| Navigation | Shortcut |
| --- | --- |
| Go to beginning of line | ^ |
| Go to end of line | $ |
| Go to next word | w |
| Go to previous word | b |
| Move to the end of the previous word | e |

You can go back to editing your command line by hitting the `i` key.

### Deleting and Editing Text

These shortcuts allow you to quickly edit the current command more efficiently than by just using the Delete key.

| Edition | Shortcut |
| --- | --- |
| Delete current character | Ctrl - D |
| Delete previous word | Ctrl - W |
| Delete next word | Alt - D |
| Edit the current command in your text editor | Ctrl - X Ctrl - E |
| Undo previous action(s) | Ctrl - \- |

The equivalent `vi`\-style shortcuts are:

| Edition | Shortcut |
| --- | --- |
| Replace current character by another (ex: *e*) | r - e |
| Delete current character | x |
| Delete previous word | d - b |
| Delete next word | d - w |
| Edit the current command in your text editor | v |
| Undo previous action(s) | u |

### Cutting and Pasting

The shell provides you with shortcuts to cut and paste commands quickly without using your mouse.

| Action | Shortcut |
| --- | --- |
| Cut current word before the cursor | Ctrl - W |
| Cut from cursor to end of line | Ctrl - K |
| Cut from cursor to start of line | Ctrl - U |
| Paste the cut buffer at current position | Ctrl - Y |

The equivalent `vi`\-style shortcuts are:

| Action | Shortcut |
| --- | --- |
| Cut current word before the cursor | d - w |
| Cut from cursor to end of line | d - $ |
| Cut from cursor to start of line | d - ^ |
| Paste the cut buffer at current position | p |

### Controlling the Terminal

Finally, these shortcuts will let you interact with the terminal itself.

| Action | Shortcut | Equivalent command |
| --- | --- | --- |
| Clear the terminal screen | Ctrl - L | `clear` |
| Close the terminal screen | Ctrl - D | `exit` |
| Send current command to the background. | Ctrl - Z |  |

Even mastering *some* of these shortcuts should make you immensely more productive at typing commands and navigating command-line interfaces. I suggest you take time to experiment until you feel more accustomed with them. I can guarantee that you will feel the productivity boost!

### A Unified Command-line Editing Experience

These shortcuts do not just work in your shell, but in any application using the `readline` library to allow the user to type and edit commands. Learning these shortcuts will thus make you productive in all types of command lines that you might encounter in your career, such as `python`, `irb`, `sqlite3`, etc.

To make sure you get a smooth and homogeneous editing experience in all command lines you use in your system, you can set your preferred mode in the `readline` configuration file itself.

```
$ cat ~/.inputrc
set editing-mode vi  # or emacs

```

## Navigating Through History

If you find yourself typing a certain command times and times again, you should probably be aware of how to navigate and search your shell history, in order to save time and keystrokes.

While the obvious way to re-execute a previous command might seem to just bash on the ↑ key until you find the command you want, there are faster and smarter ways to accomplish this.

### Searching the History

A very useful and time-saving trick is searching for a command into your shell history instead of re-typing it from scratch. You can search your command history by typing Ctrl - R which opens a `reverse-i-search` (backwards search) prompt, in which you can search for previously executed command containing a given search pattern.

Type Ctrl - R to navigate through the results, until you find the one you were looking for and type the Enter key to execute it.

```
$ <Ctrl-R>
(reverse-i-search): echo <Ctrl-R> <Enter>
$ echo "hello world"
hello world

```

If you want to stop the search, either hit Ctrl - C or Ctrl - G to be sent back into the regular shell prompt.

History search works by looking into the shell history file (`~/.bash_history` for `bash` and `~/.zsh_history` for `zsh` by default). Every time you execute a command, it will be added to your shell history file (with a maximum number of retained commands defined by the `HISTSIZE` environment variable).

The location of your shell history file can be configured by setting the `HISTFILE` environment variable.

### Rewriting History

If you want to remove a sensitive command from your history, you can simply edit your `$HISTFILE` history file and remove it.

```
$ secret-command --password 1234qwerty  # oh no! that should not be in my history!
$ grep secret-command $HISTFILE
secret-command --password 1234qwerty
$ sed -i '/secret-command/d' $HISTFILE  # deletion of history line containing 'secret-command'
$ grep secret-command $HISTFILE
$ # it's not in history anymore

```

You can also use the `history` built-in command to display your whole history

```
$ history | tail -n 5
  496  mkdir test
  497  secret-command --password 1234qwerty
  498  cd
  499  man history
  500  history | tail -n 5

```

Each history line is prefixed by its index in the history. You can then use `history -d <index>` to remove the associated line from history.

```
$ history -d 497
$ history | tail -n 7
  496  mkdir test
  497  cd
  498  man history
  499  history | tail -n 5
  500  history -d 497
  501  history | tail -n 7

```

This only works with `bash`, not `zsh`.

### Avoiding History

There is a trick you can use if you want to fly under the radar and never have a command recorded in history in the first place. Simply prefix your command by a space.

If you are using `zsh`, you need to add `setopt HIST_IGNORE_SPACE` in your `~/.zshrc` to make sure that behavior is enabled.

```
$  secret-command --password 1234qwerty  # notice the space at the start of the command!
$ history | tail -n 2
  502  history | tail -n 7
  503  history | tail -n 2

```

## Shell Expansions

The shell can perform expansions, meaning it can replace portions of the command before executing it. Relying on expansions allows you to type less and rely on the shell itself to do the heavy lifting. While there are multiple types of expansions, we will only cover 5:

- history expansion: quickly access previous commands and arguments from history
- tilde expansion: replace the `~` path prefix
- pathname expansion: expand a path pattern into a list of files
- braces expansion: expand a pattern between braces into a longer sequence
- command expansion: replace a sub-command by its output

Expansions are extremely powerful. When used right, an expansion can literally save you from writing a script.

As we only over what we think are the most useful expansions and shortcuts, feel free to refer to the `bash` manual, section `EXPANSION` if you want to see the full list.

### History Expansion

Your shell has multiple tricks up its sleeve to allow you to quickly reference previous commands or arguments in history with a minimum of keystrokes. While this section only provides you with what we feel are the most useful of them, feel free to go to the `HISTORY EXPANSION` section of the `bash` manual.

#### Event Designators

An *Event designator* is a reference to a command line entry in the history list. It allows you to quickly refer to a previous command without having to re-type it.

##### `!-n`

`!-n` refers to the nth latest command: `!-1` refers to the latest command, `!-2` to the command before that, etc.

```
$ echo "hello world!"
hello world!
$ cd
$ !-2  # !-1 is "cd" and !-2 is 'echo "hello world!"'
$ echo "hello world"
hello world

```

`!!` is a shortcut for `!-1`, aka the latest command.

```
$ echo "hello world!"
hello world!
$ !!
$ echo "hello world"
hello world

```

`!!` is oftentimes used in conjunction with `sudo`, to re-execute the previous command with superuser privileges when it failed, due to a lack of permission.

```
$ vim /etc/myfile
vim: /etc/myfile: Permission denied
$ sudo !!
$ sudo vim /etc/myfile

```

##### `^string1^string2`

`^string1^string2` is used to repeat the previous command in which `string1` is replaced by `string2`.

```
$ cat ./myfile
Just a file full of junk
$ ^cat^rm
$ rm ./myfile

```

I personally use and abuse of this technique when I'm about to irremediably delete some resources (files, folders, containers, etc), and I want to make sure I'm about to delete the *right* things by listing these resources first. If you are familiar with SQL queries, it is the equivalent of executing a `SELECT` query before changing the `SELECT` to `DELETE` to make sure you're not going to delete more than you wanted to.

#### Word Designators

Word designators are used to select desired words from a previous command (by default, the latest). They can be very useful when you want to type a new command that uses arguments previously typed in a previous command.

##### `!^`

`!^` maps to the first argument of your latest command.

```
$ touch first.txt second.txt last.txt
$ vim !^
$ vim first.txt

```

##### `!$`

`!$` maps to the last argument of your latest command.

```
$ touch first.txt second.txt last.txt
$ vim !$
$ vim last.txt

```

##### Combining Event and Word Designators

You can even combine event and word designators in more complex shapes by using the following syntax

```
[EVENT DESIGNATOR]:[WORD DESIGNATOR]

```

For example, you could use the `!!` event designator to select the last command, and the `2` word designator to select the second argument.

```
$ touch first.txt second.txt last.txt
$ vim !!:2
$ vim second.txt

```

### Tilde Expansion

For each unquoted word starting with `~` in the command, all characters preceding a forward slash (`/`) will be considered a *tilde prefix*. Depending on its actual value, the tilde prefix can be expanded several ways, although the simple `~` is probably its most common use.

| Tilde prefix | Expansion |
| --- | --- |
| `~` | Your home directory |
| `~+` | Your current working directory |
| `~-` | Your previous working directory |

**Example**

```
$ ls ~
Android                code       Downloads              Music
AndroidStudioProjects  Desktop    Dropbox                Pictures
bin                    Documents  Firefox_wallpaper.png  Videos

```

This lists the content of your home directory, and is the equivalent to `ls $HOME`. You can combine the tilde with a suffix to compose an absolute path to some file or folder in your home directory.

```
$ cd ~/code
$ pwd
/home/br/code

```

### Pathname Expansion

Pathname expansions allow you to write an short path pattern and have it expanded in a list of files and directories, saving you from tedious copy-pastes or a possibly long (and error-prone) command writing.

#### `*`

The *glob*, or *wildcard* `*` character matches any string. It allows you to give a *pattern* to the shell, that it will then expand to all files and directories matching the pattern. The wildcard can be prefixed or suffixed, which will further specify our pattern. For example, `*.jpg` matches all files ending with the `.jpg` extension, and `README.*` matches all files named `README` whatever their extension.

Let us consider the following file and directory structure.

```
$ tree
.
|-- pic1.jpg
|-- pic2.jpg
|-- pic3.jpg
|-- pic4.jpg
\__ pics
|   |-- pic5.jpg
|   |-- pic6.jpg
|   \__ pic7.jpg
\__ sounds
    \__sound1.mp3

2 directory, 8 files

```

We want to move all `jpg` files into our `pics` directory. Instead of running 4 different `mv` commands or manually typing a long `mv` command, we can run just one using a pathname expansion.

```
$ mv *.jpg pics
$ tree
.
\__ pics
|   |-- pic1.jpg
|   |-- pic2.jpg
|   |-- pic3.jpg
|   |-- pic4.jpg
|   |-- pic5.jpg
|   |-- pic6.jpg
|   \__ pic7.jpg
\__ sounds
    \__sound1.mp3

2 directory, 8 files

```

`*.jpg` was expanded to all files ending with `.jpg`, causing the shell to actually run `mv pic1.jpg pic2.jpg pic3.jpg pic4.jpg pics`, causing all 4 `jpg` files to be moved to the `pics` directory in a single command.

We could have executed the following command for the same result: `mv pic*.jpg pics`. This would have moved all files with name starting by `pic` and ending with `.jpg` to the `pics` directory

You can use `*` several times within the same pattern. For example `ls */*` will list all files and directories located in a subdirectory.

```
$ ls */*
sounds/sound1.mp3   pics/pic2.jpg       pics/pic4.jpg       pics/pic6.jpg
pics/pic1.jpg       pics/pic3.jpg       pics/pic5.jpg       pics/pic7.jpg

```

Like in our second example, we can also use `*/*.jpg` to list all `jpg` files located in a subdirectory.

```
$ ls */*.jpg
pics/pic1.jpg   pics/pic3.jpg   pics/pic5.jpg  pics/pic7.jpg
pics/pic2.jpg   pics/pic4.jpg   pics/pic6.jpg

```

#### `**`

`**` is expanded to all files and directories in the children directories, with a depth limit of 1.

```
$ touch README.txt
$ mkdir sounds/lyrics
$ touch sounds/lyrics/sound1.txt
$ tree
.
|-- README.txt
\__ pics
|   |-- pic1.jpg
|   |-- pic2.jpg
|   |-- pic3.jpg
|   |-- pic4.jpg
|   |-- pic5.jpg
|   |-- pic6.jpg
|   \__ pic7.jpg
\__ sounds
    \__ lyrics
    |   \__sound1.txt
    \__sound1.mp3

3 directories, 10 files
$ ls **
README.txt

pics:
pic1.jpg pic2.jpg pic3.jpg pic4.jpg pic5.jpg pic6.jpg pic7.jpg

sounds:
lyrics     sounds.mp3

```

`ls **` was expanded into `ls README.txt pics/ sounds/`, which does not include the content of `sounds/lyrics` because of the depth limit of 1.

#### `**/`

`**/` is expanded into all directories and subdirectories with a depth limit of 1 starting from our first directory.

```
$ tree
.
|-- README.txt
\__ pics
|   |-- pic1.jpg
|   |-- pic2.jpg
|   |-- pic3.jpg
|   |-- pic4.jpg
|   |-- pic5.jpg
|   |-- pic6.jpg
|   \__ pic7.jpg
\__ sounds
    \__ lyrics
    |   \__sound1.txt
    \__sound1.mp3


3 directories, 10 files
$ ls **/
pics/:
pic1.jpg pic2.jpg pic3.jpg pic4.jpg pic5.jpg pic6.jpg pic7.jpg

sounds/:
lyrics     sounds.mp3

sounds/lyrics/:
sound1.txt

```

`ls **/` was expanded into `ls sounds/ sounds/lyrics pics/`. It thus listed all files located in our subdirectories.

### Brace Expansion

A brace expansion is a mechanism by which the shell can generate multiple strings based on a sequence of tokens defined within curly braces. The brace expansion pattern can be preceded by an optional *preamble* and followed by an optional *postscript*.

```
$ mkdir ~/test/{pics,sounds,sprites}
$ ls ~/test
pics  sounds  sprites

```

`~/test/{pics,sounds,sprites}` was expanded into `~/test/pics ~/test/sounds ~/test/sprites` causing the shell to execute `mkdir ~/test/pics ~/test/sounds ~/test/sprites` (which will be expanded further into `mkdir /home/br/test/pics /home/br/test/sounds /home/br/test/sprites` by a tilde expansion).

We could have done the same thing by factoring the final `s` of each token into a postscript.

```
$ mkdir ~/test/{pic,sound,sprite}s

```

A brace expansion can also have a sequence pattern `{x..y[..incr]}` where `x` and `y` are either an integer or a single character, and `incr` is an optional increment value.

```
$ touch ~/test/sounds/noise-{1..5}.mp3
$ ls ~/test/sounds
noise-1.mp3 noise-2.mp3 noise-3.mp3 noise-4.mp3 noise-5.mp3

```

The default increment is 1 if the sequence end is greater than its start, and -1 otherwise. However, we could specify a custom increment value if we want.

```
$ touch ~/test/pics/pic{1..10..2}.jpg
$ ls ~/test/pics
pic1.jpg pic3.jpg pic5.jpg pic7.jpg pic9.jpg

```

### Command Expansion

Your shell can replace a command surrounded by `$()` with its output.

I personally like use to commands expansions to iterate over a command's result, or by combining it with a heredoc redirection:

```
$ cat <<EOF > aboutme
My name is $(whoami)
and I live in $HOME
EOF
$ cat aboutme
My name is br
and I live in /home/br

```

## Real-life Examples

### Moving a Pattern of Files Contained in Directories and Subdirectories

What is really powerful with these expansions is that, like almost everything in the shell, they can be combined. The following example combines a pathname expansion, a brace expansion and a tilde expansion.

```
$ tree
.
|-- README.txt
\__ pics
|   |-- pic1.jpg
|   |-- pic2.jpg
|   |-- pic3.jpg
|   |-- pic4.jpg
|   |-- pic5.jpg
|   |-- pic6.jpg
|   \__ pic7.jpg
\__ sounds
    \__ lyrics
    |   \__sound1.txt
    \__sound1.mp3
$ mv **/*.{jpg,mp3} ~/assets/
$ tree
|-- README.txt
\__ pics
\__ sounds
    \__ lyrics
        \__sound1.txt
$ ls ~/assets
pic1.jpg   pic2.jpg   pic3.jpg   pic4.jpg   pic5.jpg   pic6.jpg   pic7.jpg   sound1.mp3

```

Using these expansions, we were able to move all `jpg` and `mp3` files located in directories and subdirectories to the `assets` directory located in your home directory, in exactly 27 characters!

### Renaming Multiple Directories

We could use a `for` loop, pathname expansion and a command expansion to rename all directories contained in the current directory to their uppercase equivalent.

```
$ for dir in */; do
    mv "$dir" "$(echo "$dir" | tr '[:lower:]' '[:upper:]')"
  done

```

Let's decompose that command into its different steps:

- the `*/` glob pattern is expanded over the list of directories, on which we iterate via a `for` loop
- we execute `echo $dir | tr '[:lower:]' '[:upper:]'`, which will convert the current directory name to uppercase
- the `$(echo $dir | tr '[:lower:]' '[:upper:]')` command is expanded into the uppercase directory name
- the directory is renamed into an uppercase name
- the `for` loop iterates over the next directory name
- we move on to the next directory and repeat the previous steps for each of them

Iterating over paths with a `for` loop is brittle as it breaks if a path contains a space. We will later see how to properly do it using the `find` command.

## Summary

Your shell has so many productivity tricks and shortcuts up its sleeve it can be a little bit daunting. I suggest you don't try to learn them all at once, but really just experiment with them and see what feels natural. Even mastering some of them will make you more productive!

What if there is an action you find useful but you just don't like the keyboard shortcut? Luckily for you, the next chapter will dive into how to personalize and customize your shell.

## Going Further

**5.1**: Create a directory. Use a bash expansion to move into that directory without typing its name a second time.

**5.2**: Print your 4th last command typed into your terminal without re-typing it.

**5.3**: Create the following empty files `README.txt`, `requirements.txt` and `TODO.txt` in a single command, without typing `.txt` more than once.

**5.4**: Delete all the files created in the last question without typing `.txt` more than once.

**5.5**: Create the following directory tree in a single command.

```
files
|-- 1
|   |-- 1a
|   |-- 1b
|   |-- 1c
|   |-- 2a
|   |-- 2b
|   |-- 2c
|   |-- 3a
|   |-- 3b
|   \-- 3c
|-- 2
|   |-- 1a
|   |-- 1b
|   |-- 1c
|   |-- 2a
|   |-- 2b
|   |-- 2c
|   |-- 3a
|   |-- 3b
|   \-- 3c
\-- 3
    |-- 1a
    |-- 1b
    |-- 1c
    |-- 2a
    |-- 2b
    |-- 2c
    |-- 3a
    |-- 3b
    \-- 3c

```

**5.6**: Remove all subdirectories starting with `3` created in the previous command, while keeping the top `3` directory.

**5.7**: Re-execute the command from exercise 5.3 by looking backwards into your shell history.
