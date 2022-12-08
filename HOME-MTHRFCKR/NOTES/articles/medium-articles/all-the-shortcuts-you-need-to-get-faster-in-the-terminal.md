---
tags:: medium
created: 2022-08-05T17:17:08 (UTC -04:00)
tags: []
source: https://levelup.gitconnected.com/all-the-shortcuts-you-need-to-get-faster-in-the-terminal-ce91b91ecf91
author: Ankan Bag
---

# All the shortcuts you need to get faster in the terminal. | by Ankan Bag | Level Up Coding

---
## These shortcuts will help beginners and power users, get more work done in less time.

![[0FDnZPUcXPoDPLdw5.jpeg]]

Photo by [Alex Chumak](https://unsplash.com/@ralexnder?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com/?utm_source=medium&utm_medium=referral)

> “All the best people in life seem to like LINUX.”
> 
> ~Steve Wozniak, co-founder of Apple

Do you know what most of the senior devs in the industry have in common? Most of them have a basic knowledge of the _command-line interface._ Having a working knowledge of the terminal gives you a competitive advantage over other devs. Using the terminal can also enhance your workflow greatly but these tricks will take it to the next level.

Almost all Operating Systems have a built-in CLI for the power users to take control over the system and launch missiles (I wish!). But the Windows PowerShell was somewhat limiting so the people at _Microsoft built ‘Windows Subsystem for Linux (WSL2.0)’_ for the developers (even they realized lately). So to learn the basics you don’t have to leave the comfort of your existing machine.

## Why consider using a Terminal in the first place?

It is very common to be afraid of the terminal, even I was afraid of it, 3 years back when I entered the tech world and used to run Windows as my daily driver. We feel very comfortable using the GUI and many even consider it to be a relic of the past (which is !true). Here are some of the reasons why it is still around today.

-   **Automating everyday repetitive tasks:** Ever wondered how boring things get when you want to update the server every Sunday at midnight! or run a script at a specific time of a specific day or open an application right when you start the machine. Well, terminal got you covered, you can set a cron job to do such things and never have to worry again. You can’t automate these things from the GUI.
-   **More control over the Operating System:** You can run commands to change permissions of a file, find the largest files in your system, interact with databases, start and manage servers, manage processes, perform a quick DNS lookup, ping other machines in your network, and much more. With GUI, you can do some of the above tasks but most of those tasks are reserved for the terminal only.

![[1iEo6zQG_M0-tHyviseEX9w.png]]

Find the 10 biggest files in a directory (just replace /usr/bin/ with the desired directory)

-   **Cloud Computing:** If you have worked in the industry, then you will definitely come across this term a lot nowadays. To work on this technology, you are required to have some basic knowledge of the terminal like _ssh-ing_ to the server.
-   **It is literally faster to do stuff from the terminal:** Let’s imagine I want you to make 52 different folders for each week in a year and then inside of each folder you want to make 7 different files for each day in a week. How will you achieve that in a GUI? right-clicking and clicking new-folder 364 times? Or you can type in one command (check the image below) in the terminal to do the same! Isn’t it faster?

![[1wQb-TeiuxyOFVarDMzhZog.png]]

Creating files for every week of the year.

-   **It’s a lot more fun to work with:** Apart from doing serious work, you can do a lot of fun stuff in the terminal too. Like updating your Twitter status randomly every day at 6 pm! or running a steam engine as a punishment for mistyping sl instead of ls or getting a fortune cookie every day or finding prime factors of any number or making a cow say something and a lot more.

![[1UC6f2Xdrr3OMPvYe3RTOEQ.png]]

Update Twitter Status using **‘curl’**

If you are convinced about using the terminal, we shall now discuss the main topic of today.

## Top terminal tricks.

> “Intelligence is the ability to avoid doing work, yet getting the work done.”
> 
> ~ Linus Torvalds, creator of LINUX Kernel

By now, you know using the terminal is faster already but there exist tonnes of shortcuts that can take you to the moon (without crash landing!). Seriously, you can use some of the listed shortcuts and terminal aliases to let it do all the heavy lifting for you. Knowing these shortcuts will let you tame this wild beast and let you do things with the snap of your fingers instantly (like Thanos).

## 1\. Autocompleting commands.

**Tab autocompletion:** This is probably the most important and common of all. You can write a few letters of the command or file and hit tab, the command or the file name would be filled automatically.

## 2\. Cutting and pasting in the terminal.

If you try to copy, cut or paste texts in the prompt using keyboard shortcuts, you might have noticed that it doesn’t work at all. To paste texts that you copied from StackOverflow, in the terminal, you have to press **‘_ctrl-shift-v_’**. Similarly to copy or cut texts from the command line, you have to press **‘ctrl-shift-c’** and **‘ctrl-shift-x’** respectively. But wait, there’s more trick in the terminal too.

Here’s more than your normal cut, copy and paste. Explore!

**ctrl-k:** cuts/kills the text from the current cursor location until the end of the line.

**ctrl-u:** cuts/kills the text from the current cursor location to the beginning of the line.

**ctrl-w:** cuts/kills the text from the current cursor location through the beginning of the word.

**alt-d:** cuts/kills the text from the current cursor location through the end of the word.

**ctrl-y:** when we kill texts using the above commands, the “killed” text is stored in a memory known as the “kill-ring”. _‘ctrl-y’_ retrieves the texts and pastes them below the cursor.

## 3\. Jumping in the command line.

What happens when you made a typo at the beginning, the middle or the end of a big line. Well, you have to press the arrow key endlessly to get there. These keyboard shortcuts will let you get there quicker.

**ctrl-a:** moves the cursor to the beginning of the line. This is similar to pressing the _Home_ button on the keyboard.

**ctrl-e:** moves the cursor to the end of the line. This is similar to pressing the _End_ button on the keyboard.

**ctrl-f:** moves the cursor forward one character at a time (same as the right arrow).

**ctrl-b:** moves the cursor backward one character at a time (same as the left arrow).

**alt-f:** moves the cursor forward one word (same as pressing ctrl + right arrow).

**alt-b:** moves the cursor forward one word (same as pressing ctrl + right arrow).

**ctrl-t:** swaps the current character under the cursor with the one preceding it. This can be useful to correct typos very quickly!

## 4\. Searching the history and history expansion.

Bash keeps a record of the commands we enter inside an actual file at _~/.bash\_history._ You can view the file inside your home directory and can scroll through the history one command at a time using the up and down arrows. We can also use the **_history_** command to view the entire history. But generally, it is easier to manage if we pipe the output to _less_.

**Reverse-i-search (ctrl-r):** As you are typing the bash will start searching the history and populate the closest matching command executed recently. You can also press **ctrl-r** to search for the next matching command in recent history.

![[1dhFQM4oAsjumjtcLmwjdxg.gif]]

Reverse searching with (ctrl-r)

**Auto populating from the history:** Have you ever entered a command, only to realize that you forget to give the necessary permission for that. For example, you typed `apt install cmatrix` and forget to precede the command with sudo. Well, you can type `sudo !!` and it will expand to `sudo apt install cmatrix`_._ **!! operator expands into the previous command.**

![[1o49YWpyCt-J0sqdOw74O2w.png]]

Using the !! to replace with the previous command

Another history expansion is when you want to auto-fill only the previous argument of the previous commands. press **alt-.** _to cycle through the relative argument of the previous commands._

## 5\. Expansions in the terminal.

Remember the example where I created 52 folders and 364 files in a single command, I used something called _brace expansion_.

**Wildcards or Globbing patterns:** We can use special wildcard characters to make patterns that can match multiple filenames at once.

**The asterisk ( \* ) wildcard:** The asterisk character represents zero or more characters in a file name. For example, `ls *.js` will match any files that end with _.js_ like _index.js_ and _app.js_ in the current directory and`cat pink*` will match any file that starts with _“pink”_ in its names like _pinky.pdf_ or _pinkSky.js_

**The question ( ? ) wildcard:** The question mark character represents any single character in a file name. For example, `ls index.???` will match any files named “index” with the extension of length 3 like _index.htm_ or _index.css_ but not _index.html_

**Range wildcards:** Square brackets (\[\]) are used for specifying a range of characters to match. Any character inside the brackets will be matched individually. For example, `ls file[0–9]` will match _file1, file2_, up to _file9_ and `ls *[abc]` will match any file ending with a, b, or c. like _manga_, _bob_, and _thicc_.

We can also negate these range wildcards by simply using a caret (^) at the beginning of the characters like `ls [^A]*` will match any file that does not start with a capital ‘A’.

**Brace Expansion:** Brace Expansion is used to generate arbitrary strings. It will generate multiple strings based on the given pattern. To use that we provide a set of strings inside of curly braces ({}), as well as optional suffixed and prefixes. For example, `touch count-{123}.txt` will generate three files: _count-1.txt, count-2.txt, count-3.txt._ We can also specify ranges by using (..) in between the characters like `touch count-{1..3}` will do the same thing as the earlier command. We can also do nesting with this expansion like `echo {a,b{1..5},c}` will print _a, b1, b2, b3, b4, b5, c._

## Create your own Commands!

Aliases are like keyboard shortcuts but for the terminal and supercharged. They are the most useful shortcuts of them all. You can do a lot of complex jobs with just a single command. These are helpful for commands, you use the most like you can set an alias `gcm` to do `git commit -am` which is much faster to type.

To create an alias, we have to edit a file called _~/.bashrc_ or _~./bash\_profile._ Inside the file, you can set your alias by writing `alias <your_alias_name> = “type command to execute”` . For example, `alias pss=”ps -aux | grep”` will let you search the currently running processes, you can now type `pss chrome` and it will search for all the processes that belong to chrome.

![[1i1ZQLSLu5ilaZygKhiF-8g.png]]

Setting custom aliases inside the ~/.bashrc file

## Ending note.

Congratulations! now you can consider yourself a terminal superhero. Now you have the ultimate control over the terminal. And you can also make your own little commands using existing commands to do a more complex job. You can also use these tricks to impress your peers at work.

May the power of the terminal be with you!
