---
tags:: medium
created: 2022-08-05T17:16:50 (UTC -04:00)
tags: []
source: https://medium.com/@thanhdonguyen01/18-useful-terminal-commands-for-mac-users-b59fd8c8d6aa
author: Thành Đô Nguyễn
---

# 18 useful Terminal commands for Mac users | Medium | Medium

---
![[0siKL8IGC_2Sc-mNC.jpg]]

Image source: Pixabay

Thanks to a friendly user interface, most of the time, Mac users do not have to work with Terminal on Mac like on other Unix-like operating systems. However, there are still some helpful Terminal commands that you should know.

1.  ls

_ls_ is a command used to list files and folders in a specific directory.

![[1-C7R2lm3F2oLiyQaLNG1nw.png]]

With _ls -l,_ you can see not only the list of files, but also other details, including file type, file owner, file size, …

![[1lHs_6v86ar9veszu93P2aQ.png]]

2\. cd

_cd_ is used to change the current working directory in the Terminal. It is always used to combine with other commands.

![[1aNZs3epSf9Vc0FBRsGPQ1Q.png]]

_cd ~_: change the current to home directory.

_cd -_: switch to the previous used directory.

4\. _pwd_

_pwd_ is used to show the current working directory.

![[1VlftesGxwzddWu9rH4yYEQ.png]]

5\. _mv_

_mv_ is used to change the file name or move a file to a new directory.

![[1tApAJh816OJ0fkWGHQf6MA.png]]

Move list.txt to the folder list

![[1bLDtk_eeyrm_KxmTMeN_Nw.png]]

Change the name of the file list.txt to list\_v2.txt

6\. _mkdir_

_mkdir_ is used to make a new directory.

![[1mIqwDGN48_P_X3vwLsMKLw.png]]

7\. _rmdir_

In contrast to _mkdir, rmdir_ is used to remove a directory.

8\. _grep_

_grep_ is used to search for a string in a specific file.

![[1kniiDvVXX8YFHiBlZx_miQ.png]]

9\. _rm_

_rm_ is used to remove a file

![[1yIqxz4zMIaNV-JTbvh4Gew.png]]

10\. _cp_

_cp_ is used to copy a file or folder.

![[1A0TzdmTGQWegriJQLDF62A.png]]

list\_replica.txt — The copy of list.txt

11\. _ps_

_ps_ command is used to show the running processes.

_ps_: list the running processes in the current shell

![[1L7la7ydPQV72a5A1Axa4_g.png]]

_ps -A_: view all the running processes

![[1MwK9KUU6sCAtj9-CFmxmNw.png]]

_ps -aux_: display both user and system processes, with more useful information than other similar options

![[1w-ZtFDJbuHLOPDNvvapeDA.png]]

```
USER = user owning the processPID = process ID of the process%CPU = It is the CPU time used divided by the time the process has been running.%MEM = ratio of the process’s resident set size to the physical memory on the machineVSZ = virtual memory usage of entire process (in KiB)RSS = resident set size, the non-swapped physical memory that a task has used (in KiB)STAT = multi-character process stateSTARTED = starting time or date of the processTIME = cumulative CPU timeCOMMAND = command with all its arguments
```

12\. _more_

_more_ is used to view text files.

![[1A0TzdmTGQWegriJQLDF62A.png]]

13\. _nslookup_

_nslookup_ is used to obtain the domain name or IP address.

![[1JvmgWmHVgxP8MhoOhzWy0Q.png]]

14\. _traceroute_

_traceroute_ is used to show the route of a packet, from its source to its destination.

![[1w2oFPMR6eUvkQjdnBIfVow.png]]

15\. _nano_

_nano_ is used as a text editor.

![[1GdV0JPZ-ZX5gi9-pOX9yiA.png]]

16\. _gcc_ (if it is installed with Xcode)

_gcc_ is used to compile C files. You can also you Nano (as mentioned above) to write C codes and then compile with GCC later.

![[1hNqfTZK5HtGUhxJjr4JyaQ.png]]

17\. _python2_

![[1UnKtjVwEPUwvPFj6VK8hgA.png]]

_python2_ is installed on Mac by default. You can use it to run scripts written in Python 2.

18\. _chmod_

_chmod_ is used to set permissions.

![[1UjlalO-owub4mnhTd7jQbw.png]]

Don’t forget that you can use **Ctrl + C** to terminate a running command.

Thank you for reading!
