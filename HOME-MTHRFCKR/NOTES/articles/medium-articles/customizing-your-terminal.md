---
tags:: medium
created: 2022-08-05T17:17:32 (UTC -04:00)
tags: []
source: https://medium.com/@sammykerridge/customizing-your-terminal-becoming-a-zsh-power-user-d9a8aab5aad0
author: Sam Kerridge
---

# Customizing your Terminal — Becoming a zsh Power User | by Sam Kerridge | Medium

---
Welcome to the first episode in a new mini-series of satisfying terminal configs and lazy bash hacks. Because I’m an iOS developer — this post will be for all my fellow MacOS homies out there. Windows version _maybe_ en route my dudes.

I love scripting, I’m quite lazy, and I’m a sucker for anything slightly aesthetic. Combine those traits and you’ve got a kid with a fancy terminal custom designed to speed up workflows and keep you in the coding zone longer. I am also a huge fan of a custom, personalized terminal, because honestly — I love feeling like a hackermans power user whenever I touch a terminal.

![[0ZwiYcDLncJ8IMyp5.jpeg]]

_Hackermans_

This post will focus mostly on the visual setup for iTerm2, and also introduce some ZSH magical plugins I now can’t live without. The next post in this series will be how I like to configure my aliases to speed up workflows, and how I keep my config synced across devices using .dotfile magic. I should have split this post into two parts — but I didn’t so disclaimer below yo:

**Warning:** this post is a **long boi**, if you intend to follow it, strap in and block out an hour (at least).

![[1jokKsbou9ka-GXNkXSGHiQ.png]]

_much beauty_

## Agenda

Above is my custom terminal configuration for iTerm2 running a zsh shell and a few fancy plugins. Yours doesn’t have to look anything like this by the end of reading this, the guide I’m writing here works for any look you want, I’m simply showing you the tools and steps you’ll need to get there.

**Today I’ll be taking you through:**

-   How to get the status line prompt and customise it to fit your needs (pictured above)
-   How to get the color coded, cleanly formatted, and iconified look from your `ls` command (pictured above)
-   Installing plugins like autocomplete and syntax highlighting
-   How to connect your terminal to a global (OS wide) keybind that can overlay any application
-   Rich command reverse searching and fuzzy finding
-   Customizing your theme, and some handy iTerm specific settings

So let’s crack into it hey

## You will need:

## iTerm2

