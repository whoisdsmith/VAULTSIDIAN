---
tags:: medium
created: 2022-08-05T17:16:43 (UTC -04:00)
tags: []
source: https://medium.com/codex/quick-start-with-terminal-useful-commands-you-should-know-f8231d74b5c1
author: Carla Martins
---

# Quick start with Terminal — Useful commands you should know | by Carla Martins | CodeX | Medium

---
In Linux, command-line is the primary mean for interacting with the system, which is similar to Terminal in Mac-OS. Both Mac-OS and Linux are Unix-based systems. The Unix file system represents files in a hierarchical structure where files (or directories) are organised by directories, sub-directories and files. An application has several ways to access the files, including using a command-line. In Unix, the command prompt or terminal window is also referred to as the shell. The shell provides an interface for the user to interact with the operating system.

Unix systems shells comprise two types of commands- shell built-in commands, and shell external commands. Shell built-in commands are the basic commands given by the shell for system administration functions. They are used for system maintenance operations. Shell external commands are third-party programs that can be executed from the shell. This article will only discuss basic built-in commands you can use every day to easy your life (and impress your non-IT friends!).

## Let’s start!

The most important commands in a terminal are:

```
pwdtreecdlsmkdircatmvrm / rmdirdiffhead / tail grep
```

## pwd

This command shows the directory where the user is located. This command is important so that the user can locate himself within the tree of directories and files that make up Unix systems. In the image below, we can see in the upper part that user is in the directory pixel, that is a sub-directory of Users.

![[1H1F_YmsP4bTjOTz--5vx9Q.png]]

Image 1. Using the **pwd** command to check that user is at home directory.

In the next image, the user is in the directory unix\_command\_line, a sub-directory of Desktop.

![[1cJD_49cwxPHXi2GtGqwP0A.png]]

Image 2. Using the **pwd** command to check that user is at unix\_command\_line directory.

## tree

The **tree** command displays the folder and file structure of the current directory visually. I used the **tree** command inside my unix\_command\_line folder and the output is shown in figure 2. The **tree** command also prints the number of directories and files. We can use the **tree** command to help us navigate in the directories and find paths to files.

![[1niBHfFB4d7AkAo7kdrU_SQ.png]]

Image 3. Example of the output of **tree** command.

**cd**

The command change directory (**cd**) is used to navigate inside the directories. If you are in your home directory, and you want to go inside unix\_command\_line directory that is in your Desktop, just type: **cd /Desktop/unix\_command\_line**. You can confirm now you are inside unix\_command\_line by using pwd.

![[1U1VIPHHqbTD-jR2cziUvAg.png]]

Image 4. **cd** command to access unix\_command\_line directory.

To return one level to the parent directory, use **cd ..**, and to return to your home directory type **cd ~**.

## ls

You can use the command **ls** (list) to display files and folder names inside a directory. The charm of **ls** command is the list of options you can add. If we use the basic **ls** command inside unix\_command\_line directory, we will have all the files and directories inside unix\_command\_line directory displayed.

![[1XbjBrsShqfjMIOZd1DAX_Q.png]]

Image 5. **ls** command inside unix\_command\_line directory.

But now we can go further and try some options of the ls command. With **\-a** option, we instruct our machine to show even the hide files. You can see the difference in image 6, where it is possible to find the files “.” and “. . “.

![[1a2HUYhN-JAHtsGa1cZxHww.png]]

Image 6. **ls** command inside unix\_command\_line directory with the option **\-a**.

With the **\-R** option, it is possible to see what is inside the sub-directories of unix\_command\_line directory, as you can see in image 7.

![[1ntRIOhe_Yp3RAC3wwRbN0w.png]]

Image 7. **ls** command inside unix\_command\_line directory with the option **\-R.**

To see the size and permissions of the files and directories inside unix\_command\_line, just use the option **\-lh**.

![[1DyCLVbyi__msXycw9c6u-w.png]]

Image 8. **ls** command inside unix\_command\_line directory with the option **\-lh.**

**mkdir**

To create a new directory, the command **mkdir** (make directory) can be used in two ways. The first one, you move using **cd** to the directory where you want to create a new directory. Just use **cd Desktop/unix\_command\_line** and then **mkdir folder\_5**.

![[139IpofHQU3zmiDPVwktMkQ.png]]

Image 9. Creating a new directory using **mkdir**.

With the second option, you use the command **mkdir** specifying the path where we want to the new directory using **mkdir Desktop/unix\_command\_line/folder\_5** from home directory.

![[1OD0KQhGwO5W0A18HwX7qeA.png]]

Image 10. Creating a new directory using **mkdir** by specifying a path from home directory.

**cat**

The **cat** command stands for concatenate. It is a versatile command that can be used for more than one function. We can use **cat** to create a text file and write something on it with **cat > sample.txt ,** then write “Hello world!” and use ctrl+d to exit. We can confirm that sample.txt is in folder\_5 using **ls**.

![[1iaxjRMQbm7UT68cY1zd5DQ.png]]

