Those common file operations may be discovered elsewhere in the site, or in the help screen in Broot.

This page is a cheat sheet gathering them in one place.

It focuses on the default settings, on the basis that you change the settings only after you understood the feature.

I'll assume here you know the basics of command line file operations. Broot doesn't hide the operations, it makes them easier and faster to type and shows you immediately the result but you won't be able to do them if you don't know what a `cp` or a `mkdir` does.

For each command here, don't forget you can hit esc to remove it. It's the fast way to cance.

Note

To be easier to read, this page uses `:` to start verbs but a space is equivalent and is often more convenient to type.

Note

Most screenshots here don't feature a filtering pattern (i.e. the part before the first space or colon) but you never need to remove your filter to execute your file operation. Typing a pattern is usually the fastest way to select the file you want.

A `cd` here means changing the current directory in the shell from which broot was launched.

This is done either by hitting altenter or by issuing the `:cd` verb.

It needs broot to be launched with the [`br` shell function](https://dystroy.org/broot/install-br).

This operation only exists on unix-like systems.

The built in `chmod` command takes as argument the mode modifier.

For example, to make the selected file executable, you type `:ch` then a space or tab, then `+x`.

![chmod](https://dystroy.org/broot/img/20210603-chmod.png)

After having checked the status line, you hit enter and the modification is done.

When you're not sure about the current mode, you may show them before starting the operation. This is done either

-   by starting broot with the `-p` command line argument
-   by hitting `:perm` in broot

Here's how the same `chmod` operation would look like with the mode displayed:

![chmod](https://dystroy.org/broot/img/20210603-chmod-perm.png)

## with one panel

Select the file or directory you want to copy, type `:cp` then a tab or a space, then the destination path.

Don't hesitate to hit the tab key while typing your path to get completion. Broot accepts and solves relative paths:

![file op](https://dystroy.org/broot/img/20210603-cp.png)

After having checked the status line, you hit enter and the copy is done.

## with two panels

When you do changes involving distant location, you may want to see both trees side to side. This is done by [opening two panels](https://dystroy.org/broot/panels).

When using two panels, no argument is needed for the copy. The verb to use is `:cpp`:

![file op](https://dystroy.org/broot/img/20210603-cpp.png)

As there's no argument, you may [define a key binding](https://dystroy.org/broot/conf_verbs#keyboard-key) for cpp in your configuration if you like this operation.

The default configuration assumes the `$EDITOR` env variable is set. If it isn't and you can't set it, you should edit the `create` verb in the [configuration file](https://dystroy.org/broot/conf_file).

The desired parent being selected, type `:cr` then hit tab or a space, then the name of the new file:

![file op](https://dystroy.org/broot/img/20210603-cr.png)

On enter you'll enter your favourite text editor and you'll be back to broot when quitting it.

Select the desired parent, type `:md` then hit a space or a tab, then enter the name of the new directory and hit enter.

You may type several slash separated elements as the command will contain the `-p` flag:

![file op](https://dystroy.org/broot/img/20210603-md.png)

## the selected file or directory

Select a file, type `:rm`

![file op](https://dystroy.org/broot/img/20210603-rm.png)

Check the status line then hit enter:

## with staging

Let's assume you want to remove a lot of files and directories because your disk is full.

In such a case, you start broot in "whale hunt" mode, with `br -w` to have files and directories sorted by size.

![file op](https://dystroy.org/broot/img/20210603-br-w.png)

Instead of removing files one per one, you may want to "stage" them, that is to add them to the staging area where they're counted, summed, and where you'll remove them in one operation at the end.

You stage a file (and display the staging area) with the ctrlg shortcut:

![file op](https://dystroy.org/broot/img/20210603-br-w-stage.png)

The total size of the staging area is displayed on top (here "8.1G").

(when not doing screenshots for a website, I suggest you use a bigger console, so it's less crowded, but as you see broot stays usable in a tiny one)

When you ready to remove everything, you go to the staging area with ctrlright then type `:rm`:

![file op](https://dystroy.org/broot/img/20210603-br-w-stage-rm.png)

You finish by hitting enter.

The default configuration assumes the `$EDITOR` env variable is set. If it isn't and you can't set it, you should edit the `edit` verb in the [configuration file](https://dystroy.org/broot/conf_file).

Select the file you want to edit, type `:e` then hit enter.

![file op](https://dystroy.org/broot/img/20210603-e.png)

As there's no argument, you may [define a key binding](https://dystroy.org/broot/conf_verbs#keyboard-key).

You may have noticed the `+0`. If you're in a preview on a specific line, or you [searched on file content](https://dystroy.org/broot/navigation#file-content-searches), the file may be directly open on that line with this standard argument :

![file op](https://dystroy.org/broot/img/20210603-e-line.png)

Here, on enter, we'd go to line 13 where is the first occurence of "lazy-" in this file.

(you may change the configuration if your editor has a different syntax)

_Note that there's also a [rename](https://dystroy.org/broot/file-operations/#rename) which is usually better if you only want to change the name._

## with one panel

Select the file or directory you want to copy, type `:mv` then a tab or a space, then the destination path.

Don't hesitate to hit the tab key while typing your path to get completion. Broot accepts and solves relative paths:

![file op](https://dystroy.org/broot/img/20210603-mv.png)

After having checked the status line, you hit enter and the copy is done.

## with two panels

When you do changes involving distant location, you may want to see both trees side to side. This is done by [opening two panels](https://dystroy.org/broot/panels).

When using two panels, no argument is needed for the copy. The verb to use is `:mvp`:

![file op](https://dystroy.org/broot/img/20210603-mvp.png)

As there's no argument, you may [define a key binding](https://dystroy.org/broot/conf_verbs#keyboard-key) for mvp in your configuration if you like this operation.

When a file (not a directory) is selected and you hit enter, the `:open_stay` internal is executed, which calls the standard file opening solution of your system and doesn't close Broot. For example on a desktop linux, this calls a variant of xdg-open which in turns will choose an application using the file's extension.

When your system doesn't know how to open files (for example on server linux with no windowing solution), this may be a problem and you can [change this behavior](https://dystroy.org/broot/tricks#change-standard-file-opening).

If all you want is to change part of the name of a file, perhaps its extension, the `:rename` verb is ideal.

It's mapped by default to F2.

Just hitting the trigger key prefills the input with the command with the name as argument.

You only have to edit this name then hit enter.

![file op](https://dystroy.org/broot/img/20210603-rename.png)