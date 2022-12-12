If you want to know the list of available _shells_ on your macOS (Catalina, Mojave, Big Sur) you can try the command **cat /etc/shells**, this will print list of all shells that are available,

![Terminal command to get available shells in macOS](https://code2care.org/howto/command-to-get-list-of-available-shells-in-macos-terminal/images/Terminal%20command%20to%20get%20available%20shells%20in%20macOS.png "Terminal command to get available shells in macOS")

Terminal command to get available shells in macOS

```
mac:~ code2care$ cat /etc/shells
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

/bin/bash
/bin/csh
/bin/dash
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
```

✏️ Z Shell (Zsh) is the default. shell shipped since macOS Catalina and BigSur

### How to switch between shells in macOS?

Simply type the shell name on the prompt.

```
code2care@mac ~ % bash

The default interactive shell is now zsh.
To update your account to use zsh, please run `chsh -s /bin/zsh`.
For more details, please visit https://support.apple.com/kb/HT208050.

bash-3.2$ csh

[mac:~] code2care% dash

$ ksh

$ sh

sh-3.2$ tcsh

[mac:~] code2care% zsh

code2care@mac ~ % 
```