Image 11. Creating a new file using **cat** command.

We can also use cat to see what is inside sample.txt by typing **cat sample.txt** .

![[1IdIvVnn3UpYmkn30PzSdlw.png]]

Image 12. Using **cat** to see what is inside sample.txt.

If we want to concatenate two files we can use cat. In the example bellow we create a new text file named sample\_2.txt using **cat > sample\_2.txt** , and write “Hello amazing world!”. To concatenate sample.txt and sample\_2.txt we just use **cat sample.txt sample\_2.txt > final\_sample.txt**. It is possible to see that final\_sample.txt is in our folder\_5 directory with **ls** and we can see its content with **cat final\_sample.txt** .

![[1L4VaWoMzpbzK6Nk0pTmGeA.png]]

Image 13. Using **cat** command to concatenate two txt files.

**mv**

The next command is called move (**mv**) and has two functions, the first one as its name says, is to move files. If we want to move final\_sample.txt from folder\_5 folder to folder\_1, we just type **mv Desktop/unix\_command\_line/folder\_5/final\_sample.txt Desktop/unix\_command\_line/folder\_1** .

![[1-fxjmq_f7e-vq0dZfWd_yg.png]]

Image 14. Moving final\_sample.txt from folder\_5 to folder\_1 using **mv** command.

The **mv** can also be used to rename files inside the same directory. If we want to change name of sample\_2.txt to sample\_3.txt we use **mv sample\_2.txt sample\_3.txt** .

![[1pVMKq8d9KVb7owpNhnW0ag.png]]

Image 15. Renaming sample\_1.txt to sample\_3.txt using **mv** command.

**rm / rmdir**

And now if we want to remove files and directories? We have **rm** and **rmdir** commands. To remove a file sample.txt just use **rm sample.text** , check if the file was removed with **ls.**

![[19yT8oI7XyleMztx37tc2Og.png]]

Image 16. Removing the file sample.txt using the command **rm**.

To remove a directory such a folder\_5 make sure the directory is empty. In this case we will need to remove sample\_3.txt before (**rm sample\_3.txt**), then we move to parent directory with **cd ..** and then use **rmdir folder\_5**. After removing folder\_5 check with **ls** again if the folder was successfully removed.

![[1GPijvG5lJKKyVkd1PUNstQ.png]]

Image 17. Removing the directory folder\_5 using **rmdir** command.

**diff**

The **diff** command stands for difference. We can use this command to check the differences between two files. For this purpose I created two files named text\_1.txt and text\_2.txt. We can take a look at their content using **cat** command.

![[1D8-Ur6Am30u4rsnC2TPg2g.png]]

Image 18. Content of text\_1.txt using **cat** command.

![[1PvUwbns1CFKO66lOIcnNaw.png]]

Image 19. Content of text\_2.txt using **cat** command.

To check for differences between text\_1.txt and text\_2.txt using diff command we just type **diff text\_1.txt text\_2.text** .

![[1XNkX1T0rbMG126AzJYZSFg.png]]

Image 20. Output of **diff** command to check differences between text\_1.txt and text\_2.txt.

**head / tail**

With **head** and **tail** commands we can see the first lines or the last lines of a file. By default, **head** and **tail** commands will return the first ten or the last ten lines of the file. However with the option **\-n** it is possible to chose the number of lines we want to see. For example, to see the first 6 lines of the file text\_1.txt we use **head -n 6 text\_1.txt** and to see the last 10 lines of the file text\_2.txt we only need **tail text\_2.txt** .

![[17QDeMIfurNgVUgIDJgseTw.png]]

Image 21. The first 6 lines of the file text\_1.txt using **head** command.

![[17YrFA9j2dp08GGTuC6PN0g.png]]

Image 22. The last 10 lines of the file text\_2.txt using **tail** command.

**grep**

The **grep** command search for patterns in files. For example, if we want to find the word “Hello” in text\_1.txt we use **grep “Hello” text\_1.txt** and the output will be the whole line where the word “Hello” appears.

![[1XvKQ7sZM88kX_a34Gb0--g.png]]

Image 23. The command **grep** returns the content of the line where the word “Hello” was found.

The **grep** command has some options. The **\-n** option shows the line number where the searched text appears.

![[1C1v90kdF5LQACFE1fq-Jdw.png]]

Image 24. With the option **\-n**, the command **grep** returns the line number where the expression is plus the content of the line.

The **\-c** option counts the number of lines where the searched text appears.

![[1hXBnjraunASmNUyduj6SBQ.png]]

Image 25. With the option **\-c**, the command **grep** returns the number of lines where the expression can be found.

In conclusion, using your terminal doesn’t need to be scary, you just need time and practice and once you start I am sure you will find it funny, interesting and powerful. Enjoy it!

**If:** you liked this article, don’t forget to follow me and thus receive all updates about new publications.

**Else If:** you want to read more, you can subscribe to Medium membership with [my referral link](https://cdanielaam.medium.com/membership). It will not cost you more, but will pay me a coffee.

**Else:** Tank you!
