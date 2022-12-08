---
tags:: medium
created: 2022-08-05T17:19:00 (UTC -04:00)
tags: []
source: https://medium.com/@CryptOdin/dotfiles-bare-git-2e45ed38b79f
author: Odin
---

# Dotfiles Bare Git. If you’re looking for an great way to… | by Odin | Jun, 2022 | Medium

---
If you’re looking for an excellent way to backup or share your dotfiles, using bare git is a simple and quick way to keep your dotfiles up to date.

After distrojumping or reinstalling the distro i started saving my dotfiles so I don’t have to set up every app from scratch every time. I’ve used several ways to backing them up from simple copy and past to usb or cloud to symlink and git then now i landed on using bare git from youtuber [Distrotube](https://www.youtube.com/watch?v=tBoLDpTWVOM).

Lets just get right to it.

First make a folder where you will store everything that normaly get stored in .git folder and init it:

```
mkdir $HOME/.dotsgit init --bare $HOME/.dots
```

Depending on if you got bash or zsh as shell there is some diffrence in the command you can figure out your shell by using `ps -p $$`

Bash:

```
echo "alias dots='/usr/bin/git --git-dir=$HOME/.dots --work-tree=$HOME'" >> $HOME/.bashrc
```

zsh:

```
echo "alias dots='/usr/bin/git --git-dir=$HOME/.dots --work-tree=$HOME'" >> $HOME/.zshrc
```

this command will avoid your git status to show every change made in your home directory only the one you got tracked

```
dots config --local status.showUntrackedFiles no
```

make a new repo and use the commands:

```
dots add .bashrcdots commit -m "added bashrc"dots branch -M maindots remote add origin https://github.com/USERNAME/YOURREPO.gitdots push -u origin main
```

now you can add all your dotsfiles to the repo with the normal git commands add, commit and push just have to use dots instead of git.

You can change it to diffrent command then dots by changing the word after alias in ether the .bashrc or .zshrc file
