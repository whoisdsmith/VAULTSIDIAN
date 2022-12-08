fzf is a general-purpose command-line fuzzy finder.

[![](https://raw.githubusercontent.com/junegunn/i/master/fzf-preview.png)](https://raw.githubusercontent.com/junegunn/i/master/fzf-preview.png)

It's an interactive Unix filter for command-line that can be used with any list; files, command history, processes, hostnames, bookmarks, git commits, etc.

## Pros

-   Portable, no dependencies
-   Blazingly fast
-   The most comprehensive feature set
-   Flexible layout
-   Batteries included
    -   Vim/Neovim plugin, key bindings, and fuzzy auto-completion

## Table of Contents

-   [Installation](https://github.com/junegunn/fzf#installation)
    -   [Using Homebrew](https://github.com/junegunn/fzf#using-homebrew)
    -   [Using git](https://github.com/junegunn/fzf#using-git)
    -   [Using Linux package managers](https://github.com/junegunn/fzf#using-linux-package-managers)
    -   [Windows](https://github.com/junegunn/fzf#windows)
    -   [As Vim plugin](https://github.com/junegunn/fzf#as-vim-plugin)
-   [Upgrading fzf](https://github.com/junegunn/fzf#upgrading-fzf)
-   [Building fzf](https://github.com/junegunn/fzf#building-fzf)
-   [Usage](https://github.com/junegunn/fzf#usage)
    -   [Using the finder](https://github.com/junegunn/fzf#using-the-finder)
    -   [Layout](https://github.com/junegunn/fzf#layout)
    -   [Search syntax](https://github.com/junegunn/fzf#search-syntax)
    -   [Environment variables](https://github.com/junegunn/fzf#environment-variables)
    -   [Options](https://github.com/junegunn/fzf#options)
    -   [Demo](https://github.com/junegunn/fzf#demo)
-   [Examples](https://github.com/junegunn/fzf#examples)
-   [`fzf-tmux` script](https://github.com/junegunn/fzf#fzf-tmux-script)
-   [Key bindings for command-line](https://github.com/junegunn/fzf#key-bindings-for-command-line)
-   [Fuzzy completion for bash and zsh](https://github.com/junegunn/fzf#fuzzy-completion-for-bash-and-zsh)
    -   [Files and directories](https://github.com/junegunn/fzf#files-and-directories)
    -   [Process IDs](https://github.com/junegunn/fzf#process-ids)
    -   [Host names](https://github.com/junegunn/fzf#host-names)
    -   [Environment variables / Aliases](https://github.com/junegunn/fzf#environment-variables--aliases)
    -   [Settings](https://github.com/junegunn/fzf#settings)
    -   [Supported commands](https://github.com/junegunn/fzf#supported-commands)
    -   [Custom fuzzy completion](https://github.com/junegunn/fzf#custom-fuzzy-completion)
-   [Vim plugin](https://github.com/junegunn/fzf#vim-plugin)
-   [Advanced topics](https://github.com/junegunn/fzf#advanced-topics)
    -   [Performance](https://github.com/junegunn/fzf#performance)
    -   [Executing external programs](https://github.com/junegunn/fzf#executing-external-programs)
    -   [Reloading the candidate list](https://github.com/junegunn/fzf#reloading-the-candidate-list)
        -   [1\. Update the list of processes by pressing CTRL-R](https://github.com/junegunn/fzf#1-update-the-list-of-processes-by-pressing-ctrl-r)
        -   [2\. Switch between sources by pressing CTRL-D or CTRL-F](https://github.com/junegunn/fzf#2-switch-between-sources-by-pressing-ctrl-d-or-ctrl-f)
        -   [3\. Interactive ripgrep integration](https://github.com/junegunn/fzf#3-interactive-ripgrep-integration)
    -   [Preview window](https://github.com/junegunn/fzf#preview-window)
-   [Tips](https://github.com/junegunn/fzf#tips)
    -   [Respecting `.gitignore`](https://github.com/junegunn/fzf#respecting-gitignore)
    -   [Fish shell](https://github.com/junegunn/fzf#fish-shell)
-   [Related projects](https://github.com/junegunn/fzf#related-projects)
-   [License](https://github.com/junegunn/fzf#license)

## Installation

fzf project consists of the following components:

-   `fzf` executable
-   `fzf-tmux` script for launching fzf in a tmux pane
-   Shell extensions
    -   Key bindings (`CTRL-T`, `CTRL-R`, and `ALT-C`) (bash, zsh, fish)
    -   Fuzzy auto-completion (bash, zsh)
-   Vim/Neovim plugin

You can [download fzf executable](https://github.com/junegunn/fzf/releases) alone if you don't need the extra stuff.

### Using Homebrew

You can use [Homebrew](https://brew.sh/) (on macOS or Linux) to install fzf.

brew install fzf

# To install useful key bindings and fuzzy completion:
$(brew --prefix)/opt/fzf/install

fzf is also available [via MacPorts](https://github.com/macports/macports-ports/blob/master/sysutils/fzf/Portfile): `sudo port install fzf`

### Using git

Alternatively, you can "git clone" this repository to any directory and run [install](https://github.com/junegunn/fzf/blob/master/install) script.

git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install

### Using Linux package managers

Package Manager

Linux Distribution

Command

APK

Alpine Linux

`sudo apk add fzf`

APT

Debian 9+/Ubuntu 19.10+

`sudo apt-get install fzf`

Conda

`conda install -c conda-forge fzf`

DNF

Fedora

`sudo dnf install fzf`

Nix

NixOS, etc.

`nix-env -iA nixpkgs.fzf`

Pacman

Arch Linux

`sudo pacman -S fzf`

pkg

FreeBSD

`pkg install fzf`

pkgin

NetBSD

`pkgin install fzf`

pkg\_add

OpenBSD

`pkg_add fzf`

XBPS

Void Linux

`sudo xbps-install -S fzf`

Zypper

openSUSE

`sudo zypper install fzf`

> ⚠️ **Key bindings (CTRL-T / CTRL-R / ALT-C) and fuzzy auto-completion may not be enabled by default.**
> 
> Refer to the package documentation for more information. (e.g. `apt-cache show fzf`)

[![Packaging status](https://camo.githubusercontent.com/54cacbe83155b7e8dd863271ef5528ab00475189e1aac87541d6afce994b75d4/68747470733a2f2f7265706f6c6f67792e6f72672f62616467652f766572746963616c2d616c6c7265706f732f667a662e737667)](https://repology.org/project/fzf/versions)

### Windows

Pre-built binaries for Windows can be downloaded [here](https://github.com/junegunn/fzf/releases). fzf is also available via [Chocolatey](https://chocolatey.org/packages/fzf) and [Scoop](https://github.com/ScoopInstaller/Main/blob/master/bucket/fzf.json):

Package manager

Command

Chocolatey

`choco install fzf`

Scoop

`scoop install fzf`

Known issues and limitations on Windows can be found on [the wiki page](https://github.com/junegunn/fzf/wiki/Windows).

### As Vim plugin

If you use [vim-plug](https://github.com/junegunn/vim-plug), add this line to your Vim configuration file:

Plug 'junegunn/fzf', { 'do': { \-\> fzf#install() } }

`fzf#install()` makes sure that you have the latest binary, but it's optional, so you can omit it if you use a plugin manager that doesn't support hooks.

For more installation options, see [README-VIM.md](https://github.com/junegunn/fzf/blob/master/README-VIM.md).

## Upgrading fzf

fzf is being actively developed, and you might want to upgrade it once in a while. Please follow the instruction below depending on the installation method used.

-   git: `cd ~/.fzf && git pull && ./install`
-   brew: `brew update; brew upgrade fzf`
-   macports: `sudo port upgrade fzf`
-   chocolatey: `choco upgrade fzf`
-   vim-plug: `:PlugUpdate fzf`

## Building fzf

See [BUILD.md](https://github.com/junegunn/fzf/blob/master/BUILD.md).

## Usage

fzf will launch interactive finder, read the list from STDIN, and write the selected item to STDOUT.

find \* -type f | fzf \> selected

Without STDIN pipe, fzf will use find command to fetch the list of files excluding hidden ones. (You can override the default command with `FZF_DEFAULT_COMMAND`)

#### Using the finder

-   `CTRL-K` / `CTRL-J` (or `CTRL-P` / `CTRL-N`) to move cursor up and down
-   `Enter` key to select the item, `CTRL-C` / `CTRL-G` / `ESC` to exit
-   On multi-select mode (`-m`), `TAB` and `Shift-TAB` to mark multiple items
-   Emacs style key bindings
-   Mouse: scroll, click, double-click; shift-click and shift-scroll on multi-select mode

#### Layout

fzf by default starts in fullscreen mode, but you can make it start below the cursor with `--height` option.

Also, check out `--reverse` and `--layout` options if you prefer "top-down" layout instead of the default "bottom-up" layout.

vim $(fzf --height 40% --reverse)

You can add these options to `$FZF_DEFAULT_OPTS` so that they're applied by default. For example,

export FZF\_DEFAULT\_OPTS='\--height 40% --layout=reverse --border'

#### Search syntax

Unless otherwise specified, fzf starts in "extended-search mode" where you can type in multiple search terms delimited by spaces. e.g. `^music .mp3$ sbtrkt !fire`

Token

Match type

Description

`sbtrkt`

fuzzy-match

Items that match `sbtrkt`

`'wild`

exact-match (quoted)

Items that include `wild`

`^music`

prefix-exact-match

Items that start with `music`

`.mp3$`

suffix-exact-match

Items that end with `.mp3`

`!fire`

inverse-exact-match

Items that do not include `fire`

`!^music`

inverse-prefix-exact-match

Items that do not start with `music`

`!.mp3$`

inverse-suffix-exact-match

Items that do not end with `.mp3`

If you don't prefer fuzzy matching and do not wish to "quote" every word, start fzf with `-e` or `--exact` option. Note that when `--exact` is set, `'`\-prefix "unquotes" the term.

A single bar character term acts as an OR operator. For example, the following query matches entries that start with `core` and end with either `go`, `rb`, or `py`.

#### Environment variables

-   `FZF_DEFAULT_COMMAND`
    -   Default command to use when input is tty
    -   e.g. `export FZF_DEFAULT_COMMAND='fd --type f'`
    -   > ⚠️ This variable is not used by shell extensions due to the slight difference in requirements.
        > 
        > (e.g. `CTRL-T` runs `$FZF_CTRL_T_COMMAND` instead, `vim **<tab>` runs `_fzf_compgen_path()`, and `cd **<tab>` runs `_fzf_compgen_dir()`)
        > 
        > The available options are described later in this document.
        
-   `FZF_DEFAULT_OPTS`
    -   Default options
    -   e.g. `export FZF_DEFAULT_OPTS="--layout=reverse --inline-info"`

#### Options

See the man page (`man fzf`) for the full list of options.

#### Demo

If you learn by watching videos, check out this screencast by [@samoshkin](https://github.com/samoshkin) to explore `fzf` features.

 [![](https://camo.githubusercontent.com/9dc9e9cf812691c301505f94718c8be64651aaf24e1e09a41484f4b19249197d/68747470733a2f2f692e696d6775722e636f6d2f767447386f6c452e706e67)](https://www.youtube.com/watch?v=qgG5Jhi_Els "fzf - command-line fuzzy finder") 

## Examples

-   [Wiki page of examples](https://github.com/junegunn/fzf/wiki/examples)
    -   _Disclaimer: The examples on this page are maintained by the community and are not thoroughly tested_
-   [Advanced fzf examples](https://github.com/junegunn/fzf/blob/master/ADVANCED.md)

## `fzf-tmux` script

[fzf-tmux](https://github.com/junegunn/fzf/blob/master/bin/fzf-tmux) is a bash script that opens fzf in a tmux pane.

# usage: fzf-tmux \[LAYOUT OPTIONS\] \[--\] \[FZF OPTIONS\]

# See available options
fzf-tmux --help

# select git branches in horizontal split below (15 lines)
git branch | fzf-tmux -d 15

# select multiple words in vertical split on the left (20% of screen width)
cat /usr/share/dict/words | fzf-tmux -l 20% --multi --reverse

It will still work even when you're not on tmux, silently ignoring `-[pudlr]` options, so you can invariably use `fzf-tmux` in your scripts.

Alternatively, you can use `--height HEIGHT[%]` option not to start fzf in fullscreen mode.

## Key bindings for command-line

The install script will setup the following key bindings for bash, zsh, and fish.

-   `CTRL-T` - Paste the selected files and directories onto the command-line
    -   Set `FZF_CTRL_T_COMMAND` to override the default command
    -   Set `FZF_CTRL_T_OPTS` to pass additional options
-   `CTRL-R` - Paste the selected command from history onto the command-line
    -   If you want to see the commands in chronological order, press `CTRL-R` again which toggles sorting by relevance
    -   Set `FZF_CTRL_R_OPTS` to pass additional options
-   `ALT-C` - cd into the selected directory
    -   Set `FZF_ALT_C_COMMAND` to override the default command
    -   Set `FZF_ALT_C_OPTS` to pass additional options

If you're on a tmux session, you can start fzf in a tmux split-pane or in a tmux popup window by setting `FZF_TMUX_OPTS` (e.g. `-d 40%`). See `fzf-tmux --help` for available options.

More tips can be found on [the wiki page](https://github.com/junegunn/fzf/wiki/Configuring-shell-key-bindings).

## Fuzzy completion for bash and zsh

#### Files and directories

Fuzzy completion for files and directories can be triggered if the word before the cursor ends with the trigger sequence, which is by default `**`.

-   `COMMAND [DIRECTORY/][FUZZY_PATTERN]**<TAB>`

# Files under the current directory
# - You can select multiple items with TAB key
vim \*\*<TAB\>

# Files under parent directory
vim ../\*\*<TAB\>

# Files under parent directory that match \`fzf\`
vim ../fzf\*\*<TAB\>

# Files under your home directory
vim ~/\*\*<TAB\>

# Directories under current directory (single-selection)
cd \*\*<TAB\>

# Directories under ~/github that match \`fzf\`
cd ~/github/fzf\*\*<TAB\>

#### Process IDs

Fuzzy completion for PIDs is provided for kill command. In this case, there is no trigger sequence; just press the tab key after the kill command.

# Can select multiple processes with <TAB> or <Shift-TAB> keys
kill -9 <TAB\>

#### Host names

For ssh and telnet commands, fuzzy completion for hostnames is provided. The names are extracted from /etc/hosts and ~/.ssh/config.

ssh \*\*<TAB\>
telnet \*\*<TAB\>

#### Environment variables / Aliases

unset \*\*<TAB\>
export \*\*<TAB\>
unalias \*\*<TAB\>

#### Settings

# Use ~~ as the trigger sequence instead of the default \*\*
export FZF\_COMPLETION\_TRIGGER='~~'

# Options to fzf command
export FZF\_COMPLETION\_OPTS='\--border --info=inline'

# Use fd (https://github.com/sharkdp/fd) instead of the default find
# command for listing path candidates.
# - The first argument to the function ($1) is the base path to start traversal
# - See the source code (completion.{bash,zsh}) for the details.
\_fzf\_compgen\_path() {
  fd --hidden --follow --exclude ".git" . "$1"
}

# Use fd to generate the list for directory completion
\_fzf\_compgen\_dir() {
  fd --type d --hidden --follow --exclude ".git" . "$1"
}

# (EXPERIMENTAL) Advanced customization of fzf options via \_fzf\_comprun function
# - The first argument to the function is the name of the command.
# - You should make sure to pass the rest of the arguments to fzf.
\_fzf\_comprun() {
  local command=$1
  shift

  case "$command" in
    cd)           fzf "$@" --preview 'tree -C {} | head -200' ;;
    export|unset) fzf "$@" --preview "eval 'echo \\$'{}" ;;
    ssh)          fzf "$@" --preview 'dig {}' ;;
    \*)            fzf "$@" ;;
  esac
}

#### Supported commands

On bash, fuzzy completion is enabled only for a predefined set of commands (`complete | grep _fzf` to see the list). But you can enable it for other commands as well by using `_fzf_setup_completion` helper function.

# usage: \_fzf\_setup\_completion path|dir|var|alias|host COMMANDS...
\_fzf\_setup\_completion path ag git kubectl
\_fzf\_setup\_completion dir tree

#### Custom fuzzy completion

_**(Custom completion API is experimental and subject to change)**_

For a command named _"COMMAND"_, define `_fzf_complete_COMMAND` function using `_fzf_complete` helper.

# Custom fuzzy completion for "doge" command
#   e.g. doge \*\*<TAB>
\_fzf\_complete\_doge() {
  \_fzf\_complete --multi --reverse --prompt="doge> " -- "$@" < <(
 echo very
 echo wow
 echo such
 echo doge
 )
}

-   The arguments before `--` are the options to fzf.
-   After `--`, simply pass the original completion arguments unchanged (`"$@"`).
-   Then, write a set of commands that generates the completion candidates and feed its output to the function using process substitution (`< <(...)`).

zsh will automatically pick up the function using the naming convention but in bash you have to manually associate the function with the command using the `complete` command.

\[ \-n "$BASH" \] && complete -F \_fzf\_complete\_doge -o default -o bashdefault doge

If you need to post-process the output from fzf, define `_fzf_complete_COMMAND_post` as follows.

\_fzf\_complete\_foo() {
  \_fzf\_complete --multi --reverse --header-lines=3 -- "$@" < <(
 ls -al
 )
}

\_fzf\_complete\_foo\_post() {
  awk '{print $NF}'
}

\[ \-n "$BASH" \] && complete -F \_fzf\_complete\_foo -o default -o bashdefault foo

## Vim plugin

See [README-VIM.md](https://github.com/junegunn/fzf/blob/master/README-VIM.md).

## Advanced topics

### Performance

fzf is fast and is [getting even faster](https://junegunn.kr/images/fzf-0.17.0.png). Performance should not be a problem in most use cases. However, you might want to be aware of the options that affect performance.

-   `--ansi` tells fzf to extract and parse ANSI color codes in the input, and it makes the initial scanning slower. So it's not recommended that you add it to your `$FZF_DEFAULT_OPTS`.
-   `--nth` makes fzf slower because it has to tokenize each line.
-   `--with-nth` makes fzf slower as fzf has to tokenize and reassemble each line.
-   If you absolutely need better performance, you can consider using `--algo=v1` (the default being `v2`) to make fzf use a faster greedy algorithm. However, this algorithm is not guaranteed to find the optimal ordering of the matches and is not recommended.

### Executing external programs

You can set up key bindings for starting external processes without leaving fzf (`execute`, `execute-silent`).

# Press F1 to open the file with less without leaving fzf
# Press CTRL-Y to copy the line to clipboard and aborts fzf (requires pbcopy)
fzf --bind 'f1:execute(less -f {}),ctrl-y:execute-silent(echo {} | pbcopy)+abort'

See _KEY BINDINGS_ section of the man page for details.

### Reloading the candidate list

By binding `reload` action to a key or an event, you can make fzf dynamically reload the candidate list. See [https://github.com/junegunn/fzf/issues/1750](https://github.com/junegunn/fzf/issues/1750) for more details.

#### 1\. Update the list of processes by pressing CTRL-R

FZF\_DEFAULT\_COMMAND='ps -ef' \\
  fzf --bind 'ctrl-r:reload($FZF\_DEFAULT\_COMMAND)' \\
      --header 'Press CTRL-R to reload' --header-lines=1 \\
      --height=50% --layout=reverse

#### 2\. Switch between sources by pressing CTRL-D or CTRL-F

FZF\_DEFAULT\_COMMAND='find . -type f' \\
  fzf --bind 'ctrl-d:reload(find . -type d),ctrl-f:reload($FZF\_DEFAULT\_COMMAND)' \\
      --height=50% --layout=reverse

#### 3\. Interactive ripgrep integration

The following example uses fzf as the selector interface for ripgrep. We bound `reload` action to `change` event, so every time you type on fzf, the ripgrep process will restart with the updated query string denoted by the placeholder expression `{q}`. Also, note that we used `--disabled` option so that fzf doesn't perform any secondary filtering.

INITIAL\_QUERY=""
RG\_PREFIX="rg --column --line-number --no-heading --color=always --smart-case "
FZF\_DEFAULT\_COMMAND="$RG\_PREFIX '$INITIAL\_QUERY'" \\
  fzf --bind "change:reload:$RG\_PREFIX {q} || true" \\
      --ansi --disabled --query "$INITIAL\_QUERY" \\
      --height=50% --layout=reverse

If ripgrep doesn't find any matches, it will exit with a non-zero exit status, and fzf will warn you about it. To suppress the warning message, we added `|| true` to the command, so that it always exits with 0.

See ["Using fzf as interative Ripgrep launcher"](https://github.com/junegunn/fzf/blob/master/ADVANCED.md#using-fzf-as-interative-ripgrep-launcher) for a fuller example with preview window options.

### Preview window

When the `--preview` option is set, fzf automatically starts an external process with the current line as the argument and shows the result in the split window. Your `$SHELL` is used to execute the command with `$SHELL -c COMMAND`. The window can be scrolled using the mouse or custom key bindings.

# {} is replaced with the single-quoted string of the focused line
fzf --preview 'cat {}'

Preview window supports ANSI colors, so you can use any program that syntax-highlights the content of a file, such as [Bat](https://github.com/sharkdp/bat) or [Highlight](http://www.andre-simon.de/doku/highlight/en/highlight.php):

fzf --preview 'bat --style=numbers --color=always --line-range :500 {}'

You can customize the size, position, and border of the preview window using `--preview-window` option, and the foreground and background color of it with `--color` option. For example,

fzf --height 40% --layout reverse --info inline --border \\
    --preview 'file {}' --preview-window up,1,border-horizontal \\
    --color 'fg:#bbccdd,fg+:#ddeeff,bg:#334455,preview-bg:#223344,border:#778899'

See the man page (`man fzf`) for the full list of options.

For more advanced examples, see [Key bindings for git with fzf](https://junegunn.kr/2016/07/fzf-git/) ([code](https://gist.github.com/junegunn/8b572b8d4b5eddd8b85e5f4d40f17236)).

___

Since fzf is a general-purpose text filter rather than a file finder, **it is not a good idea to add `--preview` option to your `$FZF_DEFAULT_OPTS`**.

# \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
# \*\* DO NOT DO THIS! \*\*
# \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
export FZF\_DEFAULT\_OPTS='\--preview "bat --style=numbers --color=always --line-range :500 {}"'

# bat doesn't work with any input other than the list of files
ps -ef | fzf
seq 100 | fzf
history | fzf

## Tips

#### Respecting `.gitignore`

You can use [fd](https://github.com/sharkdp/fd), [ripgrep](https://github.com/BurntSushi/ripgrep), or [the silver searcher](https://github.com/ggreer/the_silver_searcher) instead of the default find command to traverse the file system while respecting `.gitignore`.

# Feed the output of fd into fzf
fd --type f | fzf

# Setting fd as the default source for fzf
export FZF\_DEFAULT\_COMMAND='fd --type f'

# Now fzf (w/o pipe) will use fd instead of find
fzf

# To apply the command to CTRL-T as well
export FZF\_CTRL\_T\_COMMAND="$FZF\_DEFAULT\_COMMAND"

If you want the command to follow symbolic links and don't want it to exclude hidden files, use the following command:

export FZF\_DEFAULT\_COMMAND='fd --type f --hidden --follow --exclude .git'

#### Fish shell

`CTRL-T` key binding of fish, unlike those of bash and zsh, will use the last token on the command-line as the root directory for the recursive search. For instance, hitting `CTRL-T` at the end of the following command-line

will list all files and directories under `/var/`.

When using a custom `FZF_CTRL_T_COMMAND`, use the unexpanded `$dir` variable to make use of this feature. `$dir` defaults to `.` when the last token is not a valid directory. Example:

set -g FZF\_CTRL\_T\_COMMAND "command find -L \\$dir -type f 2> /dev/null | sed '1d; s#^\\./##'"

## Related projects

[https://github.com/junegunn/fzf/wiki/Related-projects](https://github.com/junegunn/fzf/wiki/Related-projects)

## [License](https://github.com/junegunn/fzf/blob/master/LICENSE)

The MIT License (MIT)

Copyright (c) 2013-2021 Junegunn Choi