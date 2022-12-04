## To anyone getting started with Linux, check out these commands and make your life easier!

![](https://miro.medium.com/max/700/1*Y7550RGvIbLZDjUktNG26A.png)

Use the command cmatrix to get this cool matrix. Have fun with Linux commands!

## List (ls)

Use the `**ls**` command to display the files, along with all their properties, are in a directory.

## Change directory (cd)

It is often necessary to change directories. That’s the `cd` command's function. For instance, this example takes you from your home directory into the `Desktop` directory:

```
$ cd Desktop
```

To get back to the previous directory use:

```
$ cd ..
```

![](https://miro.medium.com/max/700/1*aB4x9tItYwCP9t-ULqBFrg.png)

## Print working directory (pwd)

The `pwd` command prints your working directory. In other words, it outputs the path of the directory you are currently working in.

![](https://miro.medium.com/max/446/1*jML1zQASXLlNtfM3dKpC6Q.png)

## Make directory (mkdir)

Making directories is easy with the `mkdir` command. The following command creates a directory called `newfolder` unless `newfolder` already exists:

```
$ mkdir newfolder
```

## Copy a file (cp)

Copy files _from-here_ _to-there_ with the `cp` command. Here's an example to copy from file1.txt to file2.txt:

```
$ cp file1.txt file2.txt
```

## Create an empty file (touch)

Easily create an empty file with the `touch` command:

```
$ touch newfile.txt
```

## Escalate privileges (sudo)

The `sudo` (or _super user do_) command comes in when you require super user permissions (root) while administering your system. When you're trying to do something and your computer alerts you that only an administrator (or root) user can do, stating Permission denied, just preface it with the command `sudo`:

```
$ touch /etc/os-release && echo "Success"touch: cannot touch '/etc/os-release': Permission denied$ sudo touch /etc/os-release && echo "Success"Success
```

## Read the manual (man)

The single most important command that you will need to get the documentation for each of the commands on your Linux system is `man` .For instance, to read more about `mkdir`:

```
$ man mkdir
```

Another similar command is `info.`

Use these commands and keep learning and exploring! Thank you for reading this post, stay tuned for my next blog posts.  
You can find me on [**Twitter**](https://twitter.com/shivikapriya)**,** [**LinkedIn**](https://linkedin.com/in/priyasrivastava730) **and** [**Github**](https://github.com/priya730)**.✨**