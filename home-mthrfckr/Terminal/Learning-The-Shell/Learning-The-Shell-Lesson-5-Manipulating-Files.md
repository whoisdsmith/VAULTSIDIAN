# Learning-The-Shell-Lesson-5-Manipulating-Files

This lesson will introduce the following commands:

-   `[cp](http://linuxcommand.org/lc3_man_pages/cp1.html)` - copy files and directories
-   `[mv](http://linuxcommand.org/lc3_man_pages/mv1.html)` - move or rename files and directories
-   `[rm](http://linuxcommand.org/lc3_man_pages/rm1.html)` - remove files and directories
-   `[mkdir](http://linuxcommand.org/lc3_man_pages/mkdir1.html)` - create directories

These four commands are among the most frequently used Linux commands. They are the basic commands for manipulating both files and directories.

Now, to be frank, some of the tasks performed by these commands are more easily done with a graphical file manager. With a file manager, you can drag and drop a file from one directory to another, cut and paste files, delete files, etc. So why use these old command line programs?

The answer is power and flexibility. While it is easy to perform simple file manipulations with a graphical file manager, complicated tasks can be easier with the command line programs. For example, how would you copy all the HTML files from one directory to another, but only copy files that did not exist in the destination directory or were newer than the versions in the destination directory? Pretty hard with with a file manager. Pretty easy with the command line:

\[me@linuxbox me\]$ `cp -u *.html destination`

## Wildcards

Before we begin with our commands, we'll first look at a shell feature that makes these commands so powerful. Since the shell uses filenames so much, it provides special characters to help you rapidly specify groups of filenames. These special characters are called *wildcards*. Wildcards allow you to select filenames based on patterns of characters. The table below lists the wildcards and what they select:

Summary of wildcards and their meanings

**Wildcard**

**Meaning**

**\***

Matches any characters

**?**

Matches any single character

**\[*characters*\]**

Matches any character that is a member of the set *characters*. The set of characters may also be expressed as a *POSIX character class* such as one of the following:

POSIX Character Classes

**\[:alnum:\]**

Alphanumeric characters

**\[:alpha:\]**

Alphabetic characters

**\[:digit:\]**

Numerals

**\[:upper:\]**

Uppercase alphabetic characters

**\[:lower:\]**

Lowercase alphabetic characters

**\[!*characters*\]**

Matches any character that is not a member of the set *characters*

Using wildcards, it is possible to construct very sophisticated selection criteria for filenames. Here are some examples of patterns and what they match:

Examples of wildcard matching

**Pattern**

**Matches**

`*`

All filenames

`g*`

All filenames that begin with the character "g"

`b*.txt`

All filenames that begin with the character "b" and end with the characters ".txt"

`Data???`

Any filename that begins with the characters "Data" followed by exactly 3 more characters

`[abc]*`

Any filename that begins with "a" or "b" or "c" followed by any other characters

`[[:upper:]]*`

Any filename that begins with an uppercase letter. This is an example of a character class.

`BACKUP.[[:digit:]][[:digit:]]`

Another example of character classes. This pattern matches any filename that begins with the characters "BACKUP." followed by exactly two numerals.

`*[![:lower:]]`

Any filename that does not end with a lowercase letter.

We can use wildcards with any command that accepts filename arguments.

## Cp

The `cp` program copies files and directories. In its simplest form, it copies a single file:

\[me@linuxbox me\]$ `cp _file1 file2_`

It can also be used to copy multiple files (and/or directories) to a different directory:

\[me@linuxbox me\]$ `cp _file… directory_`

**A note on notation:** … signifies that an item can be repeated one or more times.

Other useful examples of `cp` and its options include:

Examples of the cp command

**Command**

**Results**

`cp _file1 file2_`

Copies the contents of *file1* into *file2*. If *file2* does not exist, it is created; **otherwise, *file2* is silently overwritten with the contents of *file1*.**

`cp -i _file1 file2_`

Like above however, since the "-i" (interactive) option is specified, if *file2* exists, the user is prompted before it is overwritten with the contents of *file1*.

`cp _file1 dir1_`

Copy the contents of *file1* (into a file named *file1*) inside of directory *dir1*.

`cp -R _dir1 dir2_`

Copy the contents of the directory *dir1*. If directory *dir2* does not exist, it is created. Otherwise, it creates a directory named *dir1* within directory *dir2*.

## Mv

The `mv` command moves or renames files and directories depending on how it is used. It will either move one or more files to a different directory, or it will rename a file or directory. To rename a file, it is used like this:

\[me@linuxbox me\]$ `mv _filename1 filename2_`

To move files (and/or directories) to a different directory:

\[me@linuxbox me\]$ `mv _file… directory_`

Examples of `mv` and its options include:

Examples of the mv command

**Command**

**Results**

`mv _file1 file2_`

If *file2* does not exist, then *file1* is renamed *file2*. **If *file2* exists, its contents are silently replaced with the contents of *file1*.**

`mv -i _file1 file2_`

Like above however, since the "-i" (interactive) option is specified, if *file2* exists, the user is prompted before it is overwritten with the contents of *file1*.

`mv _file1 file2 dir1_`

The files *file1* and *file2* are moved to directory *dir1*. If *dir1* does not exist, `mv` will exit with an error.

`mv _dir1 dir2_`

If *dir2* does not exist, then *dir1* is renamed *dir2*. If *dir2* exists, the directory *dir1* is moved within directory *dir2*.

## Rm

The `rm` command removes (deletes) files and directories.

\[me@linuxbox me\]$ `rm _file…_`

Using the recursive option (`-r`), `rm` can also be used to delete directories:

\[me@linuxbox me\]$ `rm -r _directory…_`

Examples of `rm` and its options include:

Examples of the rm command

**Command**

**Results**

`rm _file1 file2_`

Delete *file1* and *file2*.

`rm -i _file1 file2_`

Like above however, since the "-i" (interactive) option is specified, the user is prompted before each file is deleted.

`rm -r _dir1 dir2_`

Directories *dir1* and *dir2* are deleted along with all of their contents.

## Be Careful with Rm

Linux does not have an undelete command. Once you delete something with `rm`, it's gone. You can inflict terrific damage on your system with `rm` if you are not careful, particularly with wildcards.

***Before you use `rm` with wildcards, try this helpful trick:*** construct your command using `ls` instead. By doing this, you can see the effect of your wildcards before you delete files. After you have tested your command with `ls`, recall the command with the up-arrow key and then substitute `rm` for `ls` in the command.

## Mkdir

The `mkdir` command is used to create directories. To use it, you simply type:

\[me@linuxbox me\]$ `mkdir _directory…_`

## Using Commands with Wildcards

Since the commands we have covered here accept multiple file and directories names as arguments, you can use wildcards to specify them. Here are a few examples:

Command examples using wildcards

**Command**

**Results**

`cp *.txt text_files`

Copy all files in the current working directory with names ending with the characters ".txt" to an existing directory named *text\_files*.

`mv dir1 ../*.bak dir2`

Move the subdirectory *dir1* and all the files ending in ".bak" in the current working directory's parent directory to an existing directory named *dir2*.

`rm *~`

Delete all files in the current working directory that end with the character "~". Some applications create backup files using this naming scheme. Using this command will clean them out of a directory.

## Further Reading

-   Chapter 4 of [_The Linux Command Line_](http://linuxcommand.org/tlcl.php) covers this topic in more detail
