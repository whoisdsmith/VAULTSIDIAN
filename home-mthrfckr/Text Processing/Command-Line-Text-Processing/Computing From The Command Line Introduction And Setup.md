# Introduction and Setup

Back in 2007, I had a rough beginning as a design engineer at a semiconductor company in terms of utilizing software tools. Linux command line, Vim and Perl were all new to me. In addition to learning about command line tools from colleagues and supervisors, I remember going through and making notes in a photocopied book (unable to recall the title now).

The biggest pain points were not knowing about handy options (for example, `grep --color` to highlight matching portions, `find -exec` to apply commands on filtered files, etc) and tools (for example, `xargs` to workaround limitations of too many command line arguments). And then there were tools like `sed` and `awk` with intimidating syntax. I'm at a loss to reason out why I didn't utilize shell scripts much. I stuck to Perl and Vim instead of learning such handy tools. I also did not know about forums like [stackoverflow](https://stackoverflow.com/) and [unix.stackexchange](https://unix.stackexchange.com/) until after I left my job in 2014.

I started collating what I knew about Linux command line tools when I got chances to conduct scripting course workshops for college students. From 2016 to 2018, I started maintaining my tutorials on Linux command line, Vim and scripting languages as GitHub repos. As you might guess, I then started polishing these materials and [published them as ebooks](https://learnbyexample.github.io/books/). This is an ongoing process, with **Computing from the Command Line** being the thirteenth ebook.

This book aims to teach Linux command line tools and Shell Scripting for beginner to intermediate level users. Plenty of examples are provided to make it easier to understand a particular tool and its various features. External links are provided for further reading. Important notes and warnings are formatted to stand out from normal text.

Writing a book always has a few pleasant surprises for me. This time I learned handy options like `mkdir -m` and `chmod =`, got better understanding of many shell features and so on. I'm also planning to learn and present more command line tools for the next version of this book.

This chapter will give a brief introduction to Linux. You'll also see suggestions and instructions for setting up a command line environment to follow along the contents presented in this book.

## [Linux overview](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#linux-overview)

Quoting selective parts from [wikipedia](https://en.wikipedia.org/wiki/Linux):

> Linux is a family of open-source Unix-like operating systems based on the Linux kernel, an operating system kernel first released on September 17, 1991, by Linus Torvalds. Linux is typically packaged in a Linux distribution.
> 
> Linux was originally developed for personal computers based on the Intel x86 architecture, but has since been ported to more platforms than any other operating system. Because of the dominance of the Linux-based Android on smartphones, Linux also has the largest installed base of all general-purpose operating systems.
> 
> Linux is one of the most prominent examples of free and open-source software collaboration. The source code may be used, modified and distributed commercially or non-commercially by anyone under the terms of its respective licenses, such as the GNU General Public License.

Apart from Linux exposure during my previous job, I've been using Linux as my desktop system since 2014 and it is very well suited for my needs. Compared to my Windows experience, Linux is light weight, secure, stable, fast and more importantly doesn't force you to upgrade hardware. Read the wikipedia article linked above for a more comprehensive coverage about Linux, where it is used and so on.

## [Linux Distros](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#linux-distros)

Quoting again from [wikipedia](https://en.wikipedia.org/wiki/Linux_distribution):

> A Linux distribution (often abbreviated as distro) is an operating system made from a software collection that is based upon the Linux kernel and, often, a package management system. Linux users usually obtain their operating system by downloading one of the Linux distributions, which are available for a wide variety of systems ranging from embedded devices (for example, OpenWrt) and personal computers (for example, Linux Mint) to powerful supercomputers (for example, Rocks Cluster Distribution).

I use Ubuntu, which is beginner friendly. Here are some resources to help you choose a distro:

-   [/r/linux4noobs wiki](https://old.reddit.com/r/linux4noobs/wiki/distro_selection) — selection guide for noobs
-   [List of Linux distributions](https://en.wikipedia.org/wiki/List_of_Linux_distributions) — general information about notable Linux distributions in the form of a categorized list
-   [DistroWatch](https://distrowatch.com/) — website dedicated to talking about, reviewing and keeping up to date with open source operating systems. This site particularly focuses on Linux distributions and flavours of BSD, though other open source operating systems are sometimes discussed
-   [Light Weight Linux Distros](https://en.wikipedia.org/wiki/Light-weight_Linux_distribution) — uses lower memory and/or has less processor-speed requirements than a more "feature-rich" Linux distribution

## [Access to Linux environment](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#access-to-linux-environment)

You'll usually find installation instructions from the respective distro website you wish to install. Alternatively, you can install Linux on a [virtual machine](https://en.wikipedia.org/wiki/Virtual_machine) or try it online. Here are some resources to get you started:

-   [Install Ubuntu desktop](https://ubuntu.com/tutorials/install-ubuntu-desktop)
-   [How to run Ubuntu Desktop on a virtual machine using VirtualBox](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox)
-   [DistroTest](https://distrotest.net/index.php) — test a distro directly online without installation

If you are already on Windows or macOS, the following options can be used to get access to Linux tools:

-   [Git for Windows](https://git-scm.com/downloads) — provides a Bash emulation used to run Git from the command line
-   [Windows Subsystem for Linux](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux) — compatibility layer for running Linux binary executables natively on Windows
-   [brew](https://brew.sh/) — Package Manager for macOS (or Linux)

> ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) ![info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/info.svg) ![warning](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/images/warning.svg) If you are completely new to command line usage, I'd recommend setting up a virtual machine. Or perhaps, a secondary computer that you are free to experiment with. Mistakes in command line can be more destructive compared to the graphical interface. For example, a single space typo can result in data loss, leave your machine unusable, etc.

## [Setup](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#setup)

To follow along the contents presented in this book, you'll need files from my [cli-computing repo](https://github.com/learnbyexample/cli-computing). Once you have access to a Linux environment, follow the instructions shown below. If all the commands used below seem alien to you, wait until you reach the [ls](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/managing-files-directories.html#ls) section (you'll get a link back to these instructions at that point).

To get the files, you can clone the cli-computing repo using the `git` command or download a `zip` version. You may have to install the `git` command if you don't already have it, for example `sudo apt install git` on Debian-like systems. See [https://git-scm.com/downloads](https://git-scm.com/downloads) for other installation choices.

```
# option 1: use git
$ git clone --depth 1 https://github.com/learnbyexample/cli-computing.git

# option 2: download zip file
# you can also use 'curl -OL' instead of 'wget'
$ wget https://github.com/learnbyexample/cli-computing/archive/refs/heads/master.zip
$ unzip master.zip
$ mv cli-computing-master cli-computing
```

Once you have the files, you'll be able to follow along the commands presented in this book. For example, you'll need to execute the `ls.sh` script for the [ls](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/managing-files-directories.html#ls) section.

```
$ cd cli-computing/example_files/scripts/
$ ls
cp.sh  file.sh  globs.sh  ls.sh  rm.sh    tar.sh
du.sh  find.sh  grep.sh   mv.sh  stat.sh  touch.sh

$ source ls.sh
$ ls -F
backups/    hello_world.py*  ip.txt     report.log  todos/
errors.log  hi*              projects/  scripts@
```

For sections like the [cat](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/viewing-part-or-whole-file-contents.html#cat) command, you'll need to use the sample input files provided in the `text_files` directory.

```
$ cd cli-computing/example_files/text_files/
$ cat greeting.txt 
Hi there
Have a nice day
```

## [Command Line Interface](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#command-line-interface)

Command Line Interface (CLI) allows you to interact with the computer using text commands. For example, the `cd` command helps you navigate to a particular directory. The `ls` command shows the contents of a directory. In a graphical environment, you'd use an explorer (file manager) for navigation and directory contents are shown by default. Some tasks can be accomplished in both CLI and GUI environments, while some are suitable and effective only in one of them.

Here are some advantages of using CLI tools over GUI programs:

-   automation
-   faster execution
-   command invocations are repeatable
-   easy to save solutions and share with others
-   single environment compared to different UI/UX with graphical solutions
-   common text interface allows tools to easily communicate with each other

And here are some disadvantages:

-   steep learning curve
-   syntax can get very complicated
-   need to get comfortable with plenty of tools
-   typos have a tendency to be more destructive

You can make use of features like command history, shortcuts and autocompletion to help with plethora of commands and syntax issues. Consistent practice will help to get familiar with quirks of the command line environment. Commands with destructive potential will usually include options to allow manual confirmation and interactive usage, thus reducing or entirely avoiding the impact of typos.

## [Chapters](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#chapters)

Here's the list of remaining chapters:

-   [Command Line Overview](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/command-line-overview.html)
-   [Managing Files and Directories](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/managing-files-directories.html)
-   [Shell Features](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/shell-features.html)
-   [Viewing Part or Whole File Contents](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/viewing-part-or-whole-file-contents.html)
-   [Searching Files and Filenames](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/searching-files-and-filenames.html)
-   [File Properties](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/file-properties.html)
-   [Managing Processes](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/managing-processes.html)
-   [Multipurpose Text Processing Tools](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/multipurpose-text-processing-tools.html)
-   [Sorting Stuff](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/sorting-stuff.html)
-   [Comparing Files](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/comparing-files.html)
-   [Assorted Text Processing Tools](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/assorted-text-processing-tools.html)
-   [Shell Scripting](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/shell-scripting.html)
-   [Shell Customization](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/shell-customization.html)

## [Resource lists](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#resource-lists)

This book covers but a tiny portion of Linux command line usage. Topics like system administration and networking aren't discussed at all. Check out the following lists to learn about such topics and discover cool tools:

-   [Linux curated resources](https://learnbyexample.github.io/curated_resources/linux_cli_scripting.html) — my collection of resources for Linux command line, shell scripting and other related topics
-   [Awesome Linux](https://github.com/inputsh/awesome-linux) — list of awesome projects and resources that make Linux even more awesome
-   [Arch wiki: list of applications](https://wiki.archlinux.org/title/List_of_applications) — sorted by category, helps as a reference for those looking for packages

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/preface.html "Previous chapter")[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/command-line-overview.html "Next chapter")

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/preface.html "Previous chapter")[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/command-line-overview.html "Next chapter")
