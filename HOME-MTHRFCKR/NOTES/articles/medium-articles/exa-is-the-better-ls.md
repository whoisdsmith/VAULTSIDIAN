---
tags:: medium
created: 2022-08-05T17:17:14 (UTC -04:00)
tags: []
source: https://medium.com/javarevisited/exa-is-the-better-ls-grasp-information-faster-on-your-terminal-c7918ff3a5a7
author: Mirco
---

# Exa is the better ls. Grasp information faster on your terminal. | by Mirco | Javarevisited | Medium

---
## Make browsing your files more fun.

![[1TbV5t9-0Lig_FeQ8Kk3WQg.png]]

Everyone uses `ls` every day. It takes place six in my top ten used commands (calculated over the last 6803 commands):

```
   2000 git    589 mvn    427 gcloud    392 ./ci/deploy    298 cd    237 ls    223 docker    193 sudo    140 curl    113 terraform
```

A command used so often should be a pleasure to use. But the output of `ls` is rather dull.

Displaying the content of a folder with `ls -alh` looks like this:

![[1rrixS_Yw0kzI292AG0GuOw.png]]

Output of ls -alh

You get a lot of information, but it is hard to grasp:

1.  if it’s a file or a directory
2.  the access rights
3.  the user and group (blurred out)
4.  file size
5.  modify date
6.  file name

You can distinguish files and folders easily, but the rest is just white text. We could use some colors, and maybe icons?

## A better solution.

[exa](https://the.exa.website/) gives you just that. The website says it’s a ‘modern replacement for ls’, and it surely is.

> A modern replacement for `ls`.
> 
> You list files hundreds of times a day. Why spend your time squinting at black and white text?

You can install `exa` with your package manager:

```
sudo apt-get install exa
```

Look at the same folder with `exa`.

![[1s3NcWInQVCX--EQbBrSxXw.png]]

Output with exa

_You immediately spot some differences:_

1.  access rights are color coded
2.  every column has its own color
3.  icons show what kinds of files you have
4.  special files (`README.md`) are highlighted

Already better. But there is more. You do not know what is inside the folders using `ls`. With `exa --tree --level 2` you can see the content of each folder:

![[1HJJsZUQJIUrh2VYcdVCMfA.png]]

There is much more to `exa`. Check out all options at its [website](https://the.exa.website/).

**My favorite parameters are:**

1.  `-l` which gives you the list view
2.  `--icons` to get the icons
3.  `--no-user` to hide information about the owner
4.  `--group-directories-first` to show the directories first
5.  `--time-style long-iso` to change the date format.

I added an alias to my `.zshrc` (`.bashrc` if you use bash) which overrides `ll`:

```
alias ll='exa -l --icons --no-user --group-directories-first  --time-style long-iso'
```

Using this, you get:

![[1vGu8-dC28vajH0MR-ho9eg.png]]

My exa configuration

This enables me to grasp folder content much faster. I hope you can take advantage of this too.
