---
tags:: medium
created: 2022-08-05T17:17:38 (UTC -04:00)
tags: []
source: https://medium.com/featurepreneur/guide-to-iterm2-46cd4625d55a
author: Ajesh Martin
---

# Guide to Iterm2. iTerm2 is an open source replacement… | by Ajesh Martin | featurepreneur | Medium

---
![[1ha6bUhaMJpmnzD-5PUdxxg.jpeg]]

[iTerm2](http://www.iterm2.com/) is an open source replacement for Apple’s Terminal. It’s highly customizable and comes with a lot of useful features.

## Installation

Use [Homebrew](https://sourabhbajaj.com/mac-setup/Homebrew/) to download and install:

```
brew install --cask iterm2
```

## Customization

## Colors and Font Settings

Here are some suggested settings you can change or set, **they are all optional**.

-   Set hot-key to open and close the terminal to `command + option + i`
-   Go to profiles -> Default -> Terminal -> Check silence bell to disable the terminal session from making any sound
-   Download [one of iTerm2 color schemes](https://github.com/mbadolato/iTerm2-Color-Schemes/tree/master/schemes) and then set these to your default profile colors
-   Change the cursor text and cursor color to yellow make it more visible
-   Change the font to 14pt Source Code Pro Lite. Source Code Pro can be downloaded using [Homebrew](https://sourabhbajaj.com/mac-setup/Homebrew/) `brew tap homebrew/cask-fonts && brew install --cask font-source-code-pro`
-   If you’re using BASH instead of ZSH you can add `export CLICOLOR=1` line to your `~/.bash_profile` file for nice coloring of listings

## zsh

The Z shell (also known as `zsh`) is a Unix shell that is built on top of `bash` (the default shell for macOS) with additional features. It's recommended to use `zsh` over `bash`. It's also highly recommended to install a framework with `zsh` as it makes dealing with configuration, plugins and themes a lot nicer.

We’ve also included an `env.sh` file where we store our aliases, exports, path changes etc. We put this in a separate file to not pollute our main configuration file too much. This file is found in the bottom of this page.

Install `zsh` using Homebrew:

```
brew install zsh
```

Now you should install a framework, we recommend to use [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh) or [Prezto](https://github.com/sorin-ionescu/prezto). **Note that you should pick one of them, not use both.**

The configuration file for `zsh` is called `.zshrc` and lives in your home folder (`~/.zshrc`).

## Oh My Zsh

![[1vFPA0k4Pw6W6YBuwx8FKUw.png]]

[Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh) is an open source, community-driven framework for managing your `zsh` configuration. It comes with a bunch of features out of the box and improves your terminal experience.

Install Oh My Zsh:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

The installation script should set `zsh` to your default shell, but if it doesn't you can do it manually:

```
chsh -s $(which zsh)
```

## Configuration

The out-of-the-box configuration is usable but you probably want to customise it to suit your needs. The [Official Wiki](https://github.com/robbyrussell/oh-my-zsh/wiki) contains a lot of useful information if you want to deep dive into what you can do with Oh My Zsh, but we’ll cover the basics here.

To apply the changes you make you need to either **start new shell instance** or run:

```
source ~/.zshrc
```

## Plugins

Add plugins to your shell by adding the name of the plugin to the `plugin` array in your `.zshrc`.

```
plugins=(git colored-man-pages colorize pip python brew osx)
```

You’ll find a list of all plugins on the [Oh My Zsh Wiki](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins). Note that adding plugins can cause your shell startup time to increase.

zsh-syntax-highlighting

The Syntax Highlighting plugin adds beautiful colors to the commands you are typing.

Clone the zsh-syntax-highlighting plugin’s repo and copy it to the “Oh My ZSH” plugins directory.

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

zsh-autosuggestions

This plugin auto suggests any of the previous commands. Pretty handy! To select the completion, simply press → key.

Clone the zsh-autosuggestions plugin’s repo and copy it to the “Oh My ZSH” plugins directory.

```
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

Enforce Changes

To apply the changes you make you need to either **start new shell instance** or run:

```
source ~/.zshrc
```

## Themes

Changing theme is as simple as changing a string in your configuration file. The default theme is `robbyrussell`. Just change that value to change theme, and don't forget to apply your changes.

```
ZSH_THEME=pygmalion
```

You’ll find a list of themes with screenshots on the [Oh My Zsh Wiki](https://github.com/robbyrussell/oh-my-zsh/wiki/themes).

## Prezto

[Prezto](https://github.com/sorin-ionescu/prezto) is a configuration framework for `zsh`; it enriches the command line interface environment with sane defaults, aliases, functions, auto completion, and prompt themes.

Install Prezto:

```
git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
```

Next create your `~/.zshrc` by running:

```
setopt EXTENDED_GLOBfor rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do    ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"  done
```

For more information on customisation visit the [GitHub repository for Prezto](https://github.com/sorin-ionescu/prezto).

## Modules

Add modules to Prezto by editing `~/.zpreztorc` and adding the modules as strings to the list:

```
zstyle ':prezto:load' pmodule \  'environment' \  'terminal' \  'editor' \  'history' \  'directory' \  'spectrum' \  'utility' \  'completion' \  'git' \  'syntax-highlighting' \  'history-substring-search' \  'prompt'
```

And don’t forget to apply your changes by **starting a new shell instance**.

## Themes

To list all available themes run:

```
prompt -l
```

Then open up your config file (`~/.zpreztorc`) and change to the theme you want:

```
zstyle ':prezto:module:prompt' theme 'minimal'
```

## `env.sh`

To include `env.sh`, open `~/.zshrc` and add the following:

```
source ~/<path to file>/env.sh
```

This file comes with some pre-defined settings, **they are all optional**. Please review them before you use them as your configuration. These are just examples to show you what you can customise in your shell.

```
#!/bin/zsh# Add commonly used folders to $PATHexport PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"# Specify default editor. Possible values: vim, nano, ed etc.export EDITOR=vim# File search functionsfunction f() { find . -iname "*$1*" ${@:2} }function r() { grep "$1" ${@:2} -R . }# Create a folder and move into it in one commandfunction mkcd() { mkdir -p "$@" && cd "$_"; }# Example aliasesalias cppcompile='c++ -std=c++11 -stdlib=libc++'alias g='git'
```

## `tree`

`tree` is a recursive directory listing command that produces a depth indented listing of files.

## Installation

To install the latest version, use homebrew:

```
brew install tree
```

## Usage

Running `tree` will produce output like this:

```
$ tree.├── Apps│   ├── Octave.md│   ├── README.md│   ├── Settings.md│   ├── araxis-merge.jpg│   ├── beyond-compare.png│   ├── delta-walker.jpg│   ├── filemerge.png│   └── kaleidoscope.png├── CONTRIBUTING.md├── Cpp│   └── README.md├── Docker│   └── README.md├── Git│   ├── README.md│   └── gitignore.md└── Go    └── README.md5 directories, 14 files
```

To limit the recursion you can pass an `-L` flag and specify the maximum depth `tree` will use when searching.

```
tree -L 1
```

will output:

```
.├── Apps├── CONTRIBUTING.md├── Cpp├── Docker├── Git└── Go5 directories, 1 files
```

## [fzf](https://sourabhbajaj.com/mac-setup/)

## `fzf`

`[fzf](https://github.com/junegunn/fzf)` is a general-purpose command-line fuzzy finder. On it's own it's not very useful but when combined with other tools it becomes super powerful.

## Installation

Use [Homebrew](https://sourabhbajaj.com/mac-setup/Homebrew/README.html) to install `fzf`:

```
brew install fzf
```

If you want to use shell extensions (better shell integration):

```
/usr/local/opt/fzf/install
```

which gives you:

-   Key bindings (`CTRL-T`, `CTRL-R`, and `ALT-C`) (available for _bash_, _zsh_ and _fish_)
-   Fuzzy auto-completion (available for _bash_ and _zsh_)

## Example Usages

Add any of these functions to your shell configuration file and apply the changes to try them out. Or just paste the function in your terminal if you just want to try it out without saving it.

```
# fd - cd to selected directoryfd() {  local dir  dir=$(find ${1:-.} -path '*/\.*' -prune \                  -o -type d -print 2> /dev/null | fzf +m) &&  cd "$dir"}# fh - search in your command history and execute selected commandfh() {  eval $( ([ -n "$ZSH_NAME" ] && fc -l 1 || history) | fzf +s --tac | sed 's/ *[0-9]* *//')}
```

**For more fuzzy search examples see the** [**official repo**](https://github.com/junegunn/fzf#fuzzy-completion-for-bash-and-zsh)**.**

## Chrome history from your terminal

Open up your shell config and add following function:

```
# ch - browse chrome historych() {  local cols sep  cols=$(( COLUMNS / 3 ))  sep='{::}'  cp -f ~/Library/Application\ Support/Google/Chrome/Profile\ 1/History /tmp/h  sqlite3 -separator $sep /tmp/h \    "select substr(title, 1, $cols), url     from urls order by last_visit_time desc" |  awk -F $sep '{printf "%-'$cols's  \x1b[36m%s\x1b[m\n", $1, $2}' |  fzf --ansi --multi | sed 's#.*\(https*://\)#\1#' | xargs open}
```

**Note**: Ensure that path to `History` file is correct; read more information on [StackOverflow](https://stackoverflow.com/a/16742333/1564365).

## `ack`

`ack` is a search tool designed for code. It's built to be a replacement for `grep` with higher speed and more options.

## Installation

To install the latest version, use homebrew.

```
brew install ack
```

## Why use `ack` over `grep`

-   Faster
-   Skips unimportant files by default
-   It searches recursively by default
-   Customizable

## Usage

```
ack [OPTION]... PATTERN [FILES OR DIRECTORIES]
```

Let’s say you want to find all JavaScript files that are using the module `pancakes` in your project, with `ack` it's as easy as

```
ack --js pancakes
```

Or you may want to find all files that _does not_ contain the word _brew_

```
ack -L brew
```

## Customization

You can customize `ack` to behave the way you want it to, this configuration i s stored in `/.ackrc`.

For example, you can add a custom type to use as a flag when searching. The following configuration will allow you to only search in `.md`, `.mkd` and `.markdown` files using the `--markdown` flag.

```
--type-set=markdown=.md,.mkd,.markdown
```

You can also tell ack to always sort and use colors in the result.

```
--sort-files--color
```

To see what configuration `ack` uses you can use the `dump` flag.

```
ack --dump
```

## Alternatives to `ack`

There’s [The Silver Surfer](https://github.com/ggreer/the_silver_searcher) which describes itself as a

> _A code searching tool similar to_ `_ack_`_, with a focus on speed._
