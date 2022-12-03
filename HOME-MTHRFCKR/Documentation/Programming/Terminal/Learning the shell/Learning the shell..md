Why do you need to learn the command line anyway? Well, let me tell you a story. Many years ago we had a problem where I worked. There was a shared drive on one of our file servers that kept getting full. I won't mention that this legacy operating system did not support user quotas; that's another story. But the server kept getting full and it stopped people from working. One of our software engineers spent a couple of hours writing a C++ program that would look through all the user's directories and add up the space they were using and make a listing of the results. Since I was forced to use the legacy OS while I was on the job, I installed [a Linux-like command line environment for it.](http://www.cygwin.com/) When I heard about the problem, I realized I could perform this task with this single line:

du -s \* | sort -nr > $HOME/user\_space\_report.txt

Graphical user interfaces (GUIs) are helpful for many tasks, but they are not good for all tasks. I have long felt that most computers today are not powered by electricity. They instead seem to be powered by the "pumping" motion of the mouse. Computers were supposed to free us from manual labor, but how many times have you performed some task you felt sure the computer should be able to do but you ended up doing the work yourself by tediously working the mouse? Pointing and clicking, pointing and clicking.

I once heard an author say that when you are a child you use a computer by looking at the pictures. When you grow up, you learn to read and write. Welcome to Computer Literacy 101. Now let's get to work.

## Contents

1.  [What is "the Shell"?](http://linuxcommand.org/lc3_lts0010.php)
2.  [Navigation](http://linuxcommand.org/lc3_lts0020.php)
3.  [Looking Around](http://linuxcommand.org/lc3_lts0030.php)
4.  [A Guided Tour](http://linuxcommand.org/lc3_lts0040.php)
5.  [Manipulating Files](http://linuxcommand.org/lc3_lts0050.php)
6.  [Working with Commands](http://linuxcommand.org/lc3_lts0060.php)
7.  [I/O Redirection](http://linuxcommand.org/lc3_lts0070.php)
8.  [Expansion](http://linuxcommand.org/lc3_lts0080.php)
9.  [Permissions](http://linuxcommand.org/lc3_lts0090.php)
10.  [Job Control](http://linuxcommand.org/lc3_lts0100.php)