---
tags:: medium
created: 2022-08-05T17:16:35 (UTC -04:00)
tags: []
source: https://medium.com/@miniChang8/top-cli-tools-%EF%B8%8F-for-software-developers-productivity-on-mac-in-2022-d425ae37154c
author: Mini Chang
---

# Top CLI tools 🛠️ for Software Developer’s Productivity on Mac in 2022 | by Mini Chang | Medium

---
Over the past decade, I found I am pretty productive in different teams as a software developer. Besides passion and interests, being familiar with Vim and leveraging a handful of productivity tools make me more productive than others. Here, I share my top CLI tools on my daily basis.

## 1\. iTerm2 ([https://iterm2.com/index.html](https://iterm2.com/index.html))

[iTerm2](http://iterm2.com/) is much better than default Terminal. iTerm2 has a lot of features which default Terminal does not have. For example, split pane view, hotkey window for instant terminal anywhere, trigger, etc. This would be the first thing that I would install on the development environment.

![[1PmNB_vysV9Sy2q25F9Natg.png]]

## 2\. Oh My Zsh ([https://ohmyz.sh/](https://ohmyz.sh/))

With good terminal, it is not enough. “ Zsh” + [“Oh My Zsh”](https://ohmyz.sh/) will unleash your terminal. For example, it allows custom prompt styles and integrates well with git, fzf, and so-and-so.

![[1qOJiQhV9GAfl2bBq82lHTA.png]]

## 3\. Autojump ([https://github.com/wting/autojump](https://github.com/wting/autojump))

[Autojump](https://github.com/wting/autojump) is a faster way to navigate your filesystem in your terminal. It makes you type “j keywork” simply to navigate to the most frequent visited folder. There are other choices like Z or Fasd. But I have been using autojump for many years, so I get used to [Autojump](https://github.com/wting/autojump). You can try Z or Fasd to see which one you prefer.

## 4\. Silver searcher([https://github.com/ggreer/the\_silver\_searcher](https://github.com/ggreer/the_silver_searcher)). Aka “ag”

Sometimes, we need to search code and certain content quickly. “ag” is great in terms of performance. Sometimes, I also use ag to replace content.

```
Search by keyword$ ag [keyword]Replace foo with goo in a certain dir$ ag -0 -l "$1" | xargs -0 perl -pi.bak -e "s/foo/goo/g"
```

## 5\. fzf ([https://github.com/junegunn/fzf](https://github.com/junegunn/fzf))

fzf is a fuzzy finder. It can find by searching anything including files, directory, etc. You can also config it with other plugins like ag, ssh, etc.

Example of searching a file

![[1JbAaeafgAO36FBpUU4xkVA.gif]]

## 6\. fuck ([https://github.com/nvbn/thefuck](https://github.com/nvbn/thefuck))

The fuck command can correct errors according to the previous console commands. The below is an example running shown in the github.

![[1pQ0_4IjuoZyf-yuMyQYGrA.gif]]

## 8\. jq ([https://github.com/stedolan/jq](https://github.com/stedolan/jq))

You might often find yourself dealing with JSON output. jq is a very nice tool to filter and transform JSON output from shell commands. For example, parsing and searching the JSON output, grepping a field from a REST service with (m)curl, etc.

## 9\. tmux([https://github.com/tmux/tmux](https://github.com/tmux/tmux))

tmux is a terminal multiplexer: it enables a number of terminals to be created, accessed, and controlled from a single screen. tmux may be detached from a screen and continue running in the background, then later reattached. Also, tmux lets you split your terminal into multiple terminals vertically or horizontally by using simple shortcuts. Most importantly, tmux makes you to run the long-running task in the background. I used it in my remote server and my local mac.

![[1r_W4LDuF0IQo3zp4xIf_FA.png]]

## 10\. grc ([https://github.com/garabik/grc](https://github.com/garabik/grc))

grc is to colorize output for several linux command line tools. For example,

```
grc traceroute -n google.com
```

![[14N5Os0SmXA546DpZd8YtEA.png]]

## 11\. cheat.sh([https://github.com/chubin/cheat.sh](https://github.com/chubin/cheat.sh))

It is an instant coding answers via the command line. There are a few instant coding answers CLI tool. I’ve been using [howdoi](https://github.com/gleitz/howdoi) and [cheat.sh](https://github.com/chubin/cheat.sh). But I feel cheat.sh is more comprehensive, and it does not need to install other python modules in order to run it. Also, I could find vim plugin, pycharm/intellij plugins for cheat.sh. I also write a couple scripts and integrate with fzf for cheata.sh. I can share in another post. The demonstration of cheat.sh is like.

![[1TWAdQ4QQKto7soMKdGmCCQ.gif]]

## 12\. tldr([https://github.com/tldr-pages/tldr](https://github.com/tldr-pages/tldr))

cheat.sh is great. However, sometimes, we forgot how to use some commands. Although typing -help can check the document, sometimes, it is difficult to know how to use the command arguments. tldr is a cli to provide an example quickly for the most commonly used CLIs.

![[1PiMAslK_BgfYSioqBF8VZQ.png]]

## 13\. bat([https://github.com/sharkdp/bat](https://github.com/sharkdp/bat))

“cat” is a useful utility but the lack of syntax highlighting can make larger documents tricky to read if you just quickly want to see the contents of a file. bat CLI gives more features including syntax highlighting that’s aware of which file it’s reading, adding line numbers, automatically page the output if required, showing non-printable characters, etc

![[1-8ohRZIRa1ljKzOlRyGvzw.png]]

## 14\. Imgcat([https://github.com/eddieantonio/imgcat](https://github.com/eddieantonio/imgcat))

Sometimes, we want to see an image on the terminal without opening finder or photo app. Imgcat open source offer this ability to see an image on the terminal.

```
imgcat somepic.png
```

Besides the above CLIs, I also shared [useful and productive apps](https://medium.com/@miniChang8/top-apps-for-developers-productivity-on-mac-e4152100bd5b) which I used daily basis in another post.
