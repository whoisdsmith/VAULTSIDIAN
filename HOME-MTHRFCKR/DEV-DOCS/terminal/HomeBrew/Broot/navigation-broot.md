When you start broot, the current directory is displayed, with most often some directories open and some lines truncated, in order to fit the available height.

The first line is called the root, and is currently selected.

From here you may navigate using the following keys:

-   ↓ or ↑ : select the next or previous line
-   ctrl← or ctrl→ : focus (or open) a panel to the left or to the right
-   ⏎ on a file : open the file using xdg-open (or your OS equivalent)
-   alt⏎ on a file : leave broot and open the file using xdg-open
-   ⏎ on a directory : focus the directory (i.e. make it the new root)
-   alt⏎ on a directory : leave broot and `cd` the shell to that directory.
-   ⏎ on the first line : goes up one level (focus the parent directory)
-   esc gets you back to the previous state (or leave broot if there's none)
-   ? brings you to the help screen

There are also a few more shortcuts:

-   you can quit with Ctrlq
-   you can select a line with a mouse click
-   you can open a line with a mouse double-click

and you can define your own [shortcuts](https://dystroy.org/broot/conf_verbs/#shortcuts-and-verb-search) or triggering [keyboard keys](https://dystroy.org/broot/conf_verbs/#keyboard-key).

The best way to navigate is by filtering the tree.

This is done by typing a few letters.

The pattern filters the tree while you type. It's interpreted in a fuzzy way so that you don't have to type all the letters or even consecutive letters. The best match is automatically selected.

For example:

![search hel](https://dystroy.org/broot/img/20190305-search-hel.png)

Hitting esc clears the current pattern.

If there's a `/` before or after the pattern, it's interpreted as a regular expression.

For example `/pat+ern` would match `"patern.zip"` or `"some_patttern.rar"` but not `"pATTern"`.

If you want the regex to be case insensitive, add the `i` flag: `/pat+ern/i`.

To display only files containing `"memmap"`, type `c/memmap`:

![content](https://dystroy.org/broot/img/20200620-content-search.png)

(as the search is displayed in real time you'll usually stop as soon as you have the right matches)

Simple patterns can be composed with the `!`, `&` and `|` operators.

For example, if you don't want to see files whose name ends in `"rs"`, you may type `!/rs$` (it's the negation of the `/rs$` regular expression).

And if you want to see all files containing `"pattern"` but not the rust ones, you'll type `!rs&c/pattern`:

![composite](https://dystroy.org/broot/img/20200620-composite-notrs.png)

If you want to know more about the exact pattern syntax, see [reference](https://dystroy.org/broot/input/#the-filtering-pattern).

When you search in broot in a very big directory on a slow disk, broot doesn't always look at all files. It stops when it found enough matches and then rates those matches.

If you think there might be a better match, hidden deeper, you may require a _total search_, which is a search which look at _all_ files. This is done using the `:total_search` verb, which may be triggered with the Ctrl\-S key combination (you may redefine it, see [configuration](https://dystroy.org/broot/conf_file/#keyboard-key)).

As for other searches, it's interrupted as soon as you type anything.

Flags are displayed at the bottom right of the panel, showing the settings regarding hidden files and .gitignore rules.

![flags](https://dystroy.org/broot/img/20190101-flags.png)

Initially, broot doesn't show files whose name starts with a dot, or files declared as ignored by a `.gitignore` file. Permissions and file sizes aren't shown.

This behavior is tuned with several toggles.

name

shortcut

key

description

toggle\_counts

counts

toggle showing deep counts of files in directories

toggle\_dates

dates

toggle showing last modified dates (deep computed)

toggle\_files

files

toggle showing files (or just folders)

toggle\_git\_file\_info

gf

toggle display of git file information

toggle\_git\_ignore

gi

alti

toggle use of .gitignore

toggle\_hidden

h

alth

toggle showing hidden files

toggle\_perm

perm

toggle showing file permissions (Unix only)

toggle\_sizes

sizes

toggle showing sizes

toggle\_trim\_root

t

toggle removing nodes at first level too

To apply one, type a space (or `:`), then the start of its shortcut, then hit ⏎.

For example typing `:s` then enter will show file and directory sizes.

Note

The displayed size on Unix is the space the file takes on disk, that is the number of blocks multiplied by the size of a block. If a file is sparse, a little 's' is displayed next to the size.

Those toggles may also be defined with [launch options](https://dystroy.org/broot/launch) and the [default\_flags preference](https://dystroy.org/broot/conf_file/#default-flags). And you can see them in the application with ?.

Other than executing a command leaving broot, there are several ways to quit:

-   if the current root is selected, just hit `enter`
-   hit ctrl+Q
-   type `:q` or `space` `q` then `enter`