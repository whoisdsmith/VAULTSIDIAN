---
tags:: medium
created: 2022-08-05T17:16:57 (UTC -04:00)
tags: []
source: https://medium.com/@alekseyvy/crash-course-terminal-commands-for-total-beginners-7ba087ea84db
author: Aleksey Vasiliev
---

# Crash Course: Terminal commands for total beginners. | by Aleksey Vasiliev | Medium

---
The most needed Unix-based terminal commands for beginner web developers.

**ls** command will list all files and directories inside the folder that you are currently in.

![[1Eer52GH1TS9LgqJc2bNdUQ.png]]

To navigate in the terminal we use the **cd** command, to move up we provide folder name or path where we want to change our current directory, for example:

```
cd folder_name
```

will move us into folder\_name directory,

```
cd ..
```

will move us into the parent directory of our current directory.

We can create files by using the

```
touch filename.ext 
```

command, which creates files in your current directory, we provide filename and extension for example:

```
touch test.txt
```

![[1lIHBnaif8_z5oqgrgbRvkw.jpeg]]

Same as we create files with the **touch** command, we could create folders. For that, we have

```
mkdir folder_name 
```

the command that creates a folder with the name we provide, for example:

```
mkdir TEST
```

![[1IxJaCv68menR9AxjFgmnXA.jpeg]]

As we create files and folders we need some way to delete them and that where

```
rm some_name 
```

comes in handy by providing a filename or folder name we can delete it, for example,

```
rm test.txt
```

will delete the test.txt file

![[16ljwv-J-mRbgcqc5TBxKUA.jpeg]]

to delete the folder we need to specify flags **\-rf** (**r** for recursive, **f** for force) and provide the name of a folder, for example

```
rm -rf TEST
```

will delete the TEST folder with all content that inside of that folder.

![[1A-02FdQXgfCxinByPFpGIw.jpeg]]

**cp** command, copy file or folder into a specified destination, for example:

```
cp test.txt src/
```

will copy **test.txt** into the **src** folder.

![[18KEfJNhAwru-wdJRzX7EIw.jpeg]]

**mv** command can be used in two ways, we can move files or directories with a command

```
mv file_name folder_name 
```

this will move the file to the specified folder, for example:

```
mv test.txt src
```

![[1KLRsMRQsJjU5k5XI6DOGog.jpeg]]

or we can rename a file or folder, by specifying the **initial file** and a **new name** for the file, for example:

```
mv test.txt more_test.txt
```

![[17DUU-Hyit4TjOOObHioqPQ.jpeg]]

The **clear** command will do exactly what it says, it will clear our terminal.

before **clear**:

![[1lJwtl42R6OYo7WGvmDJhAQ.png]]

after **clear**

![[1G6PjLdGUNl3c6yVZRgqEyA.png]]

That’s it, for more in-depth you can learn flags that each command uses, but for beginners, this will be enough. Thanks, and good luck with your journey.
