This tutorial is for beginner users who want to learn the basics of how to use the command line. Here's another [basic command line tutorial](http://matt.might.net/articles/basic-unix/) with more information, if you'd like to learn more.

-   [What Is the Command Line?](https://www.davidbaumgold.com/tutorials/command-line/#what-is-the-command-line?)
-   [Finding the Command Line](https://www.davidbaumgold.com/tutorials/command-line/#finding-the-command-line)
    -   [Mac OS X](https://www.davidbaumgold.com/tutorials/command-line/#mac-os-x)
    -   [Linux](https://www.davidbaumgold.com/tutorials/command-line/#linux)
    -   [Windows](https://www.davidbaumgold.com/tutorials/command-line/#windows)
-   [Command Syntax](https://www.davidbaumgold.com/tutorials/command-line/#command-syntax)
-   [Basic Utilities](https://www.davidbaumgold.com/tutorials/command-line/#basic-utilities)
-   [Moving Around the Computer](https://www.davidbaumgold.com/tutorials/command-line/#moving-around-the-computer)
-   [Neat Tricks](https://www.davidbaumgold.com/tutorials/command-line/#neat-tricks)
    -   [Tab Autocompletion](https://www.davidbaumgold.com/tutorials/command-line/#tab-autocompletion)
    -   [Shortcuts](https://www.davidbaumgold.com/tutorials/command-line/#shortcuts)
-   [Warnings](https://www.davidbaumgold.com/tutorials/command-line/#warnings)

## What Is the Command Line?

The command line is the ultimate seat of power on your computer. Using the command line, you can perform amazing feats of wizardry and speed, taming your computer and getting it to do _precisely_ what you want. Unfortunately, the price of this power is complexity: nobody ever said that ruling your computer would be easy.

The command line is, at its heart, simply a place where you type commands to the computer. The computer is your obedient servant, and will attempt to carry out any command that it understands. Unfortunately, the computer does not speak English, or any other language spoken by humans (although it has recognizable elements). In order to give it commands, we must first start learning the language of the computer.

**NOTE:** The command line, as with all power, has its [risks](https://www.davidbaumgold.com/tutorials/command-line/#warnings). You have the capability to instruct the computer to do anything it has the capability of doing. If you instruct the computer to erase all of your data, it will cheerfully proceed to do so. **Do not run a command just to see what it does.** Make sure you understand what the command is supposed to do first, especially if the command involves changing or removing files.

## Finding the Command Line

Most people don't use the command line on a regular basis, so it can be a bit difficult to find the first time. The Windows operating system doesn't even have a proper command line built in — to execute these commands, you will have to install one.

### Mac OS X

The Mac command line is a program called Terminal. It lives in the `/Applications/Utilities/` folder. To find it, go to your Applications folder. Near the bottom, there is a folder called Utilities. Go inside, and one of the applications listed is called Terminal. Double-click that application to open it.

### Linux

The location of the command line depends on whether you are using the Gnome or KDE window manager. (If there is a big K icon on the bottom left of the screen, you are using KDE; if not, you are using Gnome.) If you are using KDE, click the K button, select System, and click on Konsole. If you are using Gnome, click the Applications button at the top left, select System Tools, and click on Terminal.

### Windows

Unfortunately, you will have to install your own command line program. Windows comes with a command line, but it is non-standard and more difficult to use. [Babun](https://babun.github.io/) is a free, easy to install command line program. Simply [download the Babun installer](http://projects.reficio.org/babun/download), double-click it to install Babun, and then move the installer to the recycle bin. To use Babun, go to the Start menu, select Programs, and click on Babun.

## Command Syntax

Nobody likes grammar, so let's get this over with quickly. All commands have three parts: the utility, the flags, and the arguments. The utility always comes first. The other two parts have different rules, depending on which command you are using: you may not have to use any flags or arguments at all. Here is a sample command that you might type into a command line:

Let's break this command down into parts:

-   `ls` is a **utility**. Utilities are also sometimes known as commands all on their own, because they indicate the general idea of what you want. Most of the time, you can simply run a utility all by itself, without any flags or arguments. Most commands only have one utility.
-   `-l` is a **flag** that alters how the utility operates. Flags are like options or preferences: the utility will usually work perfectly well with the defaults, but sometimes, you want to modify how it works slightly. Flags always start with either one or two dashes (`-`), and they usually come between the utility and the arguments.
-   `~/Desktop` is an argument to the utility. Arguments are used when the utility needs to know exactly what you want for a certain action, and there is no clear default setting. You can think of it more like a conversation than an argument: The utility says "I don't know how I should do this!", and you use an argument to say, "Here, this is how you should do it." Arguments usually come at the end of the command, after the utility and the flags (if any flags are used). The number of arguments used generally depends on the utility: some don't need any arguments, some require exactly one argument, some require lots of arguments, and some are flexible in the number of arguments they can take.

This command uses the `ls` utility, which is used to list the contents of directories. We use the `-l` flag to indicate to the utility that we want more information than it usually provides, and so it should show us the directory contents in a long format (`-l` is short for "long"). Last, the utility wants to know, "But which directory should I list the contents of?" Using the argument, we reply, "Show me the contents of my Desktop."

In all cases, to submit a command to the computer, press enter. Now, let's start learning some useful commands!

## Basic Utilities

Here is a list of basic utilities that you will use on a regular basis. Anything in capital letters that starts with a dollar sign, like `$THIS`, is an argument to the utility. You should replace `$THIS` with the actual argument you want to give the computer.

```
man $UTIL
```

**man**ual. Get information for how to use any utility. Replace `$UTIL` with any utility, like `ls`, `cd`, or even `man`! Press the up and down arrows to scroll through the documentation. Press Q to quit and go back to the command line.

```
ls $DIR
```

**l**i**s**t. Lists the contents of the directory `$DIR`. If no directory is specified, lists the contents of the current working directory. Use the `-l` flag to get more information.

```
cd $DIR
```

**c**hange **d**irectory. Changes the current working directory to the directory `$DIR`. In effect, moves you around the computer.

```
pwd
```

**p**rint **w**orking **d**irectory. If you ever get lost in the computer, run this command to get a trail of breadcrumbs all the way down from the top level of the computer to see where you are.

```
less $FILE
```

Displays the contents of a file. Press the up and down arrows to scroll though the file. Press Q to quit and go back to the command line.

```
cp $FILE $LOCATION
```

**c**o**p**y. Copies the `$FILE` to the `$LOCATION`.

```
mv $FILE $LOCATION
```

**m**o**v**e. Moves the `$FILE` to the `$LOCATION`.

```
rm $FILE
```

**r**e**m**ove. Deletes a file **permanently**: there is no way to get it back. [Be careful when using this command!](https://www.davidbaumgold.com/tutorials/command-line/#warnings)

```
sudo $CMD
```

**s**uper **u**ser **do**. When you use this utility, you use an entire command as a single argument: for example, `sudo ls -l ~/Desktop`. `sudo` asks for your user account password. As a security measure, the screen does not display anything as you type, not even asterisks (`*`). If the password is typed in correctly, `sudo` executes the `$CMD` with elevated permissions. [Be careful when using this command!](https://www.davidbaumgold.com/tutorials/command-line/#warnings)

A note about using `sudo`: The computer has a few built-in safety restraints to prevent normal users from doing bad things, like deleting critical files. The super user has no such restraints. Note that the super user is not necessarily bad: you must use `sudo` to install programs and do anything else that affects how your computer runs.

## Moving Around the Computer

Lets start by using `ls` to look around your computer. Try typing `ls` into the command line and pressing enter. The computer will reply with a list of names. These names are the names of files and folders in the directory you are currently in. Whenever you open up a new command line, you start in your home directory, which is the directory that generally contains all of your files.

Well, that's nice. But what if we want to go someplace else? That's what `cd` is for. `cd` requires an argument: if you tell the computer you want to go somewhere, you also have to tell it where you are going. Try entering this command:

Remember, to press enter once you have finished typing. The computer will not reply, but you are now sitting in your Documents directory. You can test this by running `ls` again: the list of names will be different.

So where do we go from here? How do we know which of these names are folders (that we can go into) and which are files (that we can't)? For that, we need more information from the ls command. Let's give it the `-F` flag to tell us about files and folders. Try entering this command:

You will notice that this time, some of the names that the computer returns to you will have a slash after them. These names are folders: the rest are files. You can always cd into a folder by running cd with the folder name as an argument, as long as you can see that folder with `ls -F`.

When you're done looking in folders, it's time to go back up. But how? Luckily, every folder contains a hidden link back up. To see these hidden links, we will use the `-a` flag for ls to see all. There are at least two hidden links in every folder. The `.` (one period) link takes you back to the same folder you are currently in — it doesn't take you anywhere. The `..` (two periods) link takes you back up to the parent folder. In fact, you can give the `ls` command multiple flags, like so:

If you run this command, you will notice that the `.` and `..` hidden links have slashes next to them, which means you can use them with cd! To go back up a folder, you can always run:

```
cd ..
```

Remember that if you ever get lost in the computer, you can run `pwd` to see where you are.

## Neat Tricks

Computer programmers are lazy. Because they are lazy, they invented some techniques to do more with less work. Here are some of those techniques:

### Tab Autocompletion

Whenever you need to type out a location in an argument (for example, in the `cd` command), you don't have to type out the whole thing: the first few letters will do. Once you've typed three or four letters, press the tab key, and the command line will fill in the rest for you! For example, if you are in your home directory, and you type `cd Desk` and then press the tab key, the command line will automatically complete the command to read `cd Desktop`! You can also use this if you find yourself mistyping folder names: tab autocompletion will always fill it in correctly.

### Shortcuts

The command line has a few shortcuts built in. For example, to see your previously typed command, just press the up button. You can do this to submit the same command multiple times, or to edit a command that you didn't type in quite right. Another shortcut: you can use `~` (tilde) to refer to your home directory: `cd ~` will take you back there.

## Warnings

Remember, when you use the command line, the computer will cheerfully do anything it can for you. If you ask it to do something bad, it will try to do so. Some people take advantage of this fact by telling novice command line users to run commands that do nasty things to your computer. Here are a few to watch out for. **Never run any of these commands! They can and will destroy your computer!**

```
sudo rm -rf /
```

The command to remove a file is `rm`. You can also use `rm` to remove multiple files at a time. This command tells the computer to start at the top of the file structure, and delete _every single file on the computer_ without stopping. After this command has run, your computer be empty. If you turn it off, it will not be able to turn back on until you reinstall an operating system on it.

```
:(){ :|:& };:
```

This interesting-looking piece of code is called a [fork bomb](https://en.wikipedia.org/wiki/Fork_bomb). Like a virus, it will continually multiply and subdivide itself, asking for more and more resources from the computer, until the entire computer is trying to process this code. As a result, the computer has no resources left for any other programs or processes, and will freeze or crash. Fortunately, rebooting your computer should cure it.