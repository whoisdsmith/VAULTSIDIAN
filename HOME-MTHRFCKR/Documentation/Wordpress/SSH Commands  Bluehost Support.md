# SSH Commands | Bluehost Support

Your Bluehost Account includes SSH access. This is a list of common commands that you might use.

**Commands**
**Description**

cat
Print file contents to the screen

cat filename.txt
Cat the contents of filename.txt to your screen

cd -
Change directory

cd ..
Go up a directory

cd /usr/local/apache
Go to /usr/local/apache/ directory

cd ~
Go to your home directory

cp -a /home/burst/new_design/* /home/burst/public_html/
Copies all files, retaining permissions form one directory to another.

cp
Copy a file

cp filename filename.backup
Copies filename to filename.backup

du
Shows disk usage.

du -sh
Shows a summary in human-readable form of total disk space  
used in the current directory, including subdirectories.

du -sh *
Same thing goes with (du -sh), but for each file and directory.  
This is helpful when finding large files taking up space.

file
Attempts to guess what type of file a file is by looking at its content.

file*
Prints out a list of all files/directories in a directory

find * -type d|xargs -i cp --verbose php.ini {}
Copies your php.ini file into all directories recursively.

grep
Looks for patterns in files

grep -v root /etc/passwd
Shows all lines that do not match the root

grep root /etc/passwd
Shows all matches of root in /etc/passwd

kill
Terminate a system process

kill : 9 PID EG
kill -9 431

kill PID EG
kill 10550  
Use top or ps ux to get system PIDs (Process IDs)

last
Shows who logged in and when

last -20
Shows only the last 20 logins

last -20 -a
Shows last 20 logins, with the hostname in the last field

ln
Create's "links" between files and directories

ln -s /home/username/tmp/webalizer webstats
Now you can display http://www.yourdomain.com/webstats to show your Webalizer stats online.  
You can delete the symlink (webstats), and it will not delete the original stats on the server.

ls
List files/directories in a directory, comparable to dir in windows/dos.

ls -al
Shows all files (including ones that start with a period),  
directories, and details attributes for each file.

more
Like a cat, but opens the file one screen at a time rather than all at once

more /etc/userdomains
Browse through the userdomains file.  
hit Space to go to the next page, q to quit

netstat
Shows all current network connections.

netstat -an
Shows all connections to the server, the source, and destination IPs and ports.

netstat -rn
Shows routing table for all IPs bound to the server.

pico
Friendly, easy to use file editor

pico /home/burst/public_html/index.html
Edit the index page for the user's website.

ps
ps is short for process status, which is similar to the top command.  
It's used to show currently running processes and their PID.  
A process ID is a unique number that identifies a process,  
with that, you can kill or terminate a running program on your server (see kill command).

ps aux
Shows all system processes

ps aux --forest
Shows all system processes like the above but organizes in a beneficial hierarchy

ps U username
Shows processes for a certain user

rm
Delete a file

rm filename.txt
Deletes filename.txt will more than likely ask if you really want to delete it

rm -f filename.txt
Deletes filename.txt, will not ask for confirmation before deleting.

rm -rf tmp/
Recursively deletes the directory tmp and all files in it, including subdirectories.

**Be extremely careful with using "rm" command. If used improperly, you can end up deleting important content that can never be recovered without a restore.**

tail
Like a cat, but only reads the end of the file

tail -f /var/log/messages
Watch the file continuously while it's being updated

tail /var/log/messages
See the last 20 (by default) lines of /var/log/messages

tail -200 /var/log/messages
Print the last 200 lines of the file to the screen

top
Shows live system processes in a nice table, memory information, uptime,  
and other useful info.  
This is excellent for managing your system processes,  
resources and ensure everything is working fine, and your server isn't  
bogged down.  
  
top  
Shift + M to sort by memory usage  
Shift + P to sort by CPU usage

touch
Create an empty file

touch /home/burst/public_html/404.html                                    
Create an empty file called 404.html in the directory /home/burst/public_html/

vi
Another editor, tons of features

vi /home/burst/public_html/index.html
Edit the index page for the user's website.

w
Shows who is currently logged in and where they are logged in from.

wc -l filename.txt
It tells how many lines are in filename.txt

wc
word count.

**EG:**

**PID**
**TTY**
**TIME**
**COMMAND**

10550
pts/3
0:01
/bin/csh

10574
pts/4
0:02
/bin/csh

10590
pts/4
0:09
APP

Each line represents one process, with a process being loosely defined as a running instance of a program. The column-headed PID (process ID) shows the assigned process numbers of the processes. The heading COMMAND shows the location of the executed process. 

### Putting commands together

Often you will find that you need to use different commands on the same line.  
Here are some examples.

  * The **|** character is called a pipe, and it takes a date from one program and pipes it to another.
  * **>** means create a new file, overwriting any content already there.
  * **>> **means to append data to a file, creating a new one if it does not already exist.
  * **<** send input from a file back into a command. 
    * **grep User /usr/local/apache/conf/httpd.conf | more** \- This will dump all lines that match User from the httpd.conf, then print the results to your screen one page at a time.
    * **last -a > /root/lastlogins.tmp** \- This will print all the current login history to a file called lastlogins.tmp in /root/
    * **netstat -an | grep:80 | wc -l - **Show how many active connections there are to apache (httpd runs on port 80)
    * **mysqladmin processlist | wc -l**  \- Show how many current open connections there are to MySQL
    * **mysqldump -u username -p dbname > file.sql** \- MySQL Dump
    * **mysql -u username -p database_name <file.sql** \- Importing MySQL database
    * **tail -10000 /var/log/exim_mainlog | grep domain.com | more** \- This will grab the last 10,000 lines from /var/log/exim_mainlog, find all occurrences of domain.com (the period represents 'anything,' comment it out with a so it will be interpreted literally), then send it to your screen page by page.
    * **tar -zxvf file.tar.gz**  \- UnTAR file
    * **which [perl]**  -  Finding path to [perl]

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **[888-401-4678](tel:888-401-4678)**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.

​


___

#article 