As my intro alludes to, the terminal we will be using is called [**iTerm2**](https://iterm2.com/), and it’s incredible. It has a tonne of customisation options, it’s (reasonably) fast, and is perfect for our needs today.

-   Download a stable iTerm2 release from [here](https://iterm2.com/downloads.html)

## zsh

The shell we will be looking at is called **zsh** (z-shell). Zsh is a wonderful shell that is nearly identical to bash (Bourne-again shell), however allows for a lot more customisation options. MacOS adopted zsh to succeed bash and become their default shell a year or two ago — so I will assume you’re already running this.

-   If not, follow the install instructions for MacOS [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)

## Oh-my-zsh

Zsh has this crazy cool open source community who maintain a framework called Oh-my-zsh. They’ve come together to create a fantastic collection of [plugins](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins) to help manage your shell configuration and speed up your workflows. Think of things like autocompleting commands, [sexy themes](https://github.com/ohmyzsh/ohmyzsh/tree/master/themes), better tab completion, or preconfigured aliases → all available through easy to install plugins.

-   Follow the download instructions [here](https://github.com/ohmyzsh/ohmyzsh)

## Powerlevel10k

Gather round folks, this is where the magic happens. Powerlevel10k is the _much_ speedier successor to Powerlevel9k (DBZ reference anyone?). But what is it? It is essentially a theme, but due to the amazing config wizard, it acts more like a plugin.

This theme is what will allow you to customize your prompt with a bunch of handy infographics. These little pieces of information are genuinely incredible for quick info at a glance (and some of them just look cool).

![[0RhVB1Ec7RJUM6g47.png]]

_My personal prompt style_

![[0vPqYcAPcCxzthuaI.png]]

_Prompt styles offered by Powerlevel10k_

These could be things such as language version (e.g. Ruby version), the Kubernetes cluster you’re working in (kube context), your Git status (current branch, how out of sync you are to remote, untracked files), your current working directory (full path), your current virtual environment, your AWS assumed role, and so much more.

Powerlevel10k also has a few features built-in to help speed up the loading of your oh-my-zsh plugins and provide the user with snappier prompts after each command.

-   To install → follow the install instructions for oh-my-zsh on [this page](https://github.com/romkatv/powerlevel10k)
-   You may notice it asks you to install a specific font for this to work properly → read below

## Nerdfont

The last thing you’ll need to install is a “[powerline font](https://powerline.readthedocs.io/en/latest/overview.html)”. There is a status line plugin written for vim, allowing you to customize status lines, and it also works with most major shells.

[Overview](https://powerline.readthedocs.io/en/latest/overview.html)

Powerline fonts allow us to take advantage of this plugin, and they also have icons built into them which we’ll make use of later.

Powerlevel10k has a [recommended font](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k) to install called “Meslo nerd font”. Their version comes patched to work beautifully with Powerlevel10k, so I can personally recommend this one.

-   To install the recommended font for Powerlevel10k, it will prompt you to install during the setup wizard (which we’ll get to later, so don’t stress)

_Alternatively_, you may be able to find a cool (and compatible) one on [Nerdfonts.com](https://www.nerdfonts.com/)

## Ruby >= 2.5

**Note:** This step is only necessary if you want to add the color highlighting to your `ls` command, as that’s the only plugin today which uses Ruby.

-   You might already have a distribution of Ruby installed on your system. Type `ruby -v` to check
-   Otherwise, type `brew install ruby` to get the latest version

## How to:

Assuming you’ve installed everything above (with the exception of a nerd font), you should be ready to charge on with the actual config of your terminal.

## Configure Powerlevel10k

This theme (p10k) has a tonne of customization options and a beautiful setup wizard to walkthrough.

1.  Install Powerlevel10k as explained above
2.  **Restart** your zsh shell
3.  Type `p10k configure` and follow the wizard to choose your preferences

![[0mXX05zPnFHg4KN0S.gif]]

4\. When prompted if you want to install the recommended font → answer **yes**

5\. To update your font in iTerm2 → preferences → profiles → text → font → Hack Nerd Font

## Customize your prompt

After finishing the setup wizard, you’ll want to customize the sections that are displayed on your prompt. There are a bunch turned on by default which I don’t need and do nothing but slow down my terminal. I turned these off and so should you.

To get these separate sections on your command prompt, you’ll have to dive into the config file for Powerlevel10k. This file is a dotfile called `.p10k.zsh` and should be located in your home directory `~`

**Tip:** if you’re using MacOS Finder and can’t see it → that’s the wizardry of dotfiles.

-   Use **CMD + SHIFT + .** to show hidden files and folders.

When you have this file open → there are two important array declarations → `POWERLEVEL9K_LEFT_PROMPT_ELEMENTS` , and vice versa for the right hand side.

Think of these two arrays as a _literal_ vertical split in your terminal straight down the middle. The arrays are a **left-to-right** defined list of all the sections you want to display, in-order.

Let’s look at mine for reference.

![[0-jEnZyBgGLUrz6Js.png]]

_My left prompt-line configuration_

![[0pIKzhzHC4Sess4_C.png]]

_My actual prompt-line_

The names for **all** of the available segments should be listed in this file, but commented out. There is also a comment beside each one saying what the purpose for it is.

If we look at the first picture above, and compare it to the second picture, you can use some of your deductive skills to visualise their direct relationship.

On the left hand side I want to show the OS icon, the current directory, and my git status. Following that, I can use the “newline” keyword to push things down a line or two. You can see I have a newline keyword followed by the “prompt char”.

Looking at the second picture, you’ll notice that my prompt/cursor is on a fresh line.

![[098RcQx56vTpu4_oW.gif]]

Configure this however you like, save the file, refresh your terminal, then BOOM → you’re on your way to a fully personalised terminal.

**Extra:** Powerlevel10k has a beta-ish feature called [“Show on command”](https://github.com/romkatv/powerlevel10k#show-on-command). This essentially hides widgets until you type a command which relates to it (like typing a kube command and your kube context appearing). If you want to do this then just follow their instructions in the [README](https://github.com/romkatv/powerlevel10k#show-on-command).

## Color code your \``ls`\` command

![[1jokKsbou9ka-GXNkXSGHiQ.png]]

Because we’ve installed a beautiful font loaded with icons, we may as well put them to use. ColorLS is a Ruby script built for beautifying your directory viewing commands, making the output much easier to parse on the eyes.

1.  As mentioned earlier, installing this requires a Ruby version >= 2.5, and a powerline font.
2.  You can look over the [README here](https://github.com/athityakumar/colorls) (there a lot of flags and options, so you should have a browse)
3.  If you can’t be bothered reading, just run `gem install colorls`
4.  Once installed, we want to make it easy to use! I do this by attaching the commands to an alias.
5.  **Tip:** for the uninitiated → an alias is a way for you to bind a commonly used command to a shortcut string for faster usage.

> I will go more into depth of my alias setup in the next post

## **Aliases with zsh**

An alias is a way to assign a piece of a bash script to a shortened command. They are extremely handy for storing and shortening commands you use often.

1.  To store aliases globally and make sure they are loaded every time we launch a terminal, we need to store them in our zsh shell’s config file
2.  Your `.zshrc` file is located at `~/.zshrc` I access this file often → so let’s alias it
3.  `alias ed=’code ~/.zshrc’` → I called this **ed** (short for edit)
4.  I use VS Code to edit this file via this command: `code` →`vi`, `nano`, or `vim` will work in place too.
5.  Now you need to refresh your terminal to read/source the file with our newly added alias. This is another common command → so let’s alias this too. Closing and reopening your terminal will have the same effect.
6.  `alias ref=’source ~/.zshrc’` → I called this **ref** (short for refresh)
7.  Now when you want to add a new alias, simply type `ed` to open your editor. After saving your `.zshrc` file, simply type `ref` to re-source your config and access this new command.

## **ColorLS aliases**

Now that we can add and use an alias, let’s do what we came here for.

I have two aliases setup for ColorLS, have a look through their [README](https://github.com/athityakumar/colorls) to see which are best suit you

1.  `alias l=’colorls -A --sd’`

I use this in place of my standard \`ls\` command. It outputs the whole directory color coded, with icons beside files/folders.

2. `alias ll=’colorls -lA --sd’`

This is for when I need more information (such as file size or user permissions). It outputs the directory in one long table view with a row for each file, and it’s metadata.

![[1jokKsbou9ka-GXNkXSGHiQ.png]]

_What happens when I type the letter L (capital letter for your readability, I use lowercase)_

![[1Nro9fQnF_AkSJIUxYCR9Qg.png]]

What happens when I type LL

## Oh-my-zsh Plugins

As I mentioned earlier → Oh-my-zsh is a community driven framework which provides support for either official plugins, or custom ones.

-   Find the official list [here](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins)
-   Click into the folders and the README for each plugin should explain it’s use
-   If you want to see the actual behaviour, all logic should be inside the `<plugin_name>.plugin.zsh` file

The official list is quite comprehensive, however I only use two. This is essentially for two reasons:

**Too many plugins will slow down shell startup**

-   However the Powerlevel10k plugin/theme we have running claims to have an ‘instant prompt’ by facilitating faster plugin load times (maybe via caching? unsure).

**A lot of the plugins are simply convenient lists of aliases (e.g. a bunch of git aliases)**

-   I _personally_ prefer to write my _own_ functions and aliases, as it allows me to remember them much better and **write them as I need them** — rather than just add a plugin and then have 1000 aliases to read through and never use

_Official_ plugins are a breeze to install, as they are just a single `.zsh` file and a [README.md](http://readme.md/) file. This means, if you’ve installed Oh-my-zsh → **all** of the official plugins are already cloned at `~/.oh-my-zsh/plugins/`

_Custom_ plugins (like the ones we will be using today) are stored inside the `oh-my-zsh/custom` directory. This directory is empty by default, so to install a custom plugin → all you need to do is clone the plugin you would like to use into your `oh-my-zsh/custom` directory, and then follow the steps below.

Oh-my-zsh does another wonderful abstraction for us by simply offering a ‘plugins’ array inside our `~/.zshrc` shell configuration file (remember → our `ed` alias should open this file). This means to install an official plugin, simply add the name of it to the array and the rest will be handled for you!

**Note:** Our two plugins today will be custom installs, so make sure to follow the instructions below to get them working.

![[0E_Jgoszy88qiK4Q3.png]]

_How my plugins array in_ `_~/.zshrc_` _looks_

![[0R2srHcTCRP4QW-gL.png]]

_My prompt with auto-suggestions_ **_and_** _syntax highlighting turned on_

[**Auto-suggestions**](https://github.com/zsh-users/zsh-autosuggestions)

A wonderful plugin which uses your shell history to suggest commands back at you as you type.

-   To install this, follow the steps for oh-my-zsh [here](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh), then restart your terminal
-   To use this plugin, hit the right arrow key to insert a suggestion `**→**`

For a bit more styling on your auto-suggestion (to help differentiate suggestions from text easier), add this line at the bottom of your `~/.zshrc` file (you can edit the hex color value)

```
ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE="fg=#939393,bold,underline"
```

[**Syntax Highlighting**](https://github.com/zsh-users/zsh-syntax-highlighting)

A plugin which highlights certain syntax’s red as you type. When the command is recognized it changes to green. Really handy for personal aliases and functions as it works on those too.

-   To install this, simply follow the instructions for oh-my-zsh in [this repo](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh), then restart your terminal

## iTerm2 Specific Configuration

There are some insane settings in iTerm2 that just make the experience so much more pleasurable in my opinion, so let’s go through a few. All of these settings live in the preferences for iTerm2

## **Theming**

You can set all of your color schemes in here. You can either Google some prebuilt iTerm2 color schemes, use the in-built ones, or design your own like I did. I don’t plan on telling you what colors to change, it’s a trial by fire kind of process. Just play with the colors and watch your terminal update (changes should be instantly reflected)

To change colors → Preferences → Profiles → Colors

## **Default Window Sizing**

Personally I find the default window size to be a bit on the small side. Luckily, you can change how wide and tall the window opens as.

To change default window size → Preferences → Profiles → Window → Columns + Rows

## **Background Image**

Totally optional, but if I went this far creating a nice looking terminal then I may as well finish it off with a cool background image. In the spirit of being a Macbook user, I jumped on the incredible [Unsplash](https://unsplash.com/), and eventually went with an image that reminds me of an old Apple ad.

To add a background image → Preferences → Profiles → Window → Background Image

![[0J2fovBBWI2u55jgT.png]]

## Fuzzy Finding and Rich Reverse Searching

I don’t know much about fuzzy finding and how advanced power users leverage it, but I do know a couple of awesome use cases for it. If you want to find out more about the advanced use cases, look through the [README](https://github.com/junegunn/fzf) or just do some [googlin’](https://medium.com/better-programming/boost-your-command-line-productivity-with-fuzzy-finder-985aa162ba5d).

A fuzzy finder is essentially a search filter inside your terminal. You can filter by things like command history, git commits, files, aliases, processes, and much much more.

I use a fuzzy finder for two main things → a rich reverse history with a great UI, or recursively searching for a directory or file. We’re going to use a fuzzy finder called [**fzf**](https://github.com/junegunn/fzf)

## **Installation**

-   Throw a brew install in ya terminal for installing fzf

`brew install fzf`

-   You’ll want to bind the fzf directory finder widget to **ALT/OPTION + C**

Because MacOS inserts an alternative keyboard character when using this key combination, we can use that special character to bind our widget call to

Throw `bindkey "ç" fzf-cd-widget` in your `./zshrc` file

## **Usage**

There are 3 wonderful use cases for this plugin

Rich reverse search **history** — **CTRL + R**

-   This is a feature of any normal shell when you hit **CTRL + R**, you can search through all of your previously executed commands.
-   However, fzf adds a fantastic UI to this command which lets you see a bunch of commands at once, and use the arrow keys to navigate to the command you want.

Recursive **file** searching — **CTRL + T**

-   Allows you to recursively (and very quickly) search for a **filename** under your current working directory
-   Pushing enter to select a file will insert the file’s path into your current shell command, so is best used mid-command

Recursive **directory** traversing — **ALT + C**

-   Allows you to recursively (and very quickly) search for a **directory** under your current working directory
-   Pushing enter on a directory will take you to that directory

## Hotkey Window

Do you know what a hotkey window is on MacOS? I didn’t until about 2 weeks ago, now I use it every single day. A hotkey window is a globally recognized shortcut which allows a program to overlay anything on your screen as if it were the top layer in Photoshop. There is only one of these in existence with default MacOS config — spotlight search.

If you haven’t heard me rave about it, **CMD + SPACE** is my favorite shortcut ever to walk this earth. It brings up the oh so wonderful spotlight search → MacOS’ default (extremely fast and powerful) system wide search.

Turns out you can set these hotkeys yourself, so long as the software has support for it. iTerm2 has a setting for this which I bound to a fairly empty but easy to use keybind — **CMD + \\**

To set this up → preferences → keys → hotkey → create a dedicated hotkey window

**Note:** Setting up a hotkey window with iTerm2 will actually just create a new profile under preferences → profiles → hotkey window

-   It is important to know this → as any changes made to this profile will _only_ affect the overlay, and any changes made to the other profiles will be reflected in those.

To change the screen it is displayed on, the transparency, and the position on the screen:

-   preferences → profiles → hotkey window → window → style + screen + transparency

![[0mwVa1yt5EaWCKwrI.png]]

_My terminal appearing over a fullscreen Chrome as a hotkey window_

## Vim Fix

One last thing to note is that somewhere along this convoluted terminal setup, I _think_ that Vim was overridden to lose it’s color syntax highlighting. This annoys me as I use it for all my git ops, but it’s a simple fix if the same thing happened to you.

All we need to do is create an `rc` file at our home directory for vim to read settings from, then tell it to turn syntax highlighting on. This command will do both for you

```
echo "syntax on" > ~/.vimrc # might need a sudo in front of it
```

## Congratulations!

You made it to the end of a monolithic tutorial, what a wild ride it was. If you stuck with me this long → mad respect, much love.

Next in the series is how I configure my aliases and functions using some dotfile magic, plus how I sync them across all the devices I code on.

Thanks ya’ll,  
Kerridge

**Config count:** 19  
**Install count:** 30
