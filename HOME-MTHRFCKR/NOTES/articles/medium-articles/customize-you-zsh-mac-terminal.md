---
tags:: medium
created: 2022-08-05T17:16:25 (UTC -04:00)
tags: []
source: https://medium.com/@amankrr/customize-you-zsh-mac-terminal-eb47df935522
author: Aman Kumar
---

# Customize you zsh mac terminal.. Make your ZSH mac terminal colourful… | by Aman Kumar | Medium

---
![[16TR26W2huesFjW4Aye-cDw.jpeg]]

As a linux or mac user we all love to work with terminal because its very powerful tool and gives us more control. But when you will come across with mac terminal it’s pretty simple with a single colour 😐. Which sometime gets annoying because you can’t differentiate between your command and results, and makes difficult to work for long time.

So, I spent a whole day in customizing it to make it look better 😅. Here’s a short guide how you can also customize it easily step by step.

> _Its better to visit links which are provided, for detailed installation and customization._

## 1\. zsh Syntax Highlighter

This package provides syntax highlighting for the shell zsh. When you start typing it starts highlighting commands. It really helps upon getting errors, as one can easily find out whether there is a typo or not.

Copy and paste below command in your terminal.

```
brew install zsh-syntax-highlighting
```

After successful installation you will see this:

![[1WZFRlTlH--CQKuAO5JQ7Iw.png]]

after installation message

> put _“source /…/……./……../…………/…………”_ in your .zshrc file located in root directory (Hidden) save that file close your terminal and reopen boom ready to go.

**_For more visit:_** [_https://github.com/zsh-users/zsh-syntax-highlighting_](https://github.com/zsh-users/zsh-syntax-highlighting)

## **2\. lsd**

In zsh shell of mac when we type **_ls_** and hit enter it show output in single color. It’s pretty hard to see which type of files are there. **_lsd_** shows the output in different colors which helps a lot by showing different colors for different file types and folder and also makes terminal look pretty good.

Before installing **_lsd_** you have to install **Nerd fonts.** Copy and paste below command in your terminal one by one.

```
brew tap homebrew/cask-fontsbrew install --cask font-hack-nerd-font
```

After successful installation set the font of your terminal as Nerd Font then install lsd.

```
brew install lsd
```

Type lsd and you will see colorful output. If not then close your terminal and open it again now type lsd not it will work. You will probably thinking that I want to use ls instead of lsd. You can do this by :

```
alias ls='lsd'
```

Copy the above line and paste it in your .zshrc file save that and source it. You are ready to rock, type ls and you will see colorful output.

> **Note:** If you haven’t installed and set nerd font for your terminal the icons will show as question mark in output when you will type lsd or ls.

**_For more visit:_** [**_https://github.com/Peltoche/lsd_**](https://github.com/Peltoche/lsd)

## 3\. bat

What about **_cat command_** we regularly use it. As you know cat command also show output in single color no syntax highlighting for files. So, for this **_bat_** is perfect. It provide us various themes we can choose in which we want to see our file output.

```
brew install bat
```

After successful installation.

```
export BAT_THEME='gruvbox-dark'alias cat='bat --paging=never'
```

Copy the above line and paste it in your .zshrc file save that and source it. You are ready to rock, type cat and you will see colorful output.

> **Note:** If you want to see more themes type **bat — list-themes** in your terminal and you will see a list of themes for bat now copy the name of the theme which you like and replace it with **gruvbox-dark** written above within quotes(don’t remove quotes).

**_For more visit:_** [**_https://github.com/sharkdp/bat_**](https://github.com/sharkdp/bat)

## 4\. Powerlevel10k

It’s a theme for zsh. Makes prompt look good and provide great information also.

Before installing powerlevel10k install the fonts and set for your mac terminal font(from below link). Don’t worry about the fonts you installed and set for your mac before, while installing lsd. lsd will work fine even if you set these fonts but if you don’t install and set the fonts which are recommended for powerlevel10k, then your powerlevel10k will not work properly. Visit the below link and download and install the fonts:

After installing and applying these font for your mac terminal. Now install powerlevel10k.

```
brew install romkatv/powerlevel10k/powerlevel10kecho "source $(brew --prefix)/opt/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc
```

Run the above command one by one and then follow the steps shown on your terminal. After successful installation and configuration your powelevel10k will setup and ready to use. It’s better to close and reopen the terminal after successful installation and configuration.

Here’s my powerlevel10k theme:

![[12TVeF8PGko5yeAIm1Hn4sQ.png]]

powelevel10k theme

**_For more visit:_** [**_https://github.com/romkatv/powerlevel10k_**](https://github.com/romkatv/powerlevel10k)

## .zshrc

This is how my zshrc file looks like.

.zshrc file

Have fun. Play with setting and explore more 🍿🎉.

**All Links**
