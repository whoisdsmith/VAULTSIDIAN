# terminal-commands924-revision-v1-terminal-commands

Command-line (Terminal) is a very powerful tool we have in our machine and this is over responsibility to use it smartly. Let’s get started with these commands. I am dividing this into two sections first one is a must-know and the second one is good to know.

To open the terminal, press **Ctrl+Alt+T** in Ubuntu, or press **Alt+F2**. For mac user **command+space** then type terminal in spotlight search then hit **enter**.

## Let’s Start with Must-know Commands

I will give you Ubuntu commands. Most all their command is used in daily basics as a software engineer. This article is for any software engineer that wants to use the terminal more efficiently.

## 1. Mkdir (create the directory)

Let’s create the folder using the command line like other commands this one is also easy to use. You just have to write ***mkdir*** and pass the folder name.

```
Example: - mkdir folderName

```

## 2. Cd (go on a path)

If you want to go on a path/folder you will use the ***cd*** command in both operating systems.

```
Example: - cd /path/where/to/want/to/go/

```

## 3. Touch (create a New file)

Creating a file is very simple using the command you have to use the ***touch*** command to create a file. You just have to pass the file name with the extension.

```
Example: - touch filename.txt

```

## **4. Vi (edit File Using terminal)**

Let's edit a file using a terminal with the command ***vi.*** This command is used to open a terminal editor.

```
Example: - vi filename.txtthen press i to insert to text.

```

## 5. Pwd (show Correct Directory path)

This command is used to check your current path. This command will give to pull path of all the directories that start with a forward slash (/).

```
Example: - pwd/Applications/MAMP/htdocs/

```

## 6. Ls (list All the items)

This command is a very used command. This command is used to list all the items. By default, this command will display the content of your current directory.

If you want to see the content of another directory you have to pass the path of the directory. For Example ***ls /var/www*** to view the content of the ***www*** directory.

![](https://miro.medium.com/max/700/1*J2ChcUc4xks05a6p5Wb2aw.png)

## 7. Cp (copy file/folder)

This command is used to copy files or folders. For example, if you want to copy a file in the same folder you have to type ***cp file.txt file1.txt.*** This command will create a copy of the file.txt with the name file1.txt.

If you want to copy the folder you have to pass ***-r*** with the ***cp*** command.

```
Example: - cp fileName1.txt fileName2.txtcp -r folder1/ folder2/

```

## 8. Mv (move or Rename file/folder)

This command is used to move files or folders. For example, if you want to move a file in the same folder you have to type ***mv file.txt file1.txt.*** This command will cut the file and paste it with a new name (file1.txt). This command is also used for renaming files.

Like the ***cp*** command, if you want to move the folder you have to pass ***-r*** with the ***mv*** command.

```
Example: - mv fileName1.txt fileName2.txtmv -r folder1/ folder2/

```

## 9. Rm (delete File or folder)

Command use to delete file or folder. For instance, If you want to delete a file using this command ***rm filename.txt.*** This command will delete your ***filename.txt*** file if exist in the current folder.

Like other commands, if you want to delete a folder you have to pass -r with the command also.

**Note**: Be very careful with this command. This will delete everything and there is no undo.

```
Example: - rm fileName.txtrm -r folder/

```

## 10. Grep (find Some Text in a file)

This command is also very useful command and very Important also. This command is used to file given text into a given file. For example, If You want to find a black keyword in the file.txt the command will be ***grip black file.txt*** This command will find all black work in file.txt. Lines that contain the searched word will be displayed fully.

```
Example: - grep black file.txt

```

## Let’s Start with Good to Know Commands

## 11. Sudo (**SuperUser Do**)

This command makes you god of the server. This command enables you to perform any task that required root permissions. You can shut down, restart or install the package on the server as well.

```
Example: - sudo suThen it will ask for the password.

```

## 12. Tail -f (use to Show File Last 10 lines)

This command is used to show the last 10 lines of a given file. For example, ***tail -f error.log*** will show the last 10 lines and will print upcoming lines. If you want to exit from the ***tail -f*** command you have to press ***ctrl+c.***

```
Example: - tail -f /var/log/error.log

```

You can also use the grep command with the tail command.

```
Example: - tail -f /var/log/error.log | grep "error"

```

## 13. Diff (to Compare files)

The **diff** command compares the contents of two files line by line. After analyzing the files, it will output the lines that do not match.

```
Example: - diff file1.log file2.log

```

## 14. Chmod (change permissions)

This command is a very command in Linux. ***chmod*** is used to change the read, write, and execute permissions of files and directories.

If you want to change permissions of folders and files inside that folder you can pass **-R** after **chmod** with space. **-R** is used for recursive.

```
Example: - chmod 777 file.txt

```

## 15. Top (show top Usage applications)

This command is the same as a task manager (windows)or activity manager (Mac). Command will provide you with all running applications with the CPU usage percentage. Note: For exit press **ctr+c.**

```
Example: - top

```

![](https://miro.medium.com/max/700/1*hT4fNHMiokm-JQzJHXIKXA.png)

## 16. Kill (stop Any service)

This command is used to stop or terminate any running service. In this command, you have to pass the process id of the application and the process id or PID.

```
Example: - kill 151

```

## 17. Wget (get the File from the internet)

The Linux command line is very useful to download files from the internet with the help of the ***wget*** command. It will download in your current folder.

```
Example: - wget http://medium.com/files/file.zip

```

## 18. Ssh (to Log in on server)

The command is used to log in to the server using the command line. You do not need an application to log in to the server. You just need the IP of the server or the hostname of the server.

```
Example: - ssh root@10.0.0.8then this command will need password to acess server.

```

## 19. Scp (to transfer/ Get the File on the server)

The command is used to get or transfer files from the server or to the server. Both can be done by a single command. for example, if You want to transfer a zip file to the server you can use the below command.

```
Example: - scp ./file.zip root@10.0.0.8:/tmp/then this command will need password to transfer file to server.

```

If you want to get some files from the server you just have to use the below command.

```
Example: - scp root@10.0.0.8:/tmp/file.zip ./then this command will need password to transfer file to server.

```

## 20. Zip (create a Zip or unzip)

**zip, unzip** — Use **zip** to compress files into a zip archive and **unzip** to extract files from a zip archive.

You can watch videos also on [Youtube](https://youtu.be/ewSrDZ8soHQ) in Hindi. If you need help consider following me on [**Github**](https://github.com/kewal28), or [**LinkedIn**](https://www.linkedin.com/in/kanojiakr/).

That’s all, thanks! If you liked this post, don’t forget to leave a 👏.
