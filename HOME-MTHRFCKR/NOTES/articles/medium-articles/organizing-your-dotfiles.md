---
tags:: medium
created: 2022-08-05T17:18:53 (UTC -04:00)
tags: []
source: https://htoopyaelwin.medium.com/organizing-your-dotfiles-e059090a4bf5
author: Htoo Pyae Lwin
---

# Organizing your dotfiles. A better way to manage your… | by Htoo Pyae Lwin | Medium

---
![[13WXlE7oiiNbQVHULmFuXXQ.png]]

.dotfiles

## What is a dot file?

A dot file is a hidden configuration file in the Unix world. They are named with a dot at the start (for example `.bashrc`), hence the name dotfile. Usually, they are important files that we don’t want to lose and are properly kept in place. Since they are configurations, we may also want to reuse them in different machines.

## Why do we need to organize dotfiles?

We, as programmers, usually have somewhat our own personal taste in setting up the development environment, whether it’s aesthetically or for productivity. These setups are usually configured in the form of dotfiles. So, if we were to switch from one machine to another, we may have to set up these configurations for all the software we use from start again. It’d be much better if we can have all our configurations in one place that can be used in different machines.

## How to organize?

What better way to organize files than version control? Of course, we’re gonna use Git to manage dotfiles. That way, we can experiment, revert and review all the changes we made and also upload them to the repository which can then be shared.

There are a couple of different ways to manage your dotfiles. You may even want to refer to the [unofficial guide to dotfiles in GitHub](https://dotfiles.github.io/) where many of the approaches and tools are documented very well. But here what I’m about to show, in my opinion, is the simplest way to manage our dotfiles.

Step 1:

First of all, we need to decide which dotfiles are gonna be managed. For me, usually, these are my `.vimrc`, `.zshrc`, `.tmux.conf`, and global `.gitconfig`.

Step 2:

We’re gonna move these dotfiles to a new folder named `~/.dotfiles` and keep them separated on their own folders.

```
mkdir ~/.dotfiles/{vim,zsh,tmux,gitconfig}mv ~/.vimrc ~/.dotfiles/vimmv ~/.zshrc ~/.dotfiles/zshmv ~/.tmux.conf ~/.dotfiles/tmuxmv ~/.gitconfig ~/.dotfiles/gitconfig
```

Then, we’re gonna initialize git in this new folder.

```
git init
```

At this point, our software (e.g vim) will be broken out of configuration since the configuration files have been moved. So, we need to tell the system the new path of our dotfiles and this can be done by symlinks in Unix systems.

For that, we’re gonna use [Stow](https://www.gnu.org/software/stow/) which is a _symlink farm manager_ that can make the system believe our dotfiles are placed in the same home directory.

```
brew install stow
```

Using Stow is easy.

```
stow folder -t target_path
```

So we can make a symlink like this:

```
cd ~/.dotfiles && stow vim -t ~
```

and this will make a symlink under the home directory, so the vim can then load the configuration.

We can delete the Stow by

```
stow -D vim
```

## Automating

Since we don’t want to manually do this for all of our dotfiles, we will write a simple shell script inside `~/.dotfiles`to automatically run this command for all the dotfiles we have.

We will also have another script to clean up the Stow we made

Now it’s all set, we can just make the `install` executable and run it.

```
cd ~/.dotfiles && sudo chmod +x install && ./install
```

So if we go to our home directory now, we will see like below:

![[1FQxegPi5STrDcMxEJvZtLQ.png]]

## Version Control

Since our dotfiles are now within the .dotfiles folder and we’ve already initiated git, we can now commit them and upload them to GitHub so that we can reuse them in another machine or whatever we like to.

```
cd ~/.dotfiles && git add . && git commit -m 'feat: Dotfiles added'
```

We can play around with new configurations as we want in a safe manner since we can revert back to the latest working state whenever we like.
