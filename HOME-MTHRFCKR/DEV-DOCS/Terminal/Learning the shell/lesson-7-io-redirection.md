In this lesson, we will explore a powerful feature used by command line programs called _input/output redirection_. As we have seen, many commands such as `ls` print their output on the display. This does not have to be the case, however. By using some special notations we can _redirect_ the output of many commands to files, devices, and even to the input of other commands.

## Standard Output

Most command line programs that display their results do so by sending their results to a facility called _standard output_. By default, standard output directs its contents to the display. To redirect standard output to a file, the ">" character is used like this:

\[me@linuxbox me\]$ `ls > file_list.txt`

In this example, the `ls` command is executed and the results are written in a file named `file_list.txt`. Since the output of `ls` was redirected to the file, no results appear on the display.

Each time the command above is repeated, `file_list.txt` is overwritten from the beginning with the output of the command `ls`. To have the new results _appended_ to the file instead, we use ">>" like this:

\[me@linuxbox me\]$`ls >> file_list.txt`

When the results are appended, the new results are added to the end of the file, thus making the file longer each time the command is repeated. If the file does not exist when we attempt to append the redirected output, the file will be created.

## Standard Input

Many commands can accept input from a facility called _standard input_. By default, standard input gets its contents from the keyboard, but like standard output, it can be redirected. To redirect standard input from a file instead of the keyboard, the "<" character is used like this:

\[me@linuxbox me\]$ `sort < file_list.txt`

In the example above, we used the `[sort](http://linuxcommand.org/lc3_man_pages/sort1.html)` command to process the contents of `file_list.txt`. The results are output on the display since the standard output was not redirected. We could redirect standard output to another file like this:

\[me@linuxbox me\]$ `sort < file_list.txt > sorted_file_list.txt`

As we can see, a command can have both its input and output redirected. Be aware that the order of the redirection does not matter. The only requirement is that the redirection operators (the "<" and ">") must appear after the other options and arguments in the command.

## Pipelines

The most useful and powerful thing we can do with I/O redirection is to connect multiple commands together to form what are called _pipelines_. With pipelines, the standard output of one command is fed into the standard input of another. Here is a very useful example:

\[me@linuxbox me\]$ `ls -l | less`

In this example, the output of the `ls` command is fed into `less`. By using this `"| less"` trick, we can make any command have scrolling output.

By connecting commands together, we can accomplish amazing feats. Here are some examples to try:

Examples of commands used together with pipelines

**Command**

**What it does**

`ls -lt | [head](http://linuxcommand.org/lc3_man_pages/head1.html)`

Displays the 10 newest files in the current directory.

`[du](http://linuxcommand.org/lc3_man_pages/du1.html) | sort -nr`

Displays a list of directories and how much space they consume, sorted from the largest to the smallest.

`[find](http://linuxcommand.org/lc3_man_pages/find1.html) . -type f -print | [wc](http://linuxcommand.org/lc3_man_pages/wc1.html) -l`

Displays the total number of files in the current working directory and all of its subdirectories.

## Filters

One kind of program frequently used in pipelines is called a _filter_. Filters take standard input and perform an operation upon it and send the results to standard output. In this way, they can be combined to process information in powerful ways. Here are some of the common programs that can act as filters:

Common filter commands

**Program**

**What it does**

`[sort](http://linuxcommand.org/lc3_man_pages/sort1.html)`

Sorts standard input then outputs the sorted result on standard output.

`[uniq](http://linuxcommand.org/lc3_man_pages/uniq1.html)`

Given a sorted stream of data from standard input, it removes duplicate lines of data (i.e., it makes sure that every line is unique).

`[grep](http://linuxcommand.org/lc3_man_pages/grep1.html)`

Examines each line of data it receives from standard input and outputs every line that contains a specified pattern of characters.

`[fmt](http://linuxcommand.org/lc3_man_pages/fmt1.html)`

Reads text from standard input, then outputs formatted text on standard output.

`[pr](http://linuxcommand.org/lc3_man_pages/pr1.html)`

Takes text input from standard input and splits the data into pages with page breaks, headers and footers in preparation for printing.

`[head](http://linuxcommand.org/lc3_man_pages/head1.html)`

Outputs the first few lines of its input. Useful for getting the header of a file.

`[tail](http://linuxcommand.org/lc3_man_pages/tail1.html)`

Outputs the last few lines of its input. Useful for things like getting the most recent entries from a log file.

`[tr](http://linuxcommand.org/lc3_man_pages/tr1.html)`

Translates characters. Can be used to perform tasks such as upper/lowercase conversions or changing line termination characters from one type to another (for example, converting DOS text files into Unix style text files).

`[sed](http://linuxcommand.org/lc3_man_pages/sed1.html)`

Stream editor. Can perform more sophisticated text translations than `tr`.

`[awk](http://linuxcommand.org/lc3_man_pages/awk1.html)`

An entire programming language designed for constructing filters. Extremely powerful.

  

## Further Reading

-   Chapter 6 of [_The Linux Command Line_](http://linuxcommand.org/tlcl.php) covers this topic in more detail.
-   Chapters 19 through 21 of _The Linux Command Line_ provide an in-depth look at the text processing tools available in Linux.
-   To learn more about the AWK programming language, consider the [AWK adventure](http://linuxcommand.org/lc3_adv_awk.php).