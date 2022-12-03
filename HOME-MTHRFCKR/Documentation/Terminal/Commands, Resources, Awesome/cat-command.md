# Cat Command in Linux {15 Commands with Examples} | phoenixNAP KB

> ## Excerpt
> Check out our 15 basic cat commands with examples. Create files, add content and merge multiple files with the powerful cat command!

---
Introduction

If you have worked in Linux, you surely have seen a code snippet that uses the **`cat`** command. Cat is short for concatenate. This command displays the contents of one or more files without having to open the file for editing.

**In this article, learn how to use the `cat` command in Linux.**

![cat command in Linux with examples](https://phoenixnap.com/kb/wp-content/uploads/2021/04/how-to-use-the-cat-command-in-linux.png)

Prerequisites

-   A system running Linux
-   Access to a terminal window / command line

## cat Command Syntax

To use the **`cat`** command, follow the format:

```
cat [options] filename(s)
```

**`[options]`** – This lets you issue additional instructions to the **`cat`** command. For example, to display the contents of a file with each line numbered, use the **`–n`** option:

```
cat –n filename
```

**`filename(s)`** – Specify the name of the file (or files) that you want to display. If you use more than one filename, each file will be displayed.

## Linux Cat Command Examples

This article includes **15 `cat` commands** and examples of how to use them. To try out the commands, create a couple of sample files, and test the cat commands listed below.

### 1\. Create a New File

You can create new files and add content to them using the **`cat`** command.

Create **test1.txt** and **test2.txt**, which you can use as sample files to test out the other commands.

1\. Open a terminal window and create the first file:

```
cat >test1.txt
```

2\. The cursor moves to a new line where you can add the wanted text. Type a simple sentence such as:

```
This is test file #1.
```

3\. To exit the prompt and write the changes to the file, hold the **Ctrl** key and press **d**.

![Create a new file using the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/create-a-file-using-cat-command.png)

4\. Repeat the process to create **test2.txt**. Run:

```
cat >test2.txt
```

5\. Type:

```
This is test file #2.
```

6\. Press **Ctrl+d**.

![Creating a sample file with the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/create-a-file-with-cat-command.png)

### 2\. Display Contents of a Single File

To display the contents of test1.txt using the **`cat`** command run:

```
cat test1.txt
```

The output displays the content as in the image below.

![Display the content of a file using the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/use-cat-command-to-display-the-contents-of-a-file.png)

### 3\. Display Contents of Multiple Files

To display the contents of both files, run the command:

```
cat test1.txt test2.txt
```

![Use the cat command to show content of multiple files.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/use-cat-command-to-show-content-of-multiple-files.png)

### 4\. Redirect Contents of a Single File

Instead of displaying the contents of a file on the screen, **`cat`** can put them in a file.

```
cat test1.txt > test3.txt
```

If the destination filename doesn’t exist, it will be created. If you run **`cat`** on **test3.txt**, you should see the contents from **test1.txt**:

```
cat test3.txt
```

The output displays:

![Redirect file contents using the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/redirect-file-contents-using-the-cat-command.png)

If a file is exported that already exists, this will **overwrite the contents of the file**:

```
cat test2.txt > test3.txt
```

```
cat test3.txt
```

The test3.txt file now has the following content:

![Overwrite the content of an existing file using the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/overwrite-the-content-of-existing-file-using-cat.png)

### 5\. Redirect Contents of Multiple Files

You can redirect the contents of multiple file into one single file:

```
cat test1.txt test2.txt > test3.txt
```

Display the content of **test3.txt** with:

```
cat test3.txt
```

The output shows the contents of both files, as in the image below.

![Redirect content of multiple files using the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/redirect-content-of-multiple-files-with-the-cat-command.png)

### 6\. Display the Contents in Reverse Order

The **`cat`** command can display the content of a file in reverse order (by lines). To do this, use **`tac`** (cat in reverse):

```
tac test3.txt
```

![Display contents of file in reverse order.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/display-content-in-reverse-order-using-cat-command.png)

### 7\. Append File Contents to Another File

The **`cat`** command can add the contents of a file to the end of another file. Instead of using a single **`>`** sign, use a double **`>>`** sign:

```
cat test1.txt >> test3.txt
```

Open the **test3** file by running:

```
cat test3.txt
```

The content of **test3** followed by **test1** should display.

![Append file content content to another file.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/append-file-content-to-another-file.png)

### 8\. Append Text to Existing File

You can use a similar command to append text to an existing file:

```
cat >> test1.txt
```

Add a new line to the file:

```
This is the second line in test file #1.
```

Hold **Ctrl** and hit **d**.

Check the content of the **test1.txt** file:

```
cat test1.txt
```

![Append text to existing file using the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/append-text-to-existing-file-using-the-cat-command.png)

### 9\. Combine Operations

The functions of the **`cat`** command can be combined. For example, to combine the output of two files, and store the result in a new file:

```
cat test1.txt test2.txt > test4.txt
```

```
cat test4.txt
```

![Combining cat operations into one command](https://phoenixnap.com/kb/wp-content/uploads/2021/04/combining-cat-commands.png)

Alternately, you can append multiple files to the end of an existing file:

```
cat test2.txt test1.txt >> test4.txt
```

```
cat test4.txt
```

![Append multiple files to an existing file using the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/append-multiple-files-to-an-existing-file.png)

Note that the order specified is the order the files in which they are added to the destination file.

### 10\. More and Less Options (Manage Large Files)

If you use **`cat`** on a very large file, you’ll end up with a huge string of data that’s hard to read. You can break it into pages using **`| more`**:

```
cat test4.txt | more
```

This displays a single page of the file. When you press a key, it will scroll to the next page.

If you’d like the ability to scroll forward and backward through the display, use **`| less`**.

```
cat test4.txt | less
```

### 11\. Show Line Numbering

You may find it useful to have line numbers in the output, especially for large files. To enable line numbering, add the **`-n`** option to the **`cat`** command:

```
cat –n test1.txt
```

The output should appear as in the image below:

![Show line numbering with cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/show-line-numbering-with-cat-command.png)

### 12\. Show the End of Line

You can instruct cat to highlight the end of each line and spaces between lines with **$**.

To do so, use the command:

```
cat -e test1.txt
```

Since the sample file **test1.txt** has only one line, the output shows one **$** at the end of it.

![Show highlight at the end of line with the cat command.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/show-highlight-at-the-end-of-line-with-cat.png)

### 13\. Show TAB Separated Lines

The **`cat`** command has the option of displaying the file content along with the tab space within the text.

To show tab separated lines for a sample run:

```
cat -t test4.txt
```

The tab space within the text is represented by **^I.**

### 14\. Remove Blank Lines

To omit blank lines from the output of cat with the **`–s`** option:

```
cat -t test4.txt
```

### 15\. List All CAT Commands

If you have trouble remembering the options, use the **`--help`** command:

```
cat ––help
```

![List all cat commands.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/list-all-cat-commands.png)

Conclusion

You should now have a good understanding of how to use the **`cat`** command in Linux.

Want to master more Linux commands? Check out our [Linux Commands Cheat Sheet](https://phoenixnap.com/kb/linux-commands-cheat-sheet).
