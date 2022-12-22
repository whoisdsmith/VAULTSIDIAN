The most important part of broot configuration is the `verbs` sections, which let you define new commands or shortcuts.

You can define a new verb in the configuration file inside the `verbs` list.

HjsonTOML

```
{
    invocation: edit
    key: F2
    shortcut: e
    apply_to: file
    external: "nvim {file}"
    leave_broot: false
}
```

The possible attributes are:

name

default

role

invocation

how the verb is called by the user, with placeholders for arguments

internal

execution, when your verb is based on a predefined broot verb

external

execution, when your verb is based on an external command

cmd

a semicolon sequence to execute, similar to an argument you pass to `--cmd`

key

a keyboard key triggering execution

keys

several keyboard shortcuts triggering execution (if you want to have the choice)

shortcut

an alternate way to call the verb (without the arguments part)

leave\_broot

`true`

whether to quit broot on execution

from\_shell

`false`

whether the verb must be executed from the parent shell (needs `br`). As this is executed after broot closed, this isn't compatible with `leave_broot = false`

apply\_to

the type of selection this verb applies to, may be `"file"`, `"directory"` or `"any"`. You may declare two verbs with the same key if the first one applies to only files or only directories

working\_dir

the working directory of the external application, for example `"{directory}"` for the closest directory (the working dir isn't set if the directory doesn't exist)

set\_working\_dir

`false`

