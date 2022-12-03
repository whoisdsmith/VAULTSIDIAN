Simply put, the shell is a program that takes commands from the keyboard and gives them to the operating system to perform. In the old days, it was the only user interface available on a Unix-like system such as Linux. Nowadays, we have _graphical user interfaces (GUIs)_ in addition to _command line interfaces (CLIs)_ such as the shell.

On most Linux systems a program called `[bash](http://linuxcommand.org/lc3_man_pages/bash1.html)` (which stands for Bourne Again SHell, an enhanced version of the original Unix shell program, `sh`, written by Steve Bourne) acts as the shell program. Besides `bash`, there are other shell programs available for Linux systems. These include: `ksh`, `tcsh` and `zsh`.

## What's a "Terminal?"

It's a program called a _terminal emulator_. This is a program that opens a window and lets you interact with the shell. There are a bunch of different terminal emulators we can use. Some Linux distributions install several. These might include `gnome-terminal`, `konsole`, `xterm`, `rxvt`, `kvt`, `nxterm`, and `eterm`.

## Starting a Terminal

Window managers usually have a way to launch a terminal from the menu. Look through the list of programs to see if anything looks like a terminal emulator. While there are a number of different terminal emulators, they all do the same thing. They give us access to a shell session. You will probably develop a preference for one, based on the different bells and whistles it provides.

## Testing the Keyboard

OK, let's try some typing. Bring up a terminal window. The first thing we should see is a _shell prompt_ that contains our user name and the name of the machine followed by a dollar sign. Something like this:

\[me@linuxbox me\]$

Excellent! Now type some nonsense characters and press the enter key.

\[me@linuxbox me\]$ `kdkjflajfks`

If all went well, we should have gotten an error message complaining that it cannot understand the command:

\[me@linuxbox me\]$ `kdkjflajfks` bash: kdkjflajfks: command not found

Wonderful! Now press the up-arrow key. Watch how our previous command "kdkjflajfks" returns. Yes, we have _command history_. Press the down-arrow and we get the blank line again.

Recall the "kdkjflajfks" command using the up-arrow key if needed. Now, try the left and right-arrow keys. We can position the text cursor anywhere in the command line. This allows us to easily correct mistakes.

## You're not operating as root, are you?

If the last character of your shell prompt is # rather than $, you are operating as the _superuser_. This means that you have administrative privileges. This can be dangerous, since you are able to delete or overwrite any file on the system. Unless you absolutely need administrative privileges, do not operate as the superuser.

## Using the Mouse

Even though the shell is a command line interface, the mouse is still handy.

Besides using the mouse to scroll the contents of the terminal window, we can can use it to copy text. Drag the mouse over some text (for example, "kdkjflajfks" right here on the browser window) while holding down the left button. The text should highlight. Release the left button and move the mouse pointer to the terminal window and press the middle mouse button (alternately, press both the left and right buttons at the same time when working on a touch pad). The text we highlighted in the browser window should be copied into the command line.

## Further Reading

-   The [Wikipedia entry for Steve Bourne](https://en.wikipedia.org/wiki/Stephen_R._Bourne), developer of the original Bourne shell
-   The [Wikipedia article on the Unix shell](https://en.wikipedia.org/wiki/Unix_shell), the place where all this fun got started
-   The ["Power Terminals"](http://linuxcommand.org/lc3_adv_powerterm.php) Adventure