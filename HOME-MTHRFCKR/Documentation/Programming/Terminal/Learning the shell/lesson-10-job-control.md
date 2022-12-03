In the previous lesson, we looked at some of the implications of Linux being a multi-user operating system. In this lesson, we will examine the multitasking nature of Linux, and how it is controlled with the command line interface.

As with any multitasking operating system, Linux executes multiple, simultaneous processes. Well, they appear simultaneous, anyway. Actually, a single processor core can only execute one process at a time but the Linux kernel manages to give each process its turn at the processor and each appears to be running at the same time.

There are several commands that are used to control processes. They are:

-   `[ps](http://linuxcommand.org/lc3_man_pages/ps1.html)` - list the processes running on the system
-   `[kill](http://linuxcommand.org/lc3_man_pages/killh.html)` - send a signal to one or more processes (usually to "kill" a process)
-   `[jobs](http://linuxcommand.org/lc3_man_pages/jobsh.html)` - an alternate way of listing your own processes
-   `[bg](http://linuxcommand.org/lc3_man_pages/bgh.html)` - put a process in the background
-   `[fg](http://linuxcommand.org/lc3_man_pages/fgh.html)` - put a process in the foreground

## A Practical Example

While it may seem that this subject is rather obscure, it can be very practical for the average user who mostly works with the graphical user interface. Though it might not be apparent, most (if not all) graphical programs can be launched from the command line. Here's an example: there is a small program supplied with the X Window system called `xload` which displays a graph representing system load. We can execute this program by typing the following:

\[me@linuxbox me\]$ `xload`

Notice that the small `xload` window appears and begins to display the system load graph. On systems where `xload` is not available, try `gedit` instead. Notice also that our prompt did not reappear after the program launched. The shell is waiting for the program to finish before control returns. If we close the `xload` window, the `xload` program terminates and the prompt returns.

## Putting a Program into the Background

Now, in order to make life a little easier, we are going to launch the `xload` program again, but this time we will put it in the background so that the prompt will return. To do this, we execute xload like this:

\[me@linuxbox me\]$ `xload &` \[1\] 1223 \[me@linuxbox me\]$

In this case, the prompt returned because the process was put in the background.

Now imagine that we forgot to use the "&" symbol to put the program into the background. There is still hope. We can type `Ctrl-z` and the process will be suspended. We can verify this by seeing that the program's window is frozen. The process still exists, but is idle. To resume the process in the background, type the `bg` command (short for background). Here is an example:

\[me@linuxbox me\]$ `xload` \[2\]+ Stopped xload \[me@linuxbox me\]$ `bg` \[2\]+ xload &

## Listing Running Processes

Now that we have a process in the background, it would be helpful to display a list of the processes we have launched. To do this, we can use either the `jobs` command or the more powerful `ps` command.

\[me@linuxbox me\]$ `jobs` \[1\]+ Running xload& \[me@linuxbox me\]$ `ps` PID TTY TIME CMD 1211 pts/4 00:00:00 bash 1246 pts/4 00:00:00 xload 1247 pts/4 00:00:00 ps \[me@linuxbox me\]$

## Killing a Process

Suppose that we have a program that becomes unresponsive; how do we get rid of it? We use the `kill` command, of course. Let's try this out on `xload`. First, we need to identify the process we want to kill. We can use either `jobs` or `ps`, to do this. If we use `jobs` we will get back a job number. With `ps`, we are given a _process id_ (PID). We will do it both ways:

\[me@linuxbox me\]$ `xload &` \[1\] 1292 \[me@linuxbox me\]$ `jobs` \[1\]+ Running xload& \[me@linuxbox me\]$ `kill %1` \[me@linuxbox me\]$ `xload &` \[2\] 1293 \[1\] Terminated xload \[me@linuxbox me\]$ `ps` PID TTY TIME CMD 1280 pts/5 00:00:00 bash 1293 pts/5 00:00:00 xload 1294 pts/5 00:00:00 ps \[me@linuxbox me\]$ `kill 1293` \[2\]+ Terminated xload \[me@linuxbox me\]$

## A Little More About kill

While the `kill` command is used to "kill" processes, its real purpose is to send _signals_ to processes. Most of the time the signal is intended to tell the process to go away, but there is more to it than that. Programs (if they are properly written) listen for signals from the operating system and respond to them, most often to allow some graceful method of terminating. For example, a text editor might listen for any signal that indicates that the user is logging off, or that the computer is shutting down. When it receives this signal, it could save the work in progress before it exits. The `kill` command can send a variety of signals to processes. Typing:

kill -l

will print a list of the signals it supports. Many are rather obscure, but several are handy to know:

**Signal #**

**Name**

**Description**

**1**

**SIGHUP**

Hang up signal. Programs can listen for this signal and act upon it. This signal is sent to processes running in a terminal when you close the terminal.

**2**

**SIGINT**

Interrupt signal. This signal is given to processes to interrupt them. Programs can process this signal and act upon it. We can also issue this signal directly by typing `Ctrl-c` in the terminal window where the program is running.

**15**

**SIGTERM**

Termination signal. This signal is given to processes to terminate them. Again, programs can process this signal and act upon it. This is the default signal sent by the `kill` command if no signal is specified.

**9**

**SIGKILL**

Kill signal. This signal causes the immediate termination of the process by the Linux kernel. Programs cannot listen for this signal.

Now let's suppose that we have a program that is hopelessly hung and we want to get rid of it. Here's what we do:

1.  Use the `ps` command to get the process id (PID) of the process we want to terminate.
2.  Issue a `kill` command for that PID.
3.  If the process refuses to terminate (i.e., it is ignoring the signal), send increasingly harsh signals until it does terminate.

\[me@linuxbox me\]$ `ps x | grep bad_program` PID TTY STAT TIME COMMAND 2931 pts/5 SN 0:00 bad\_program \[me@linuxbox me\]$ `kill -SIGTERM 2931` \[me@linuxbox me\]$ `kill -SIGKILL 2931`

In the example above we used the `ps` command with the x option to list all of our processes (even those not launched from the current terminal). In addition, we piped the output of the `ps` command into `grep` to list only list the program we are interested in. Next, we used `kill` to issue a SIGTERM signal to the troublesome program. In actual practice, it is more common to do it in the following way since the default signal sent by `kill` is SIGTERM and `kill` can also use the signal number instead of the signal name:

\[me@linuxbox me\]$ `kill 2931`

Then, if the process does not terminate, force it with the SIGKILL signal:

\[me@linuxbox me\]$ `kill -9 2931`

## That's It!

This concludes the "Learning the Shell" series of lessons. In the next series, "Writing Shell Scripts," we will look at how to automate tasks with the shell.

## Further Reading

-   For a more in-depth treatment of the topic, see Chapter 10 in [_The Linux Command Line_](http://linuxcommand.org/tlcl.php).
-   [_1963 Timesharing: A Solution to Computer Bottlenecks_](https://youtu.be/Q07PhW5sCEk), a fascinating YouTube video from the Computer History Museum describing the first timesharing operating system and how it works. It's basically the same method used by all modern computers.