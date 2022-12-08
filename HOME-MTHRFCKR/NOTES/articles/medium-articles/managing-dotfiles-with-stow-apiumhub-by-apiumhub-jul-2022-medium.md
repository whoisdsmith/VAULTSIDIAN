---
tags:: medium
created: 2022-08-05T17:19:04 (UTC -04:00)
tags: []
source: https://medium.com/@Apiumhub/managing-dotfiles-with-stow-apiumhub-1ebd9007736c
author: Apiumhub
---

# Managing dotfiles with stow — Apiumhub | by Apiumhub | Jul, 2022 | Medium

---
![[1xBI14dvKyWS-SSHE0JXrkg.jpeg]]

As a programmer, much of our time at work is spent developing code (and attending meetings, of course. ) So much, that we usually spend a lot of time configuring the toolset that we use on a daily basis. We are not only talking about the evolution of the configuration, but also about how to configure your new laptop, having several computers, or simply sharing a certain configuration of a certain tool with a colleague.

The great majority of applications (and more in unix systems) are configured through the well-known “dotfiles” (stored in the user’s $HOME), that are not more than files or folders that begin with a . to configure the applications (ex: .bashrc, .git/). The purpose of starting with a dot is that by default operating systems treat them as hidden files and don’t show them unless you tell them to.

Before we start, let’s explain the 3 terms we need to know to work with [STOW](https://www.gnu.org/software/stow/manual/stow.html), which are: Package, Stow Directory and Target Directory.

-   **Package:** It’s a collection of files that must be “installed” together in the same target directory.
-   **Stow directory:** It’s the repository where all our packages will be.
-   **Target directory:** It’s the directory where we want to install those configurations that are in our packages.

The functionality that we are looking for Stow is going to generate a symbolik link of the files that we have inside our packages in the target directory. In the example, if we run `stow git`, it will create a link from ~/.gitconfig to ~/.dotfiles/git/.gitconfig.

In this case, the convention decided by the community is to place everything inside a directory called .dotfiles inside our home, but this is something that can be appreciated reading forums and articles about dotfiles management. It has certain logic since in stow, by default, the target directory is the parent of the stow directory. That means that if we place ~/.dotfiles as the stow directory, the target directory will be ~/, which is where we will want to place our dotfiles.

The purpose of this article is to get our git (.gitconfig) and zsh (.zshrc) configuration out of our home without any control and move it into our .dotfiles folder, where we can upload it to a git repository (stow with git has very good synergy), synchronize it with Dropbox, or whatever we like.

To begin, we are going to create our stow directory, which can be wherever we like, but in this article we will use ~/.dotfiles for the reasons that have been previously explained. Now, we are going to start creating the git configuration. For it, we will create our `git` package inside our stow directory, and inside it, the configuration files related to git that we want to create a simlink in the target directory.  
In this case it will be only our .gitconfig:

$ cd ~  
$ mkdir -p .dotfiles/git

$ touch .dotfiles/git/.gitconfig

Now what we are looking for is to copy the content of the .gitconfig with the current configuration that is in the user’s $HOME (~/.gitconfig), and paste it in the new file generated inside our stow directory.  
To do this, we are going to launch the stow command with the parameters -adopt, -n and -v, and as an argument we will tell it that we want to stow in the git folder: `stow -adopt -nv git`.

$ stow -adopt -nv git

Let’s explain what each option does separately:

-   **\-n:** With this option we are telling stow not to execute any action, just tell us what it intends to do if we remove the option.
-   **\-v:** This option is the one that will allow us to read what stow intends to do (in the end it’s to increase the verbosity level).
-   **\-adopt:** This option is the only one that modifies the stow directory, all the others focus on the target directory. With this option what we do is that prior to stowear, it will move the current file in the target directory to the stow directory, and then create the link. Very useful when we are starting to create our .dotfiles.

Once we see the actions it will do, we just need to remove the `-n` option from the command to run it:

$ stow -adopt -v git

With this we can see how to save the current configuration inside our .dotfiles and how stow manages all the links in an easy way.

To finish the article, I would like to comment in a summarized way what other things I have needed to do with stow:
