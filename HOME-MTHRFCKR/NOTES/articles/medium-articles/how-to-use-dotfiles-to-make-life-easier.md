---
tags:: medium
created: 2022-08-05T17:17:59 (UTC -04:00)
tags: []
source: https://captainnobody1.medium.com/setting-up-my-macos-dev-environment-the-right-way-how-to-use-dotfiles-to-make-life-easier-ad237a653764
author: Miriah Peterson
---

# Setting up my macOS Dev environment the right way: How to use DOTfiles to make life easier | by Miriah Peterson | Medium

---
Since I first started writing software in high school, I have had many software development computers and many software development environments. They were almost always someone else’s idea. I have used a variety of editors ([NetBeans](https://netbeans.apache.org//), [Visual Studio](https://visualstudio.microsoft.com/), [Notepad++](https://notepad-plus-plus.org/downloads/), [Xcode](https://developer.apple.com/xcode/), [VSCode](https://code.visualstudio.com/), etc), terminals ([PowerShell,](https://docs.microsoft.com/en-us/powershell/) [Bash](https://www.gnu.org/software/bash/), [zsh](https://zsh.sourceforge.io/)), and operating systems (W[indows](https://www.microsoft.com/en-us/windows), [Windows Bootcamp](https://support.apple.com/guide/bootcamp-assistant/install-windows-newer-mac-boot-camp-bcmp173b3bf2/mac), [Arch Linux,](https://archlinux.org/) [macOS](https://www.apple.com/macos/monterey/)). When I purchased my M1 MacBook Pro in late 2021, I decided to start fresh and quit using someone else’s developer environment idea. The following are the steps I took in my setup.

## Terminal Setup

macOS comes with a built-in [Bash terminal](https://apple.stackexchange.com/questions/25143/what-is-the-difference-between-iterm2-and-terminal), but I prefer to download and use [iTerm2.](https://iterm2.com/) This is a pretty common choice among macOS users due to its expanded feature set like profiles, stats, plugins, and customizable color schemes (I like the slightly transparent style).

To accompany iTerm2, I installed [Oh-my-zsh](https://ohmyz.sh/). All Unix terminals use Bash commands by default. Zsh is just an overlay onto Bash, just like iTerm2 for the terminal. It has themes you can customize, plugins that add functionality, and life-saving features like _TAB complete_ (pressing the tab button to complete a command-line interface (CLI) command.)– a great feature if you struggle with spelling like me.

![[0kf3AN6TgTyAhO5Qj.png]]

[https://github.com/Soypete/dotfiles/blob/f90c2cf0be843e3c20b677814a4f7a39676f741b/zsh/zshrc#L62](https://github.com/Soypete/dotfiles/blob/f90c2cf0be843e3c20b677814a4f7a39676f741b/zsh/zshrc#L62)

No terminal setup is complete without a set of quality configuration files. These files (called DOTfiles) provide the exact setup of your custom environment every time you sit down to code. Common DOTfiles (notice the proceeding “DOT”) are _.bashrc_ and _.zshrc_. I typically do not change the _.bashrc_, and I usually only make a few changes to the _.zshrc_. Here you can see that these changes added only two plugins for Git and VSCode. I additionally added the command to \`_source ~/.zsh\_profile_\`.

The _.zsh\_profile_ file is not necessary. If you choose, all the contents that I put in my ._zsh\_profile_ can just be added to the _.bashrc_ or the _.zshrc_, but I like having it in a file to keep it a little more organized. The _source_ command has this file initialized at setup.

![[0N5zghZXAFpVSu1zj.png]]

[https://github.com/Soypete/dotfiles/blob/main/zsh/zsh\_profile](https://github.com/Soypete/dotfiles/blob/main/zsh/zsh_profile)

In my _.zsh\_profle_ I have common variables that I want to be set in every open terminal like the _$GOPATH_ and command aliases because I want to be able to quickly call these commands as shorthand for various other commands.

Now that I have configured my terminal to my liking I need to make them transferable to other developer machines. I have been trying to figure out for a while the best way to do this, but I usually end up copy-pasting them into a personal message channel or using an old setup that I sent myself in the past. I have set up more than five developer computers in the last five years, and each one was completely different. I was tired of trial and error trying to get things right. I wanted to make the perfect setup and then easily duplicate it. The answer to my problem was it and symlinks.  
All of my DOTfiles are stored on GitHub [here](https://github.com/Soypete/dotfiles). I have a replication of this repository in my home directory _~/dotfiles_. When my terminal starts up I need it to look at the files in this directory. I did this with a simple Unix [symlink.](https://kb.iu.edu/d/abbe)

```
ln -s dotfiles/bash/bashrc .bashrc.
```

This means that every time the terminal tries to look up _~/.bashrc_ it looks at _~/dotfiles/bash/bashrc instead._

## The text editor

When I am streaming on [twitch](https://www.twitch.tv/soypete01) I get asked all the time in chat what is the best way to get started with Vim. Yes, using Vim is a symbol of awesome, ninja-like developer mastery, but so is using a keyboard without letters on it or writing Bash scripts without Google. The only reason someone should use Vim is that they want to increase speed and productivity while decreasing the need for a mouse. I started by using the [vim bindings](https://code.visualstudio.com/docs/getstarted/keybindings) in VSCode, but when there were issues with some of my favorite plugins I made the full switch to vim. (I have tried going back to VSCode due to its popularity among co-workers, but there is an exponential decrease in my productivity).

![[0sBhU1uX0n5oTuwi8.gif]]

[https://www.reddit.com/r/vim/comments/ae8tnp/i\_know\_vim\_fu/](https://www.reddit.com/r/vim/comments/ae8tnp/i_know_vim_fu/)

Vim, like VSCode, is a very simple text editor at its core, but the power comes from community-supported plug-ins. It is really simple to install on macOS using [Homebrew](https://brew.sh/). There are also a variety of projects built off of the Unix default VI editors including [Vim](https://www.vim.org/), [MacVim](https://github.com/macvim-dev/macvim), and [NeoVim](https://neovim.io/). I have used all of them at one point or another; I liked the MacVim UI at the mouse support for when you need to copy something into the browser, but with the launch of [Github’s copilot program](https://github.com/github/copilot.vim), and it being compatible with only VSCode, Jetbrains products, and Neovim, I have switched to Neovim.

Like your terminal, vim uses DOTfiles to define and load your editor’s configuration. The _.vimrc_ file is the default configuration file when you configure your vim setup. My _.vimrc_ has 3 sections: the vi configurations, the plugin definitions, and the plugin configurations. Here is [the Git copy of my _.vimrc_.](https://github.com/Soypete/dotfiles/blob/main/vim/vimrc)

## The Go Developer Environment

I am primarily a [Go](https://go.dev/) engineer. For work, I build out data pipelines using Go, and for personal projects, I still use Go because that is the main material for my talks and presentations. This means I need to have a good Go developer environment. There are 2 Vim plug-ins that I need to be successful: [vim-go](https://github.com/fatih/vim-go) and [gotests-vim](https://github.com/buoto/gotests-vim). Vim-go integrates commands from the Go binary tool like Go build and Go test with [linters](https://golangci-lint.run/), formatting, importing, code generations, and testing. Go tests generate Go table tests for functions.

![[0AH6-b4KS-1TULWXL.png]]

Gopher designed by [https://github.com/egonelbre/gophers](https://github.com/egonelbre/gophers)

All of my configurations are available for [reference on GitHub](https://github.com/Soypete/dotfiles). It was really fun to set up my M1 MacBook Pro. To check out the setup in action, come hang out with me on [twitch](https://www.twitch.tv/soypete01) every Friday from 2 pm MST to 5 pm MST.