whether the working dir of the process must be set to the currently selected directory (it's equivalent to `workding_dir: "{directory}"`)

auto\_exec

`true`

whether to execute the verb as soon as it's key-triggered (instead of waiting for enter)

The execution is defined either by `internal`, `external` or `cmd` so a verb must have exactly one of those (for compatibility with older versions broot still accepts `execution` for `internal` or `external` and guesses which one it is).

Note

The `from_shell` attribute exists because some actions can't possibly be useful from a subshell. For example `cd` is a shell builtin which must be executed in the parent shell.

If you want broot, for example, to execute `xterm -e "nvim {file}"`, you may either escape the quotes as `\"` or use the array format to separate parts.

So the two following verb definitions are equivalent.

With escaping:

HjsonTOML

```
{
    invocation: xtv
    external: "xterm -e \"nvim {file}\""
}
```

With an array:

HjsonTOML

```
{
    invocation: xtv
    external: ["xterm" "-e" "nvim {file}"]
}
```

**broot** looks for the first token following a space or `:` and tries to find the verb you want.

-   If what you typed is exactly the shortcut or name of a verb, then this verb is selected: broot explains you what it would do if you were to type `enter`
-   If there's exactly one verb whose name or shortcut starts with the characters you typed, then it's selected
-   if there are several verbs whose name or shortcut start with the characters you typed, then broot waits for more
-   if no verb has a name or shortcut starting with those characters, broot tells you there's a problem

Knowing this algorithm, you may understand the point in the following definition:

TOML

```
[[verbs]]
invocation = "p"
internal = ":parent"
```

This verb is an alias to the internal builtin already available if you type `:parent`.

Its interest is that if you do `:p`, then `enter`, it is executed even while there are other verbs whose invocation pattern starts with a `p`.

Use shortcuts for verbs you frequently use.

The main keys you can use are

-   The function keys (for example F3)
-   Ctrl and Alt keys (for example ctrlT or alta)

It's possible to define a verb just to add a trigger key to an internal verb.

For example you could add those mappings:

HjsonTOML

```
verbs: [
    {
        invocation: "root"
        key: "F9"
        internal: ":focus /"
    }
    {
        invocation: "home"
        key: "ctrl-H"
        internal: ":focus ~"
    }
    {
        key: "alt-j"
        internal: ":line_down"
    }
    {
        invocation: "top"
        key: "F6"
        internal: ":select_first"
    }
    {
        invocation: "bottom"
        key: F7
        internal: ":select_last"
    }
    {
        invocation: "open"
        key: crtl-O
        internal: ":open_stay"
    }
    {
        invocation: "edit"
        keys: [ 
            F2
            ctrl-e
        ]
        shortcut: "e"
        external: "$EDITOR +{line} {file}"
        from_shell: true
    }
]
```

Then,

-   when doing altJ, you would move the selection down (notice we don't need an invocation)
-   when doing Ctrl-H, you would go to you user home (`~` when on linux),
-   you would open files (without closing broot) with ctrl-O,
-   F7 would select the last line of the tree,
-   and you'd switch to your favorite editor with F2

Beware that consoles intercept some possible keys. Many keyboard shortcuts aren't available, depending on your configuration. Some keys are also reserved in broot for some uses, for example the enter key always validate an input command if there's some. The Tab, delete, backspace, esc keys are reserved too.

## Verbs not leaving broot

If you set `leave_broot = false`, broot won't quit when executing your command, but it will update the tree.

This is useful for commands modifying the tree (like creating or moving files).

The execution of a verb can take one or several arguments.

For example it may be defined as `vi {file}̀`.

Some arguments are predefined in broot and depends on the current selection:

name

expanded to

`{file}`

complete path of the current selection

`{file-name}`

file name of the current selection

`{file-extension}`

file extension of the current selection (example `rs` for `main.rs`)

`{file-stem}`

file name of the current selection

`{file-dot-extension}`

dot and extension of the current selection (example `.rs` for `main.rs`) or the empty string if there's no extension

`{line}`

number of selected line in the previewed file

`{parent}`

complete path of the current selection's parent

`{directory}`

closest directory, either `{file}` or `{parent}`

`{other-panel-file}`

complete path of the current selection in the other panel

`{other-panel-parent}`

complete path of the current selection's parent in the other panel

`{other-panel-directory}`

closest directory, either `{file}` or `{parent}` in the other panel

`{root}`

current tree root (top of the displayed files tree)

Note

when you're in the help screen, `{file}` is the configuration file, while `{directory}` is the configuration directory.

But you may also define some arguments in the invocation pattern. For example:

HjsonTOML

```
{
    invocation: "mkdir {subpath}"
    external: "mkdir -p {directory}/{subpath}"
}
```

(the `mkdir` verb is standard so you don't have to write it in the configuration file)

In this case the subpath is read from what you type:

![md sub](https://dystroy.org/broot/img/20190306-md.png)

As you see, there's a space in this path, but it works. **broot** tries to determine when to wrap path in quotes and when to escape so that such a command correctly works.

It also normalizes the paths it finds which eases the use of relative paths:

![mv](https://dystroy.org/broot/img/20190306-mv.png)

Here's another example, where the invocation pattern defines two arguments by destructuring:

HjsonTOML

```
{
    invocation: "blop {name}\\.{type}"
    external: "mkdir {parent}/{type} && nvim {parent}/{type}/{name}.{type}"
    from_shell: true
}
```

And here's how it would look like:

![blop](https://dystroy.org/broot/img/20190306-blop.png)

Notice the `\\.` in the invocation pattern ? That's because it is interpreted as a regular expression (with just a shortcut for the easy case, enabling `{name}`).

The whole regular expression syntax may be useful for more complex rules. Let's say we don't want the type to contain dots, then we do this:

HjsonTOML

```
{
    invocation: "blop {name}\\.(?P<type>[^.]+)"
    external: "mkdir {parent}/{type} && nvim {parent}/{type}/{name}.{type}"
    from_shell: true
}
```

You can override the default behavior of broot by giving your verb the same shortcut or invocation than a default one.

Here's a list of internals: builtin actions you can add an alternate shortcut or keyboard key for:

invocation

default key

default shortcut

behavior / details

:back

Esc

\-

back to previous app state (see Usage page)

:cd

altenter

\-

leave broot and cd to the selected directory (needs the br shell function)

:chmod {args}

\-

\-

execute a chmod

:close\_preview

\-

\-

close the preview panel

:copy\_path

altc

\-

copy path

:cp {newpath}

\-

\-

copy the file or directory to the provided name

:help

F1

\-

open the help page. Help page can also be open with ?

:focus

enter

\-

set the selected directory the root of the displayed tree

:line\_down

↓

\-

scroll one line down or select the next line (can be used with an argument eg `:line_down 4`)

:line\_up

↑

\-

scroll one line up or select the previous line

:line\_down\_no\_cycle

\-

\-

same as line\_down, but doesn't cycle

:line\_up\_no\_cycle

\-

\-

same as line\_down, but doesn't cycle

:mkdir {subpath}

\-

md

create a directory

:mv {newpath}

\-

\-

move the file or directory to the provided path

:next\_match

tab

\-

select the next matching file

:open\_stay

enter

\-

open the selected file in the default OS opener, or focus the directory

:open\_preview

\-

\-

open the preview panel

:open\_leave

altenter

\-

open the selected file in the default OS opener and leave broot

:open\_stay\_filter

\-

\-

focus the directory but keeping the current filtering pattern

:page\_down

⇟

\-

scroll one page down

:page\_up

⇞

\-

scroll one page up

:parent

\-

\-

focus the parent directory

:print\_path

\-

pp

print path and leave broot

:print\_relative\_path

\-

pp

print relative path and leave broot

:print\_tree

\-

pt

print tree and leave broot

:quit

ctrlq

q

quit broot

:refresh

F5

\-

refresh the displayed tree and clears the directory sizes cache

:rm

\-

\-

remove the selected file or directory. To stay safe, don't define a keyboard key for this action

:select\_first

\-

\-

select the first line

:select\_last

\-

\-

select the last line

:sort\_by\_count

\-

\-

sort by count (only one level of the tree is displayed)

:sort\_by\_date

\-

\-

sort by date

:sort\_by\_size

\-

\-

sort by size

:toggle\_counts

\-

\-

toggle display of total counts of files per directory

:toggle\_dates

\-

\-

toggle display of last modified dates (looking for the most recently changed file, even deep)

:toggle\_device\_id

\-

\-

toggle display of device id (unix only)

:toggle\_files

\-

\-

toggle showing files (or just folders)

:toggle\_git\_ignore

\-

\-

toggle git ignore handling (auto, no or yes)

:toggle\_git\_file\_info

\-

\-

toggle display of git file information

:toggle\_git\_status

\-

\-

toggle showing only the file which would show up on `git status`

:toggle\_hidden

\-

\-

toggle display of hidden files (the ones whose name starts with a dot on linux)

:toggle\_perm

\-

\-

toggle display of permissions (not available on Windows)

:toggle\_preview

\-

\-

toggle display of the preview panel

:toggle\_sizes

\-

\-

toggle the size mode

:toggle\_trim\_root

\-

\-

toggle trimming of top level files in tree display

:toggle\_second\_tree

\-

\-

toggle displaying a second tree

:up\_tree

\-

\-

focus the parent of the current root

:stage

+

\-

add selection to staging area

:unstage

\-

\-

remove selection from staging area

:toggle\_stage

ctrlg

\-

add or remove selection to staging area

:clear\_stage

\-

cls

empty the staging area

:open\_staging\_area

\-

osa

open the staging area

:close\_staging\_area

\-

csa

close the staging area panel

:toggle\_staging\_area

\-

tsa

open/close the staging area panel

Note that

-   you can always call a verb with its default invocation, you don't _have_ to define a shortcut
-   verbs whose invocation needs an argument (like `{newpath}`) can't be triggered with just a keyboard key.

Some internal actions can be bound to a key shortcut but can't be called explicitly from the input because they directly act on the input field:

name

default binding

behavior

:input\_clear

empty the input,

:input\_del\_char\_left

delete

delete the char left of the cursor

:input\_del\_char\_below

suppr

delete the char left at the cursor's position

:input\_del\_word\_left

\-

delete the word left of the cursor

:input\_del\_word\_right

\-

delete the word right of the cursor

:input\_go\_to\_end

end

move the cursor to the end of input

:input\_go\_left

←

move the cursor to the left

:input\_go\_right

→

move the cursor to the right

:input\_go\_to\_start

home

move the cursor to the start of input

:input\_go\_word\_left

\-

move the cursor one word to the left

:input\_go\_word\_right

\-

move the cursor one word to the right

:input\_selection\_copy

\-

copy the selected part of the input into the selection

:input\_selection\_cut

\-

cut the selected part of the input into the selection

:input\_paste

\-

paste the clipboard content into the input

You may add this kind of shortcuts in the `verbs` section:

HjsonTOML

```
{ key: "alt-b", internal: ":input_go_word_left" }
{ key: "alt-f", internal: ":input_go_word_right" }
{ key: "alt-l", internal: ":input_del_word_left" }
{ key: "alt-r", internal: ":input_del_word_right" }
```

## Copy, Cut, Paste, in input

Pasting into input is bound to ctrlV but copying from input and cutting aren't bount by default, because you don't usually write long texts here. You may add those bindings if you wish:

HjsonTOML

```
{ key: "ctrl-c", internal: ":input_selection_copy" }
{ key: "ctrl-x", internal: ":input_selection_cut" }
```

The `:focus` internal has many uses.

It can be used without explicit argument in which case it takes the selection (for example `:!focus` is equivalent to ctrl→).

It can be used with an argument, for example you can go to a specific place without leaving broot by typing `fo /usr/bin` then enter.

You may also want to use it in some cases instead of enter because it keeps the active filter.

It serves as base for several built-in commands, like `:home` whose execution is `:focus ~` (`~` is interpreted in broot as the user home even on Windows).

And you can add your own ones:

HjsonTOML

```
{ key: "ctrl-up", internal: ":focus .." }
{ key: "ctrl-d", internal: ":focus ~/dev" }
```

The `cmd` argument lets you define a sequence, just like the one you give to broot with [the `--cmd` argument](https://dystroy.org/broot/launch/#the-cmd-launch-argument).

Such a sequence can contain some searches, some calls to internals, some calls to already defined external based verbs.

For example:

HjsonTOML

```
{
    name: "backup"
    invocation: "bu {name}"
    cmd: ":cp {file}-back_{name};:!focus {file}-back_{name}"
    apply_to: directory
}
```

This verb, which is only available when a directory is selected, copies this directory with a name partially composed from the command and focus the new directory in a new panel

Note

The `cmd` execution type is still experimental in verbs and the precise behavior may change in future minor versions of broot