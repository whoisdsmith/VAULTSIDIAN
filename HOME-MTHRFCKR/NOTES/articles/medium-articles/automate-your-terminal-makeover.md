---
tags:: medium
created: 2022-08-05T17:17:18 (UTC -04:00)
tags: []
source: https://towardsdatascience.com/automate-your-terminal-makeover-f3c152958d85
author: Shinichi Okada
---

# Automate Your Terminal Makeover. Is setting up a terminal the first… | by Shinichi Okada | Medium | Towards Data Science

---
## Is setting up a terminal the first thing you do with a new computer? If yes, then this is for you.

![[115TDIyjAjW2D-02n4d_r4w.gif]]

Photo by [Haseeb Jamil](https://unsplash.com/@haseebjkhan?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/universe?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText). Gif by Author.

**\[Update: 2021–12–18, font-fira-code-nerd-font added.\]**

Towards Data Science published my article, [The Ultimate Guide to Your Terminal Makeover](https://towardsdatascience.com/the-ultimate-guide-to-your-terminal-makeover-e11f9b87ac99) in April 2020. It is one of my most popular articles. It has more than 120K views since it was published and about 300 views daily.

This month I had to install the terminal on my new laptop. Following the steps in my own article, I thought “Hmm, I can automate all these installations.”

Subsequently, I created [**Ter**minal **M**akeover **A**utomated (Terma)](https://github.com/shinokada/ati). It automates installing the following packages on a new Mac:

-   [Homebrew](https://brew.sh/)
-   [iTerm2](https://iterm2.com/downloads.html)
-   [ZSH](https://www.zsh.org/)
-   [Oh-My-Zsh](https://ohmyz.sh/)
-   [Starship](https://starship.rs/)
-   [Snazzy iTerm theme](https://github.com/sindresorhus/iterm2-snazzy)
-   [Nerd fonts](https://github.com/ryanoasis/nerd-fonts)
-   iTerm2 preferences plist
-   Plugins: [autojump](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/autojump), [brew](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/brew), [git](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git), [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md), and [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions).

## Caution

I created Terma for a new Mac. If you already installed iTerm2 and plugins, I suggest saving the `~/.oh-my-zsh` directory, `~/.zshrc` file, and `~/Library/Preferences/com.googlecode.iterm2.plist`.

I recommend using [Automate Brew Installer](https://betterprogramming.pub/how-to-automate-homebrew-installs-on-your-new-mac-or-linux-51e06881c5b7) first to save your brew list and then reinstall it after the Terma installation.

I recommend using [Dotties](https://towardsdatascience.com/dotfiles-could-be-the-most-important-files-on-your-computer-are-you-backing-them-up-99f8f8d99e68) to save your `.zshrc` and other dotfiles.

Then install Terma and run `terma uninstall` a couple of times to uninstall the above packages from a terminal, not iTerm. Then run `terma` twice.

## Installing Terma

![[1qkkWAtdQAEYTZxQuak_A0w.png]]

Finding Terminal on Finder. Screenshot by Author.

Open a terminal and install the [Awesome Package Manager](https://medium.com/mkdir-awesome/a-new-simple-package-manager-for-script-languages-a1228fd0972a).

Installing the Awesome Package Manager is easy. Run the following on your terminal:

```
curl -s https://raw.githubusercontent.com/shinokada/awesome/main/install | bash -s install
```

Once you have installed the Awesome Package Manager, install Terma.

```
awesome install shinokada/terma
```

## Getting started: run terma twice!

To run terma on your terminal, do the following:

```
terma
```

You’ll be asked for your password when installing Homebrew.

The Oh-My-Zsh installation exits the script, so you need to run `terma` **again**.

```
terma
```

![[1CtbPZ1Kun_oLsuuxmejY7w.gif]]

Installing Terma. Image by Author.

## iTerm2 is ready to rock!

When you open the newly installed iTerm press Ctrl+right-click and select Open.

![[17Zwiz2ju5yEN5oZwCKo64Q.png]]

The iTerm Preferences Profile is set with the name “Terma”, Color Presets of Snazzy, and font Fira code.

![[1iLW1fRhU3auyxHfXWhGMjA.png]]

You can use brew aliases, such as `bubu`, auto-suggestions, auto jump, and all the above plugins.

![[1HF1NPKpAOZnWjikpTVeMkw.png]]

The plugins in action. Image by Author.

## Printing help

```
terma -h
```

## Uninstalling Terma

You can remove all items installed including Homebrew. I suggest using [Automated Brew Installation](https://betterprogramming.pub/how-to-automate-homebrew-installs-on-your-new-mac-or-linux-51e06881c5b7) to save your brew list first.

```
terma uninstall
```

## What I learned from writing Terma

At first, I wrote the script in Bash, then running `source $HOME/.zshrc` requires a ZSH script. I converted the script to ZSH. All I needed to change was the `read` command.

```
# Bashread -rp "Do you want to uninstall? yes/y or no/n   " PANS# ZSHread "PANS?Do you want to uninstall Y/y or N/n?   "
```

The script uses Homebrew to install packages except for Oh-My-Zsh. To avoid unnecessary error messages, the script sources appropriate `.zshrc` files. For the iTerm2 configuration file, it copies a premade `com.googlecode.iterm2.plist` file to the `~/Library/Preferences` directory.

The script uses a heredoc to show the final message. The [Figlet](https://towardsdatascience.com/the-ultimate-guide-to-your-terminal-makeover-e11f9b87ac99#0918) program can create large letters.

![[1XT5N07rYwLxpJMHi0K9OHw.png]]

The ending message was made by Figlet and heredoc. Image by Author.

## Conclusion

Since you will be installing a number of programs with Terma, it takes some time to complete. I tested `terma` on my 2015 Mac (x86\_64) and 2021 Mac (ARM 64, M1 chip), and it worked flawlessly.

If you have your favorite iTerm2 setup, replace Terma’s `com.googlecode.iterm2.plist` with your plist file in the `~/Library/Preferences/com.googlecode.iterm2.plist` directory.

Happy coding!
