---
tags:: medium
created: 2022-08-05T17:15:27 (UTC -04:00)
tags: []
source: https://xhinker.medium.com/setup-my-ultimate-shell-zsh-9be8c95b89eb
author: Andrew Zhu
---

# Setup My Ultimate Shell — Zsh. Bash is good, but Zsh is even better… | by Andrew Zhu | Medium

---
![[1SE9AweannGMdXJDcrI25yg.png]]

Zsh with themes and plugins, by Andrew Zhu

Bash is good, but Zsh is even better. Zsh won’t boost your productivity 10x times, but you may **feel** like that. And the themes for Zsh can make the command terminal a beautiful place to stay.

> Once started using ZSH, I can’t go back to Bash anymore.

Here are my detailed setup and walkarounds, hope it is also helpful to you. This article will cover **macOS**, **Linux(Ubuntu)**, **VSCode**, and some notes for **Windows 10** **Terminal**.

## Install Zsh

For macOS, Zsh should be there already. If you are using another shell and want to shift to Zsh, use this command:

```
chsh -s /bin/zsh
```

For Ubuntu, you will need to install one.

```
sudo apt install zsh
```

Now, all Zsh configuration is in file `~/.zshrc` .Make a change in this file and save it.Run `source ~/.zshrc` will enable any new changes.

For example, you can add a command alias for `ll`. Add the following line in file .zshrc. will make `ll` function as `ls -all`.(programmers are lazy)

```
alias ll='ls -all'
```

Zsh has been there for a very long time, it only becomes well known and popular until some cool guy created [Oh My Zsh](https://ohmyz.sh/). Next, let me talk about Oh My Zsh.

## Oh My Zsh

The most powerful part of oh-my-zsh is its themes and plugins management system. Oh-my-zsh makes adding a new theme and plugin like a breeze.

Install it in macOS and Ubuntu using the same script:

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

In macOS, you may see some permission issues to 2 directories. `/usr/local/share/zsh` and `/usr/local/share/zsh/site-functions` . Run the following script to solve the issue.

```
chmod 755 /usr/local/share/zsh chmod 755 /usr/local/share/zsh/site-functions
```

The themes are in the below directory. New themes will be added here.

```
~/.oh-my-zsh/themes
```

The plugins are in the directory, New plugins will be added here.

```
~/.oh-my-zsh/plugins
```

## My Theme Choice — powerlevel10k

Before installing the theme, you’d better install a new font family — **MesloLGS NF**.

It is very easy for **Ubuntu**, just one line command.

```
sudo apt-get install fonts-powerline
```

For macOS (default terminal), you will need to manually download and double click the file to install:

-   [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
-   [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
-   [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
-   [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

Now let’s [Install](https://github.com/romkatv/powerlevel10k#oh-my-zsh) powerlevel10k

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

Next, open the zsh config file `.zshrc` , comment out the original theme, and add p10k theme.

```
# ZSH_THEME="robbyrussell"ZSH_THEME="powerlevel10k/powerlevel10k"
```

Save the file and run `source ~/.zshrc` to enable the new settings. The first-time run will pop up a configuration wizard to help you set up everything by answering some questions. After this, if you want to make some changes, run this command to rerun the configuration guide.

```
p10k configure
```

Done, now you shall see a beautiful terminal in front of you.

## Two powerful plugins

I mean **zsh-autosuggestions** and **zsh-syntax-higlighting** . You know what these two do from its name.

Download **zsh-autosuggestions**

```
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

Download **zsh-syntax-higlighting**

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

Edit `~/.zshrc` file, find `plugins=(git)` and replace `plugins=(git)` with

```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

Save file and then run `source ~/.zshrc` to enable it.

Now, your terminal is capable of suggesting and commannd highlighting.

![[1FRPQ3MskK5I_4iGrXIaZSQ.png]]

p10k theme with command highlighting and suggestion

## Some tune for VSCode

You are happy and can’t wait to use VSCode’s SSH remote to connect your code in Ubuntu, BAM, you see this:

![[1Hr-1_fdFaP5VBjmKphLuHQ.png]]

Not very good. Don’t worry, the solution is very simple. open the VSCode’s `settings.json` file and change the terminal default font to **MesloLGS NF** like this:

```
"terminal.integrated.fontFamily": "MesloLGS NF",
```

And you should be fine now.

![[1UAxwgi5X6uyLzMp1YvReAQ.png]]

## Some tune for Windows 10

You are happy and can’t wait to use the fancy Windows Terminal to ssh to your code in Ubuntu, BAM, you see this:

![[18QV-u7tJvfjk114F_y9G6w.png]]

Not good, the root cause is the same in VSCode, we need the **MesloLGS NF** font family. The most convenient way is manually downloading the font files and installing them one by one.

-   [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
-   [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
-   [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
-   [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

Double click the files to install. Then, back to Windows Terminal Settings, change the font family to **MesloLGS NF .**

![[1gltntxFn39luRHU-UJNV7w.png]]

Now, your terminal should be fine.

![[10vuYvmKuUl_MCUhUw0rx6g.png]]

## Appendix

Two additional solutions to solve the font issues.

1.  For macOS, if you are using ITerm2. The font files will be installed in the configuration stage, pretty easy.
2.  You can also manually download 4 font files and double click to install them, just like in Windows 10.

## Reference Links

1.  [https://ohmyz.sh/](https://ohmyz.sh/)
2.  [https://github.com/romkatv/powerlevel10k](https://github.com/romkatv/powerlevel10k)
3.  [https://medium.com/@satriajanaka09/setup-zsh-oh-my-zsh-powerlevel10k-on-ubuntu-20-04-c4a4052508fd](https://medium.com/@satriajanaka09/setup-zsh-oh-my-zsh-powerlevel10k-on-ubuntu-20-04-c4a4052508fd)

If you have any questions, leave a comment and I will do my best to answer, If you spot an error or mistake, don’t hesitate to mark them out. Your reading and support is the force that drives me to keep writing more. Thank You.
