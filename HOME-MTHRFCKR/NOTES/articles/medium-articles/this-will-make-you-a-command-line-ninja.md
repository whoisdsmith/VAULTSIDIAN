---
tags:: medium
created: 2022-08-05T17:15:19 (UTC -04:00)
tags: []
source: https://medium.com/pythonland/this-will-make-you-a-command-line-ninja-5f19755e1745
author: Erik van Baaren
---

# This Will Make You a Command-Line Ninja | by Erik van Baaren | Python Land | Medium

---
## Lift your skills with these tips, tricks, and a bit of effort

![[0zoqx_HaUhMH0tI_P.jpeg]]

Photo by [Aisha Askhadova](https://unsplash.com/@aiiveny?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com/?utm_source=medium&utm_medium=referral)

A well-crafted bash command or script can save hours of manual labor. This tutorial will show you exactly how easy it is to become a command-line ninja and automate those tedious tasks. If you need to polish your basics, head over to [**Shell Commands Every Developer Must Know**](https://medium.com/pythonland/shell-commands-every-developer-must-know-8257931c5521).

## 1\. The Unix philosophy

The command line has been around for decades and it’s still going strong. Part of that success comes from the Unix philosophy:

-   Write programs that do one thing and do it well.
-   Write programs to work together.
-   Write programs to handle text streams, because that is a universal interface.

When working with the command line, it’s good to keep this philosophy in mind. You’ll find that there’s always a combination of tools that does exactly what you want. The art is finding them and combining them properly.

For this article, I do assume you have basic knowledge of the command line. You should know what a terminal is and how to start one. You must be able to edit files and be familiar with basic commands, like `cd`, `ls`, `cat`, and `less`.

## 2\. Creating shell scripts

Let’s start our journey with the ability to create scripts. With scripts, you can run sequences of commands. They prevent you from repeating yourself and allow you to store long and tedious to type commands for later usage.

A command-line script starts with the shebang — a sequence of the two characters `#!`. After these two characters, you can name any interpreter and a bunch of arguments, like this:

```
#!interpreter [optional arguments]
```

A shell script is usually based on the most popular shell called Bash, so this would simply become:

```
#!/bin/bash
```

You can stop reading here and go to the next section, or continue reading for some useful extra info.

Sometimes you’ll see this instead:

```
#!/usr/bin/env bash
```

When using `/usr/bin/env`, the bash command will be searched for in the current `$PATH`, instead of hardcoding it to the `/bin` directory. Bash will almost always be found at `/bin/bash`, so the first method is fine for us.

However, you may want to use this trick to create an executable Python script. Python can be installed anywhere, depending on the way it is installed. I’ve seen it in `/usr/bin/`, `/bin`, and `/usr/local/bin` , just to name a few.

We’ll get to creating an actual shell script in a moment. But first, we’ll take a look at for-loops to juice things up a little.

## 3\. Variables

Just like other languages, Bash has variables. One peculiar thing about variables in Bash is that you access them with the dollar sign, but you set them without it. To clarify, here’s an example:

```
myvar="Hello world"echo $myvar
```

Bash has several reserved variables that are automatically set for you. They can be very useful. Here’s a non-exhaustive list:

-   **$0** — The name of the current script.
-   **$1 … $9** — The first 9 arguments to the script.
-   **$#** — number of arguments passed to the script.
-   **$@** — All the arguments supplied to the script.
-   **$USER** — The username of the user running the script.
-   **$HOSTNAME** — The hostname of the machine the script is running on.
-   **$SECONDS** — The number of seconds since the script was started.
-   **$RANDOM** — Returns a different random number each time is it referred to.
-   **$LINENO** — Returns the current line number in the Bash script.

## 4\. Using for-loops

The usefulness of the command-line, and especially scripts, increases exponentially once you master loops. And even though they might look scary, they are really not that hard.

The basic syntax of a loop is:

```
for VARIABLE in A LISTdo  command1  command2  commandNdone
```

‘A LIST’ can be anything: file names, numbers, or strings. In most scripts, it will be a list of file names, though.

Now that we know how to create a loop, let’s look at our first script:

In the last for-loop, I used the expression `$(ls)`. This executes the command between parentheses and substitutes the result. In this case, `ls` gets executed and the for-loop is fed with the file names that ls prints out.

To start this script, we can do two things. First, we can run it with:

```
$ bash loop.sh
```

The second way, which I recommend, is making the file executable. The OS will know how to execute our file because of our shebang line at the top.

Making the file executable is done by setting the file’s “execute flag” like this:

```
$ chmod +x loop.sh
```

You can now run the script with `./loop.sh`

The output in my case is:

```
You can just list a bunch of numbers and text like this:123fourOr specify a range of numbers:12345Or use the output of another command:loop.shnotes.txt
```

It might differ for you, depending on which files are in the directory in which you’re running the script.

## 5\. Scripts with arguments

We’re able to create a shell script, but this script will just do the same thing each time you run it. We can make it infinitely more interesting by using arguments.

Here’s an example, call it `arguments.sh`:

```
#!/bin/bashecho "Hello $1, from $0"
```

If we run this with one argument, the result is as follows:

```
$ ./arguments.sh WeirdoHello Weirdo, from ./arguments.sh
```

What Bash does, is chop up your _entire_ command and assign it to the not very imaginative variables `$0`, `$1`, `$2`, etcetera. As you can see, the first part of our command is the name of the script itself. This can come in handy, as can be seen in the next section.

## 6\. A much-needed safety net

Before moving on to the serious stuff, I want to teach you about an important safety net.

Once you start creating scripts, you will inevitably make mistakes. We all do. One very common mistake in scripts can be especially disastrous. It’s the unset variable. If you don’t know what I mean, just keep reading as it will become clear in a moment.

We can prevent using unset variables by starting our scripts with the following command:

```
set -u
```

That’s all! From here on, your script is treating unset variables as an error when you are substituting.

For example, this script will fail:

```
#!/bin/bashset -urm -rf /$my_directory
```

The output:

```
$ ./test.sh                                                          ./test.sh: 3: ./test.sh: my_directory: parameter not set
```

That’s because I never set `$my_directory`. Without `set -u`, it won’t fail but instead just ignore the empty variable, leaving us with the command `rm -rf /`. We all know what that does, right? If executed by a privileged user (like root), this mistake would have wiped my entire filesystem instead of the directory I intended to delete.

**_Make it a habit to always put_** `**_set -u_**` **_at the top of your scripts._**

## 7\. Conditions: if… then… else…fi

Sometimes you only want to run a command if a certain condition is true. For this, we have the if… then… else…fi construct.

Our previous `arguments.sh` example contained a little problem. It expects a name in `$1` without checking if it actually gets one. Let’s fix this:

```
#!/bin/bashif test -z "$1"then  echo "Usage: $0 <Your name>"else  echo "Hello $1, from $0"fi
```

With `test -z` we can check if a variable’s length is zero. If that is the case, we print some friendly usage instructions:

```
$ ./arguments.shUsage: ./arguments.sh <Your name>
```

The test command can test for _many things_. The full list can be seen when you enter `man test`.

That’s right, you don’t need Google for everything! _Using man-pages is part of being a command-line ninja!_ You’ll find that there’s a man page for pretty much everything you can do in your terminal.

Here is one more example in which we compare two values to see if they are the same:

```
#!/bin/bashfor i in {1..10}do  if test $i -eq 3   then    echo "I found the 3!"  fidone
```

This loop runs for 10 iterations and checks if $i is equal to 3 each time. Can you predict the output?

As you can see, the `else`\-part is optional, but you always need to end with a `fi`.

## 8\. Using the find command

There’s a powerful command that can save you lots of headaches when used in the right places — it’s called `find`.

Find, in its base, walks the file tree starting from the provided path. It then prints each directory and file, including its path relative to the current working directory.

Just try it, enter the following and see what output you get:

```
$ find .
```

I’m currently in a directory created for this article, its contents according to `find` are:

```
../images./images/cover.jpg./scripts./scripts/loop.sh./scripts/arguments.sh./scripts/words.txt
```

The first dot is simply the current directory. If you only want to list files, use:

```
$ find . -type f
```

If you only want to list directories, use:

```
find . -type d
```

## Expressions

These are just the basics. Find also takes expressions, which further narrows down what files it should return. A useful expression that I use often is `-mtime`. The following command returns all files that were modified more than 5 minutes ago. For MacOS:

```
$ find . -type f -mtime +5m
```

The m is a modifier; your options are:

-   **s:** second
-   **m:** minute (60 seconds)
-   **h:** hour (60 minutes)
-   **d:** day (24 hours)
-   **w**: week (7 days)

The plus sign is important as well:

-   a preceding plus sign means “more than n’’
-   a preceding minus sign means “less than n’’
-   neither means “exactly n’’

On many Linux distributions, find behaves a little different, and you’ll need to use:

```
$ find . -type f -mmin +5
```

This will also find all files older than 5 minutes. As far as I can see, there’s no way to use the s/m/h/d/w modifiers, so you’ll need to convert everything to minutes.

Another handy expression is `-name`, which will filter the results based on the file name. For the name, you can use a shell pattern. So the command `find . -name "*.txt"` will only return files with the .txt extension.

## Using the results

With our new ninja scripting powers, we can now use find to return a bunch of files, feed them to our for loop and do some awesome stuff with them, right?

True, but since it’s pretty obvious you want to perform some actions on the returned files, find has us covered already. No scripting is necessary.

Say you want to delete the files that match your criteria, you can simply add `-delete` to your find-command. This is obviously a bit dangerous, so before using this flag, always check the output of the find command without it first.

What gives us much more flexibility is the `-exec` flag. It allows us to execute any command. An example that you may have seen before is this one:

```
$ find /path/to/files* -mtime +5m -exec rm {} +
```

Let’s break it down:

-   find all files in the given path that were modified more than 5 minutes ago
-   execute the rm command (which deletes the files)
-   `{} +` is replaced with as many pathnames as possible for each invocation of the given utility (in our case ls)

**It’s a very efficient way of removing _lots_ of files, like thousands or even millions.**

A slight alternative to this command is:

```
$ find /path/to/files* -mtime +5m -exec rm {} \;
```

The difference is that `rm` is now executed for **_every single file_** instead of as many files per batch as your system allows. Which version you use depends on the command you’re executing on the results.

If you can use the one with the plus sign, it’s a lot faster! That’s because the command is executed on many files at once, saving your OS lots of CPU cycles that are needed to open, start, run, and exit a program. However, some commands take just one file at a time, and for those, the second version comes to the rescue.

And again: if you enter `man find`, you’ll get the full documentation. But I’ll admit — I tend to google this stuff too because you generally get useful examples instead of needing to plow through the raw documentation. However, always try to understand exactly what you’re pasting into your terminal before hitting enter!

## 9\. Working with pipes

A pipe bridges two processes together. The pipe, written with the `|` character, connects the output of one command to the input of the second. It’s one of the fundamental building blocks of a Unix shell.

An elementary example is using `cat` to feed the contents of a file to the word count tool `wc`:

```
$ cat <filename> | wc
```

Just in case you didn’t know these commands:

-   `cat` prints the contents of a file.
-   `wc` counts all the lines, words, and bytes it is fed. Another often-used version is `wc -l`, which only counts the number of lines in a file.

Let’s try this. First, create a file called `words.txt` with this content:

```
helloworldpythonninjaareyou?321
```

Then run this command:

```
$ cat words.txt | wc -l
```

The output should be 10 since there are 10 lines in the file. Another example is using sort to sort the words in your file:

```
$ cat words.txt | sort
```

The output should be:

```
?arehelloninjapythonworldyou123
```

As we can see, all the words from the words.txt file are fed to sort, which sorts them — punctuation first, then numbers, and then letters.

Alright. Here’s one last, questionable example of using pipes. There’s this awesome tool called `cowsay`. Cowsay generates an ASCII picture of a cow saying something that you feed it:

```
$ echo "Are we going to learn anything useful?" | cowsay ________________________________________< Are we going to learn anything useful? > ----------------------------------------        \   ^__^         \  (oo)\_______            (__)\       )\/\                ||----w |                ||     ||
```

This is the stuff that will make a lasting impression on your colleagues.

## 10\. Parsing JSON with jq

I think we’ve played around enough. It’s time to actually learn some useful stuff that you can apply in your daily work! Since JSON is super ubiquitous, I’d like to teach you some useful command-line JSON processing voodoo first.

The jq tool is usually not installed by default. If you don’t have it, please install it for your operating system. If you’re on MacOS, you might want to look into [Homebrew](https://medium.com/tech-explained/how-to-get-and-use-the-ultimate-macos-package-manager-f2ba5c9466d4).

An elementary example of jq usage is this:

```
echo '{ "Price": 10.0, "Name": "Cable" }' | jq
```

The result is a well-formatted, colorized version of the JSON you feed it:

![[1U-ay0n_D0a0x6inGovS16w.png]]

jq will pretty-print your JSON by default

I actually use it a lot for this purpose. If you just want to view the content of a JSON file, a simple `cat filename.json | jq` will instantly help you out. But jq can do so much more — it’s a full-fledged command-line JSON processor.

Say, for example, that you are only interested in the price field. You can simply obtain the price with the following command:

```
echo '{ "Price": 10.0, "Name": "Cable" }' | jq ".Price"
```

Try it — the result should be 10. This is still just touching the very basics. Just remember that jq exists and that you can get pretty much anything from your JSON files with it. You can read the man page or search google to find more advanced examples.

## A real-world example

How about a script that parses files names from a large pile of JSON files and then does something with those files, like analyzing the image or whatever? Sounds realistic enough, right?

OK, let’s get started. Suppose that all we got was a large file tree with JSON files scattered over multiple subdirectories. These JSON files contain meta-data about image files we need to analyze. Our first task would be to find those JSON files. We can use the find command for this:

```
find . -type f -name “*.json”
```

This will find all JSON files in all directories and sub-directories, starting from the current one. The `-name` condition ensures it will only return files ending with `.json`.

I created a bunch of test files. The hierarchy looks like this (created with the `tree` command):

```
.├── file1.json├── file2.json└── subdir    └── file3.json
```

The find command, in this case, returns:

```
$ find . -type f -name "*.json"./subdir/file3.json./file2.json./file1.json
```

Nice. So, what’s next? Parsing the image filename from the JSON file. The JSON files I created look like this:

```
{  "imagefile": "file1.gif",  "dimensions": "1024x768",  "author": "unknown"}
```

So we need to get the contents of the `imagefile`\-field, in this case `file1.gif`. We’ve done this before with`jq`. Let’s try it:

```
$ cat file1.json | jq ".imagefile""file1.gif"
```

Ahh, that was easy! What’s left is tying it all together and running our imaginary analysis software on the image:

```
#!/bin/bashfor imagejson in $(find . -type f -name "*.json")do  imagefile=$(cat $imagejson | jq ".imagefile")  echo "Analysing $imagefile"  ./run_analysis.sh $imagefiledone
```

See? It’s not that hard if you chop up the task in smaller steps and tie everything together in a script!

## 11\. Serious ninja stuff with xargs

For those who didn’t get that ninja feeling by now, this is for you. We’ll combine all our newly learned superpowers and perform parallel computing, all with a single terminal command!

`Xargs` reads items from standard input (meaning, you can pipe data to it) and executes the specified command.

The basic syntax for `xargs` is:

```
xargs [options] [command [initial-arguments]]
```

At first sight, you might not see the benefits of this. Why not create a while loop and run each command? The benefit of `xargs` is that it can batch arguments and call your command once on many files instead of individually for each file.

_But find can do so too!_

Yup, you’re right. Still, there are more advantages. Xargs will work without needing `find`. So that’s one. But `xargs` has a special trick up its sleeve: it can run commands in parallel with the `-P` option.

This option takes a number that defines how many processes it needs to start in parallel. You read that right — in parallel!

One real-world example is to use this when doing video conversion on lots of files. Let’s dissect the following command together:

```
find . -name "*.mpeg" | xargs -P 4 -I {} ffmpeg -i {} -o {}.mp4
```

First, we find all MPEG files. We feed these files to `xargs`. Next, we tell `xargs`, with `-P 4`, to use four processes concurrently. We also tell `xargs` to substitute the file name in all places where it encounters `{}` with the `-I` option.

So `xargs` gets the first video file and starts `ffmpeg`. Instead of waiting for `ffmpeg` to finish, `xargs` starts another instance of `ffmpeg` processing the second file in parallel. This goes on until it reaches four processes. If all four slots are taken, `xargs` waits for one to finish before starting the next process.

Video conversion is mostly CPU-bound. If your computer has four CPU cores, this conversion will go four times faster than regular find or a while loop. Isn’t that awesome?!

## 12\. Using history

Now you know all the awesome commands, but next week you’ll notice you already forgot them. Yes — even ninjas forget. Luckily, there are tools to help us out.

You can use the **up** and **down** keys to scroll through previously typed commands. But that’s not all. Here are some history-based time savers:

-   use `history n`, where n is the maximum number of lines you want to see.
-   repeat the last command with `!!`
-   repeat command number _n_ from history with `!n`
-   `!cd` — rerun the last command you typed starting with, in this case, ‘cd’
-   `!*` — substitute the arguments from the previous command

Perhaps the most powerful way to use the terminal history is by searching through it. If you hit `control + r`, you’ll get a search prompt that matches text from your history. Just start typing any part of a previous command, and you’ll find it back!

## 13\. How Unix works

If you followed this guide, you should have a solid base to explore further.

If you want to dive in deeper, I strongly recommend this excellent article: [How Unix works](https://link.medium.com/9A4UJTClk3). If you read it thoroughly, you’ll gain a much deeper understanding of your operating system and the command line.

## Wrap up

Thank you for reading. Please leave a private note or comment if anything is unclear or needs improvement. You’ll be helping out many others with your contribution.

That’s it! If you have valuable tricks to share, please leave a comment and help out our fellow coders.

## Support me

If you’re not a Medium member already, consider [signing up through this link](https://medium.com/@eriky/membership). You’ll get access to _all_ the articles on Medium without ads. With the link, I get a monthly commission at no cost to you.
