# Command Line Overview

This chapter will help you take the first steps in the command line world. Apart from command examples that you can try out, you'll also learn a few essential things about working in a text environment.

For newbies, the sudden paradigm shift to interacting with the computer using just text commands can be overwhelming, especially for those accustomed to the graphical user interface (GUI). After regular usage, things will start to look systematic and you might realize that GUI is ill suited for repetitive tasks. With continuous use, recalling various commands will become easier. Features like command line history, aliases, tab-completion and shortcuts will help too.

If you've used a scientific calculator, you'd know that it is handy with too many functionalities cramped into a tiny screen and a plethora of multipurpose buttons. Command line environment is something like that, but not limited just to mathematics. From managing files to munging data, from image manipulations to working with video, you'll likely find a tool for almost any computing task you can imagine. Always remember that command line tools appeared long before graphical ones did. The rich history shows its weight in the form of robust tools and the availability of wide variety of applications.

## [Hello Command Line](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#hello-command-line)

Open a [Terminal Emulator](https://en.wikipedia.org/wiki/Terminal_emulator) and type the command as shown below. The `$` followed by a space character at the start is the simple command prompt that I use. It might be different for you. The actual command to type is `echo` followed by a space, then the argument `'Hello Command Line'` and finally press the `Enter` key to execute it. You should get the argument echoed back to you as the command output.

```
$ echo 'Hello Command Line'
Hello Command Line
```

Here's another simple illustration. This time, the command `pwd` is entered by itself (i.e. no arguments). You should get *your* current location as the output. The `/` character separates different parts of the location (more details in the upcoming sections).

```
$ pwd
/home/learnbyexample
```

Next, enter the `exit` command to quit the Terminal session.

```
$ exit
```

If you are completely new to the command line world, try out the above steps a few more times until you feel comfortable with opening a Terminal Emulator, executing commands and quitting the session. More details about the command structure, customizing command prompt, etc will be discussed later.

## [File System](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#file-system)

In Linux, directory structure starts with the `/` symbol, which is referred to as the **root** directory. The `man hier` command gives description of the file system hierarchy. Here are some selected examples:

-   `/` This is the root directory. This is where the whole tree starts.
-   `/bin` This directory contains executable programs which are needed in single user mode and to bring the system up or repair it.
-   `/home` On machines with home directories for users, these are usually beneath this directory, directly or not. The structure of this directory depends on local administration decisions (optional).
-   `/tmp` This directory contains temporary files which may be deleted with no notice, such as by a regular job or at system boot up.
-   `/usr` This directory is usually mounted from a separate partition. It should hold only shareable, read-only data, so that it can be mounted by various machines running Linux.
-   `/usr/bin` This is the primary directory for executable programs. Most programs executed by normal users which are not needed for booting or for repairing the system and which are not installed locally should be placed in this directory.
-   `/usr/share` This directory contains subdirectories with specific application data, that can be shared among different architectures of the same OS.

## [Absolute and Relative paths](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#absolute-and-relative-paths)

Quoting [wikipedia](https://en.wikipedia.org/wiki/Path_%28computing%29#Absolute_and_relative_paths):

> An **absolute** or **full** path points to the same location in a file system regardless of the current working directory. To do that, it must contain the root directory.

> By contrast, a **relative** path starts from some given working directory, avoiding the need to provide the full absolute path. A filename can be considered as a relative path based at the current working directory. If the working directory is not the file's parent directory, a file not found error will result if the file is addressed by its name.

For example, `/home/learnbyexample` is an absolute path and `../design` is a relative path. You'll learn how paths are used for performing tasks in the coming chapters.

## [Shells and Terminal Emulators](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#shells-and-terminal-emulators)

These terms are often used to interchangeably mean the same thing — a prompt to allow the user to execute commands. However, they are quite different:

-   **Shell** is a command line interpreter. Sets the syntax rules for invoking commands, provides operators to connect commands and redirect data, has scripting features like loops, functions and so on
-   **Terminal** is a text input/output environment. Responsible for visual details like font size, color, etc

Some of the popular shells are `bash`, `zsh` and `fish`. This book will discuss only the [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) shell. Some of the popular terminal emulators are [GNOME Terminal](https://en.wikipedia.org/wiki/GNOME_Terminal), [konsole](https://en.wikipedia.org/wiki/Konsole), [xterm](https://en.wikipedia.org/wiki/Xterm) and [alacritty](https://github.com/alacritty/alacritty).

Quoting from [wikipedia: Unix shell](https://en.wikipedia.org/wiki/Unix_shell):

> A Unix shell is a command-line interpreter or shell that provides a command line user interface for Unix-like operating systems. The shell is both an interactive command language and a scripting language, and is used by the operating system to control the execution of the system using shell scripts.
> 
> Users typically interact with a Unix shell using a terminal emulator; however, direct operation via serial hardware connections or Secure Shell are common for server systems. All Unix shells provide filename wildcarding, piping, here documents, command substitution, variables and control structures for condition-testing and iteration.

Shell features will be discussed in later sections and chapters. For now, open a terminal and try out the following commands:

```
$ cat /etc/shells
# /etc/shells: valid login shells
/bin/sh
/bin/dash
/bin/bash
/bin/rbash

$ echo "$SHELL"
/bin/bash
```

In the above example, the `cat` command is used to display the contents of a file and the `echo` command is used to display the contents of a variable. `SHELL` is an environment variable containing full path to the shell.

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) The output of the above commands might be different for you. And as mentioned earlier, your command prompt might be different than `$` . For now, you can ignore it. Or, you could type `PS1='$ '` and press the `Enter` key to set the prompt for the current session.

**Further Reading**

-   [unix.stackexchange: What is the exact difference between a 'terminal', a 'shell', a 'tty' and a 'console'?](https://unix.stackexchange.com/q/4126/109046)
-   [wikipedia: Comparison of command shells](https://en.wikipedia.org/wiki/Comparison_of_command_shells)
-   [unix.stackexchange: Difference between login shell and non-login shell](https://unix.stackexchange.com/q/38175/109046)
-   [Features and differences between various shells](http://www.faqs.org/faqs/unix-faq/shell/shell-differences/)
-   [Syntax comparison on different shells with examples](https://hyperpolyglot.org/unix-shells)
-   [Shell, choosing shell and changing default shells](https://wiki.ubuntu.com/ChangingShells)

## [Unix Philosophy](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#unix-philosophy)

Quoting from [wikipedia: Unix Philosophy](https://en.wikipedia.org/wiki/Unix_philosophy):

> -   Write programs that do one thing and do it well.
>     
> -   Write programs to work together.
>     
> -   Write programs to handle text streams, because that is a universal interface.
>     

These principles do not strictly apply to all the command line tools, but it is good to be aware of them. As you get familiar with working from the command line, you'll be able to appreciate these guidelines better.

## [Command Structure](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#command-structure)

It is not necessary to fully understand the commands used in this chapter, just the broad strokes. The examples are intended to help you get a feel for the basics of using command options and arguments.

**Command invocation without any options or arguments**:

-   `clear` clear the terminal screen
-   `date` show the current date and time

**Command with options (flags)**:

-   `ls -l` list directory contents in a long listing format
-   `ls -la` list directory contents including hidden files in long listing format
    -   two short options `-l` and `-a` are combined together here as `-la`
-   `df -h` report file system disk space usage sizes in human readable format
-   `df --human-readable` same as `df -h` but using long option instead of short option

**Command with arguments**:

-   `mkdir project` create a directory named `project` in the current working directory
-   `man sort` manual page for the `sort` command
-   `diff file1.txt file2.txt` display differences between the two input files
-   `wget https://s.ntnu.no/bashguide.pdf` download a file from the internet
    -   the link passed to `wget` in the above example is real, visit [BashGuide](https://mywiki.wooledge.org/BashGuide) for details

**Command with both options and arguments**:

-   `rm -r project` remove (delete) the `project` directory recursively
-   `paste -sd, ip.txt` serialize all lines from the input file to a single line using `,` as the delimiter

**Single quotes vs Double quotes**:

-   **Single quotes** preserves the literal value of each character within the quotes
-   **Double quotes** preserves the literal value of all characters within the quotes, with the exception of `$`, `` ` ``, `\`, and, when history expansion is enabled, `!`

```
# no character is special within single quotes
$ echo '$SHELL'
$SHELL

# $ is special within double quotes, used to interpolate variable here
$ echo "Full path to the shell: $SHELL"
Full path to the shell: /bin/bash
```

More details and other types of quoting will be discussed in the [Shell Features](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/shell-features.html) chapter.

## [Command Network](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#command-network)

One of the *Unix Philosophy* seen earlier mentioned commands working together. The shell provides several ways to do so. A commonly used feature is redirecting the output of a command — as input of another command, to be saved in a file and so on.

-   to another command
    -   `du -sh * | sort -h` calculate size of files and folders in human-readable format using `du` and then sort them using a tool specialized for that task
-   to a file
    -   `grep 'pass' *.log > pass_list.txt` write the results to a file instead of displaying on the terminal (if the file already exists, it gets overwritten)
    -   `grep 'error' *.log >> errors.txt` append the results to the given file (creates a new file if necessary)
-   to a variable
    -   `d=$(date)` save command output in a variable named `d`

Many more of such shell features will be discussed in later chapters.

## [Scripting](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#scripting)

Not all operations can be completed using a one-liner from the terminal. In such cases, you can save the instructions in a text file and then execute them. Open your favorite text editor and write the three lines shown below:

```
$ cat cmds.sh
echo 'hello world'
echo 'how are you?'
seq 3
```

As an alternate to using a text editor, you can use either of the commands shown below to create this file.

```
# assuming 'echo' supports '-e' option in your environment
$ echo -e "echo 'hello world'\necho 'how are you?'\nseq 3" > cmds.sh

# a more portable solution using the builtin 'printf' command
$ printf "echo 'hello world'\necho 'how are you?'\nseq 3\n" > cmds.sh
```

The script file is named `cmds.sh` and has three commands in three separate lines. One way to execute the contents of this file is by using the `source` command:

```
$ source cmds.sh
hello world
how are you?
1
2
3
```

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) Your Linux distro is likely to have an easy to use graphical text editor such as `gedit` and `mousepad`. See [wiki.archlinux: text editors](https://wiki.archlinux.org/title/List_of_applications#Text_editors) for a huge list of editors to choose from.

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) The [Shell Scripting](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/shell-scripting.html) chapter will discuss scripting in more detail.

## [Command Help](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#command-help)

Most distros for personal use come with documentation for commands already installed. Learning how to use manuals from the terminal is handy and there are ways to get specific information as well.

### [man](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#man)

The `man` command is an interface to view manuals from within the terminal itself. This uses a `pager` (which is usually the `less` command) to display the contents. You could call these commands as terminal user interface (TUI) applications. As an example, type `man cat` and you should see something like the screenshot shown below:

![manual page for the cat command](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/man_cat.png)

Since the documentation has several lines that doesn't completely fit within the terminal window, you will get only the starting part of the manual. You have several options to navigate:

-   `↑` and `↓` arrow keys to move up and down by a line
    -   you can also use `k` and `j` keys (same keys as those used in the Vim text editor)
-   `f` and `b` keys to move forward and backward by a screenful of content
    -   `Space` key also moves forward by a screen
-   mouse scroll moves up and down by a few lines
-   `g` or `Home` go to the start of the manual
-   `G` or `End` go to the end of the manual
-   `/pattern` followed by `Enter` search for the given pattern in the forward direction
-   `?pattern` followed by `Enter` search for the given pattern in the backward direction
-   `n` go to the next match
-   `N` go to the previous match
-   `q` quit

As you might have noticed in the screenshot above, you can use `h` for help about the `less` command itself. Here are some useful tips related to documentation:

-   `man man` gives information about the `man` command itself
-   `man bash` will give you the manual page for the `bash` shell
    -   since this is very long, I'd recommend using the [online GNU Bash manual](https://www.gnu.org/software/bash/manual/)
-   `man find | gvim -` open the manual page in your favorite text editor
-   `man -k printf` search the short descriptions in all the manual pages for the string `printf`
    -   you can also use the `apropos` command instead of `man -k`
-   `wc --help` many commands support the `--help` option to give succinct details like options and syntax
    -   also, these details will be displayed on the terminal itself, no need to deal with `pager` interface

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) See also [unix.stackexchange: How do I use man pages to learn how to use commands?](https://unix.stackexchange.com/q/193815/109046) and [unix.stackexchange: colors in man pages](https://unix.stackexchange.com/q/119/109046).

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) The Linux manual pages are usually shortened version of the full documentation. You can use the `info` command to view the complete documentation for GNU tools. `info` is also a TUI application, but with different key configuration compared to the `man` command. See [GNU Manuals Online](https://www.gnu.org/manual/manual.html) if you'd prefer to read them from a web browser. You can also download them in formats like PDF for offline usage.

### [type](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#type)

For certain operations, the shell provides its own set of commands, known as builtin commands. The `type` command displays information about a command like its path, whether it is a builtin, alias, function and so on.

```
$ type cd
cd is a shell builtin
$ type sed
sed is /bin/sed
$ type type
type is a shell builtin

# multiple commands can be given as arguments
$ type pwd awk
pwd is a shell builtin
awk is /usr/bin/awk
```

As will be discussed in the [Shell Customization](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/shell-customization.html) chapter, you can create aliases to customize command invocations. You can use the `type` command to reveal the nature of such aliases. Here are some examples based on aliases I use:

```
$ type p
p is aliased to 'pwd'

$ type ls
ls is aliased to 'ls --color=auto'
```

The `type` command formats the command output with a backtick at the start and a single quotes at the end. That doesn't play well with syntax highlighting, so I've changed the backtick to single quotes in the above illustration.

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) See also [unix.stackexchange: What is the difference between a builtin command and one that is not?](https://unix.stackexchange.com/q/11454/109046)

### [help](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#help)

The `help` command provides documentation for builtin commands. Unlike the `man` command, the entire text is displayed as the command output. A help page in the default format is shown below. You can add `-m` option if you want the help content in a pseudo-manpage format.

```
$ help pwd
pwd: pwd [-LP]
    Print the name of the current working directory.
    
    Options:
      -L        print the value of $PWD if it names the current working directory
      -P        print the physical directory, without any symbolic links
    
    By default, 'pwd' behaves as if '-L' were specified.
    
    Exit Status:
    Returns 0 unless an invalid option is given or the current directory
    cannot be read.
```

You can use the `-d` option to get a short description of the command:

```
$ help -d compgen
compgen - Display possible completions depending on the options.
```

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) Use `help help` for documentation on the `help` command. If you use `help` without any argument, it will display all the internally defined shell commands.

### [whatis and whereis](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#whatis-and-whereis)

Here are some more ways to get specific information about commands:

-   `whatis` displays one-line manual page descriptions
-   `whereis` locates the binary, source, and manual page files for a command

```
$ whatis grep
grep (1)             - print lines that match patterns

$ whereis awk
awk: /usr/bin/awk /usr/lib/x86_64-linux-gnu/awk /usr/share/awk
/usr/share/man/man1/awk.1.gz
```

### [ch](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#ch)

[explainshell](https://explainshell.com/) is a web app that shows the help text that matches each argument of the command you type in the app. For example, a screenshot for [tar -xzvf archive.tar.gz](https://explainshell.com/explain?cmd=tar+-xzvf+archive.tar.gz) is shown below:

![explainshell example for the tar command](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/explainshell_tar.png)

Inspired by this app, I wrote a [Bash script ch](https://github.com/learnbyexample/command_help) to extract information from `man` and `help` pages. Here are some examples:

```
$ ch ls -vX
       ls - list directory contents

       -v     natural sort of (version) numbers within text

       -X     sort alphabetically by entry extension

$ ch type -a
    type - Display information about command type.

      -a        display all locations containing an executable named NAME;
                includes aliases, builtins, and functions, if and only if
                the '-p' option is not also used
```

### [Further Reading](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#further-reading)

-   [Linux man pages](https://www.mankier.com/) — one of several websites that host man pages online
-   [ArchWiki](https://wiki.archlinux.org/title/Table_of_contents) — comprehensive documentation for Arch Linux and other distributions
-   [Debian Reference](https://www.debian.org/doc/manuals/debian-reference/) — broad overview of the Debian system, covers many aspects of system administration through shell-command examples

## [Shortcuts and Autocompletion](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#shortcuts-and-autocompletion)

There are several shortcuts you can use to be productive at the command line. These will be discussed in the [Shell Customization](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/shell-customization.html) chapter. Here are some examples to give an idea:

-   `Ctrl+u` delete everything to the left of the cursor
-   `Ctrl+k` delete from the current character to the end of the line
-   `Ctrl+c` abort the currently typed command
-   `Ctrl+l` clear the terminal screen and move the prompt to the top, any characters typed as part of the current command will be retained
-   `↑` and `↓` arrow keys to navigate previously used commands from the history
    -   `Ctrl+p` and `Ctrl+n` can also be used instead of arrow keys
    -   you can modify the command before executing such lines from the history

The tab key helps you autocomplete commands, aliases, filenames and so on, depending on the context. If there is only one possible completion, it will be done on single tab press. Otherwise, you can press the tab key twice to get a list of possible matches (if there are any). Here's an example of completing a file path with multiple tab key presses at various stages. Not only does it saves time, it also helps to avoid typos since you are simultaneously verifying the path.

```
# pressing tab after typing '/e' will autocomplete to '/etc/'
$ ls /etc/

# pressing tab after 'di' will autocomplete to 'dict'
$ ls /etc/dict
# pressing tab twice will show all possible completions
$ ls /etc/dict
dictd/               dictionaries-common/ 

# type 'i' and press tab to get 'dictionaries-common'
$ ls /etc/dictionaries-common/

# type 'w' and press tab to get 'words'
$ ls /etc/dictionaries-common/words 
```

The character at which the tab key is pressed in the above example has been cherry picked for illustration purposes. The number of steps would increase if you try pressing tab after each character. With experience, using the tab key for autocompletion will become a natural part of your command line usage.

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) You can set an option to combine the features of single and double tab presses into a single tab press. This will be discussed in the [Shell Customization](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/shell-customization.html) chapter.

## [Real world use cases](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#real-world-use-cases)

If the command line environment only had file managing features, I'd still use it. Given the wide variety of applications available, I can't imagine going back to using a different GUI application for each use case. My primary work is writing ebooks, blog posts and recording videos. Here are the major CLI tools I use:

-   text processing using `head`, `tail`, `sort`, `grep`, `sed`, `awk` and so on (you'll learn about these commands in later chapters)
-   [git](https://git-scm.com/) — version control
-   [pandoc](https://github.com/jgm/pandoc/) — generating PDF/EPUB book versions from markdown files
-   [mdBook](https://github.com/rust-lang/mdBook) — web version of the books from markdown files
-   [zola](https://github.com/getzola/zola) — static site generator
-   [ImageMagick](https://imagemagick.org/index.php) — image processing like resizing, adding borders, etc
-   [oxipng](https://github.com/shssoichiro/oxipng), [pngquant](https://pngquant.org/) and [svgcleaner](https://github.com/RazrFalcon/svgcleaner) — optimizing images
-   [auto-editor](https://github.com/WyattBlue/auto-editor) — removing silent portions from video recordings
-   [FFmpeg](https://github.com/FFmpeg/FFmpeg) — video processing, padding for example (`FFmpeg` is also a major part of the `auto-editor` solution)

Some of these workflows require additional management, for which I write shell functions or scripts. I do need GUI tools as well, for example, web browser, image viewer, PDF/EPUB viewers, [SimpleScreenRecorder](https://github.com/MaartenBaert/ssr) and so on. Some of these can be handled from within the terminal too, but I prefer GUI for such cases. I do launch some of them from the terminal, primarily for providing the file or url to be opened.

You might wonder what advantage does the command line provide for processing images and videos? Apart from being faster, the custom parameters (like border color, border size, quality percentage, etc) are automatically saved as part of the scripts I create. After that, I can just use a single call to the script instead of waiting for a GUI application to open, navigating to required files, applying custom parameters, saving them after all the required processing is done, closing the application, etc. Also, that single script can use as many tools as needed, whereas with GUI you'll have to repeat such steps with different applications.

## [Exercises](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#exercises)

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) All the exercises are also collated together in one place at [exercises.md](https://github.com/learnbyexample/cli-computing/blob/master/exercises/exercises.md). For solutions, see [exercise-solutions.md](https://github.com/learnbyexample/cli-computing/blob/master/exercises/exercise-solutions.md).

**1)** By default, is `echo` a shell builtin or external command on your system? What command could you use to get an answer for this question?

**2)** What output do you get for the command shown below? Does the documentation help understand the result?

```
$ echo apple     42 'banana     100'
```

**3)** Go through [bash manual: Tilde Expansion](https://www.gnu.org/software/bash/manual/html_node/Tilde-Expansion.html). Is `~/projects` a relative or an absolute path? See [this unix.stackexchange thread](https://unix.stackexchange.com/q/221970/109046) for answers.

**4)** Which key would you use to get help while the `less` command is active?

**5)** How would you bring the 50th line to the top of the screen while viewing a `man` page (assume `less` command is the `pager`)?

**6)** What does the `Ctrl+k` shortcut do?

**7)** Briefly explain the role of the following shell operators:

*a)* `|`  
*b)* `>`  
*c)* `>>`

**8)** The `whatis` command displays one-line descriptions about commands. But it doesn't seem to work for `whatis type`. What should you use instead?

```
$ whatis cat
cat (1)              - concatenate files and print on the standard output

$ whatis type
type: nothing appropriate.

# ???
type - Display information about command type.
```

**9)** What is the role of the `/tmp` directory?

**10)** Give an example each for absolute and relative paths.

**11)** When would you use the `man -k` command?

**12)** Are there any differences between `man` and `info` pages?

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/introduction-setup.html "Previous chapter")[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/managing-files-directories.html "Next chapter")

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/introduction-setup.html "Previous chapter")[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/managing-files-directories.html "Next chapter")
