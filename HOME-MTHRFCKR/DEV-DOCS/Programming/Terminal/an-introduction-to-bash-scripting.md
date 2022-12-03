Fancy yourself a computer scientist, hobbyist, or tech nerd? Then at some point, you will, or should, consider using Bash scripting in your digital workspace.

[Bash (Bourne Again Shell)](https://www.gnu.org/software/bash/manual/bash.html#What-is-Bash_003f) is an interpreter responsible for processing commands on the command line of Unix systems. It is a [free software written by Brian Fox](https://www.redhat.com/en/command-line-heroes/season-3/heroes-in-a-bash-shell) and released in 1989 as a replacement for Sh (Bourne Shell). Bash is used by developers, data scientists, system administrators, Network Engineers, and any other person heavily relying on Unix operating systems in their day-to-day. Generally speaking, Bash scripting is used to automate everyday remedial tasks a computer scientist may take on. Simply put, a shell script is no more than a series of commands that are stored in a file like a list.

You can use Bash on [Linux](https://www.webopedia.com/definitions/linux/) and MacOS machines and it is even available on Windows 10 machines through the Windows Subsystem for Linux. Bash is typically run in a text window where users type commands to have a computer execute actions. The language can also be used to read and execute commands from files, known as shell scripts. Shell scripts are a programming language in their own right, and like any other language, Bash is a tool that can be used in several ways.

If you have seen a machine with a Linux Operating system (or Unix-like environment) before, you may have also seen the terminal console. The terminal is how a user can interface with the shell interpreter using certain commands. Commands like **cd** to navigate the file directory, **ls** to list files in the current directory, and **nano** to edit files.

![Bash Scripting Tutorial](https://www.developer.com/wp-content/uploads/2021/11/Bash-Scripting-tutorial.png)

Example of Bash Terminal in Unix

Using Bash code within the terminal, it will be run by the Bash interpreter. Commands like **ls** are binary executable files located in the **/bin** directory. When the shell receives that command (when you type it in the terminal and hit enter), it executes the **ls** file and lists the files in the current directory for the user. Using the command **ls /bin** executes the binary **ls** with the path **/bin** as an option, listing the files in the **/bin** directory. Executing **ls -al** runs the **ls** command with the flags **\-a** and **\-l** as options, listing all files and directories in the current directory path with detailed information about those items.

**touch** is another such binary executable file, a command that a user could use in the terminal. This command’s output is a new file with the name the user types as an option. For example, a user could write **touch hello.txt** and the output will be a file **hello.txt**.

**Read: [How to Manage Linux Users from the Terminal.](https://www.developer.com/open-source/manage-linux-users-terminal/)**

## How to Run Multiple Bash Commands

To run multiple Bash commands and have them executed all at once, a user can save such commands in a single file to be executed with **bash**. Assuming you are working in a Unix/Unix-like environment, let’s consider what we discussed previously.

After opening up the command terminal, start by using your preferred text editor, such as _nano_ or _vi_. Write:

nano make\_a\_file.txt

Then, write out the following:

#create a file
touch hello.txt

#list files from this directory 
ls -al

Save and exit the file and run your new script using one of the following command syntaxes:

sh make\_a\_file.txt
or
./make\_a\_file.txt
or
bash make\_a\_file.txt

If there is an error executing the file, proceed to set the executable permissions for the script file you just wrote by entering:

chmod +x hello.sh

If you’ve followed this example, you have just created a file containing multiple Bash commands. The Bash interpreter will run these commands in order and ignore lines that begin with the hash symbol # as those lines are comments. Running the file results in the terminal output of a list of files which will include a **hello.txt** where there were none before.

Usually, a Bash script file is saved in the format containing the **.sh** extension, making it clear that the file is a shell script. However, when the file begins with a “she-bang” or “hashbang” we are able to execute it like a binary file.

When creating a script, we should consider that every binary shell file starts with what is colloquially known as the “she-bang” (also known as a sh-bang or hashbang). This is the start of the script header, the first line of code that indicates which shell you will be using. When making a script we have multiple options to pick from including **shell (sh)**, **C Shell**, **Z Shell**, and others. In this case, we will stick with Bash for our scripting needs. The She-bang is the set of symbols **‘#’** and **‘!’** at the start of the script. We know as students of programming that the hash symbol (#) indicates a line that is meant to be a comment. With the she-bang however, a Unix-like system’s program interpreter will parse the rest of that first line as an interpreter directive. In this case upon writing **#!/bin/bash** the hash symbol and exclamation mark serve as an indicator to the program loader instructing it to use the Bash Shell program located at **/bin/bash** directory.

## How to Create Variables in Bash

Like most other Unix shells, Bash features variables, piping, filename wildcarding, here documents, command substitution, and control flow. Bash also supports alternation (something it shares with C shell), command line completion, and signal handling and basic debugging. With features like these, it is no wonder that bash has become the default command interpreter for Unix & Unix-like systems.

Like other programming languages, we can declare variables while making scripts in Bash. However, unlike other languages, Bash does not need keywords to declare variables or to assign them data types. Bash does not have a type system, only saving variables as string values. However, Bash _could_ convert the variables to a suitable type automatically based on certain operations, such as in arithmetic operations. To write a variable and populate it with a value, write something in the format of **VARIABLE=VALUE** making sure not to include spaces. Here is an example showing how to create variables in Bash:

#!/bin/bash

#write a variable 
NAME=“William”

#use that variable
echo “Hello $NAME”

A user can also make it so that a variable is populated by user input:

#!/bin/bash

echo “Hello $1, that is a $2 name”

And in the terminal:

~$bash name.sh “William” “great”
Hello William, that is a great name

One could also use commands like **read** to use user input for variables while it is running:

#!/bin/bash

echo “What is your name?”

read name

echo “Hello $name”

And in the terminal:

~$bash name.sh
What is your name?
~$William
Hello William

## If Statements in Bash

We can also implement **if** statements for additional functionality.

#!/bin/bash

echo “Who is there?”

read name

if \[ $name \]
echo “Hello $name”
else
echo “Must’ve been my imagination”
fi

And in the terminal:

~$bash name.sh
Who is there?
~$
Must’ve been my imagination

## How to Create a Backup Management Script in Bash

Other projects to consider making include setting up a backup management script. This can be an easy project to start on and to revisit later. With this, you can make a simple script that targets one or several files and folders to compress using the tar library and place in a new backup directory of your choosing. The following script is a rudimentary backup script that creates a .Zip file of those files in need of backups and labels them according to the date it was created:

#!/bin/bash

#get the month, day, and year of the current date 
TIME\_OF\_BACKUP=\`date +%m-%d-%y\`

#create a backup file using the current date in its name
DESTINATION=/path/\[BACKUP FOLDER\]-$TIME\_OF\_BACKUP.tar.gz 

#the folder that contains the files that we want to backup
TARGET\_FOLDER=/path/\[TARGET FOLDER\]

#create the backup
tar -cpzf $DESTINATION $TARGET\_FOLDER

As a bonus, you may want to add some complexity to this project, as well as an added level of automation, by adding a scheduled execution for your backup script. To do this, you can use the crontab program and command library. If you need to install cron, make sure to update your current package library before proceeding to install cron.

sudo apt-get update
sudo apt-get install cron

Upon a successful installation, you can proceed to use the cron library to schedule the execution of your script.

crontab -e 

This opens up the **/etc/crontab** file and allows you to write commands like the following to schedule the execution of scripts:

@weekly /path/backup\_script.sh

I won’t go further into what you can do with **crontab** as it is not within the scope of this article.

With this rudimentary beginner’s guide, you will have some idea of what Bash is, what scripting is, and what scripting in Bash is like. There are a lot of things you can do with Bash and you do not need to know a lot about programming to piece together different Linux applications and tools and make something useful. Bash scripting is a fantastically useful tool and hopefully, you will have come away from this article inspired about automating your ideas.