Command-line (Terminal) is a very powerful tool we have in our machine and this is over responsibility to use it smartly. Let’s get started with these commands. I am dividing this into two sections first one is a must-know and the second one is good to know.

To open the terminal, press **Ctrl+Alt+T** in Ubuntu, or press **Alt+F2**. For mac user **command+space** then type terminal in spotlight search then hit **enter**.

## Let’s start with must-know commands.

I will give you Ubuntu commands. Most all their command is used in daily basics as a software engineer. This article is for any software engineer that wants to use the terminal more efficiently.

## 1\. mkdir (create the directory)

Let’s create the folder using the command line like other commands this one is also easy to use. You just have to write **_mkdir_** and pass the folder name.

```
Example: - mkdir folderName
```

## 2\. cd (go on a path)

If you want to go on a path/folder you will use the **_cd_** command in both operating systems.

```
Example: - cd /path/where/to/want/to/go/
```

## 3\. touch (create a new file)

Creating a file is very simple using the command you have to use the **_touch_** command to create a file. You just have to pass the file name with the extension.

```
Example: - touch filename.txt
```

## **4\. vi (edit file using terminal)**

Let's edit a file using a terminal with the command **_vi._** This command is used to open a terminal editor.

```
Example: - vi filename.txtthen press i to insert to text.
```

## 5\. pwd (show correct directory path)

This command is used to check your current path. This command will give to pull path of all the directories that start with a forward slash (/).

```
Example: - pwd/Applications/MAMP/htdocs/
```

## 6\. ls (list all the items)

This command is a very used command. This command is used to list all the items. By default, this command will display the content of your current directory.

If you want to see the content of another directory you have to pass the path of the directory. For Example **_ls /var/www_** to view the content of the **_www_** directory.

![](https://miro.medium.com/max/700/1*J2ChcUc4xks05a6p5Wb2aw.png)

## 7\. cp (copy file/folder)

This command is used to copy files or folders. For example, if you want to copy a file in the same folder you have to type **_cp file.txt file1.txt._** This command will create a copy of the file.txt with the name file1.txt.

If you want to copy the folder you have to pass **_\-r_** with the **_cp_** command.

```
Example: - cp fileName1.txt fileName2.txtcp -r folder1/ folder2/
```

## 8\. mv (move or rename file/folder)

This command is used to move files or folders. For example, if you want to move a file in the same folder you have to type **_mv file.txt file1.txt._** This command will cut the file and paste it with a new name (file1.txt). This command is also used for renaming files.

Like the **_cp_** command, if you want to move the folder you have to pass **_\-r_** with the **_mv_** command.

```
Example: - mv fileName1.txt fileName2.txtmv -r folder1/ folder2/
```

## 9\. rm (delete file or folder)

Command use to delete file or folder. For instance, If you want to delete a file using this command **_rm filename.txt._** This command will delete your **_filename.txt_** file if exist in the current folder.

Like other commands, if you want to delete a folder you have to pass -r with the command also.

**Note**: Be very careful with this command. This will delete everything and there is no undo.

```
Example: - rm fileName.txtrm -r folder/
```

## 10\. grep (find some text in a file)

This command is also very useful command and very Important also. This command is used to file given text into a given file. For example, If You want to find a black keyword in the file.txt the command will be **_grip black file.txt_** This command will find all black work in file.txt. Lines that contain the searched word will be displayed fully.

```
Example: - grep black file.txt
```

## Let’s start with good to know commands

## 11\. sudo (**SuperUser Do**)

This command makes you god of the server. This command enables you to perform any task that required root permissions. You can shut down, restart or install the package on the server as well.

```
Example: - sudo suThen it will ask for the password.
```

## 12\. tail -f (use to show file last 10 lines)

This command is used to show the last 10 lines of a given file. For example, **_tail -f error.log_** will show the last 10 lines and will print upcoming lines. If you want to exit from the **_tail -f_** command you have to press **_ctrl+c._**

```
Example: - tail -f /var/log/error.log
```

You can also use the grep command with the tail command.

```
Example: - tail -f /var/log/error.log | grep "error"
```

## 13\. diff (to compare files)

The **diff** command compares the contents of two files line by line. After analyzing the files, it will output the lines that do not match.

```
Example: - diff file1.log file2.log
```

## 14\. chmod (change permissions)

This command is a very command in Linux. **_chmod_** is used to change the read, write, and execute permissions of files and directories.

If you want to change permissions of folders and files inside that folder you can pass **\-R** after **chmod** with space. **\-R** is used for recursive.

```
Example: - chmod 777 file.txt
```

## 15\. top (show top usage applications)

This command is the same as a task manager (windows)or activity manager (Mac). Command will provide you with all running applications with the CPU usage percentage. Note: For exit press **ctr+c.**

```
Example: - top
```

![](https://miro.medium.com/max/700/1*hT4fNHMiokm-JQzJHXIKXA.png)

## 16\. kill (stop any service)

This command is used to stop or terminate any running service. In this command, you have to pass the process id of the application and the process id or PID.

```
Example: - kill 151
```

## 17\. wget (get the file from the internet)

The Linux command line is very useful to download files from the internet with the help of the **_wget_** command. It will download in your current folder.

```
Example: - wget http://medium.com/files/file.zip
```

## 18\. ssh (to log in on server)

The command is used to log in to the server using the command line. You do not need an application to log in to the server. You just need the IP of the server or the hostname of the server.

```
Example: - ssh root@10.0.0.8then this command will need password to acess server.
```

## 19\. scp (to transfer/ get the file on the server)

The command is used to get or transfer files from the server or to the server. Both can be done by a single command. for example, if You want to transfer a zip file to the server you can use the below command.

```
Example: - scp ./file.zip root@10.0.0.8:/tmp/then this command will need password to transfer file to server.
```

If you want to get some files from the server you just have to use the below command.

```
Example: - scp root@10.0.0.8:/tmp/file.zip ./then this command will need password to transfer file to server.
```

## 20\. zip (create a zip or unzip)

**zip, unzip** — Use **zip** to compress files into a zip archive and **unzip** to extract files from a zip archive.

You can watch videos also on [Youtube](https://youtu.be/ewSrDZ8soHQ) in Hindi. If you need help consider following me on [**Github**](https://github.com/kewal28), or [**LinkedIn**](https://www.linkedin.com/in/kanojiakr/).

That’s all, thanks! If you liked this post, don’t forget to leave a 👏.