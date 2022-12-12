# Launch - Broot

> ## Excerpt
> When the installation is complete, you may start broot with either

---
When the installation is [complete](https://dystroy.org/broot/install/#installation-completion-the-br-shell-function), you may start broot with either

```
broot
```

or

```
br
```

If your shell is compatible, you should prefer `br` which enables some features like `cd` from broot.

You can pass as argument the path you want to see, for example

```
br ~
```

Broot renders on `stderr` and can be ran in a subshell, which means you can also (on Unix) do things like

```
my_unix_command "$(broot some_dir)"
```

and quit broot with `:pp` on the selected path. But most often you'll more conveniently simply add your command (and maybe a shortcut) to the [config file](https://dystroy.org/broot/conf_file/#verbs-shortcuts-and-keys).

**broot** and **br** can be passed as argument the path to display.

They also accept a few other arguments which you can view with `br --help`.

Most of them are display toggles, which may be useful when aliasing the function but which are accessible from inside the application anyway.

Some of them are a little special, though, and are explained below:

## the `--outcmd` launch argument

Some external commands can't be executed from a program.

This is especially the case of `cd`, which isn't a program but a shell function. In order to have any useful effect, it must be called from the parent shell, the one from which broot was launched, and a shell which isn't accessible from broot.

The trick to enable broot to `cd` your shell when you do `alt-enter` is the following one:

-   **br** is a shell function. It creates a temp file whose path it gives as argument to **broot** using `--outcmd`
-   when you do `alt-enter`, **broot** writes `cd your-selected-path` in this file, then quits
-   **br** reads the file, deletes it, then evaluates the command

Most users have no reason to use `--outcmd` on their own, but it can still be used to write an alternative to **br** or to port it to shells which aren't currently supported.

## the `--cmd` launch argument

This argument lets you pass commands to broot. Those commands are executed exactly like any command you would type yourself in the application.

Commands must be separated. The default separator is the semicolon (`;`) but another separator may be provided using the `BROOT_CMD_SEPARATOR` environment variable (the separator may be several characters long if needed).

Broot waits for the end of execution of every command.

For example if you launch

```
br --cmd cow /
```

Then broot is launched in the `/` directory and there's a filter typed for you.

If you do

```
br --cmd "/^vache;:p"
```

Then broot looks for a file whose name starts with "vache" and focus its parent.

If you do

```
br -c "/mucca$;:cd"
```

then broot searches for a file whose name ends with "mucca", and `cd` to the closest directory, leaving you on the shell, in your new directory (you may not have the time to notice the broot GUI was displayed).

If you do

```
BROOT_CMD_SEPARATOR=@ broot -c ":gi@target@:pp"
```

then broot toggles the git\_ignore filter, searches for `target` then prints the selection path on stdout (when doing it in my broot repository, I get `/home/dys/dev/broot/target`).

The `--cmd` argument may be the basis for many of your own shell functions or programs.
