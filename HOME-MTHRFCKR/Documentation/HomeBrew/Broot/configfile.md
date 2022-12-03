Two formats are allowed: [TOML](https://github.com/toml-lang/toml) and [Hjson](https://hjson.github.io/).

This documentation will often show you the same setting in both formats, with two tabs, like this:

HjsonTOML

```
// setting to use if your config file is in .hjson
```

The main configuration file is called either `conf.toml` or `conf.hjson`.

This default file's location follows the XDG convention, which depends on your system settings. This location in your case can be found on the help screen (use ?). From this screen you can directly open the configuration file in your system's editor by typing `:os` (shortcut for `:open_stay`).

The default configuration file contains several example sections that you may uncomment and modify for your goals.

The current default configuration file may be seen here: [default-conf.hjson](https://dystroy.org/broot/download/default-conf.hjson).

Broot accepts a few flags at launch (the complete list is available with `broot --help`.

For example, if you want to see hidden files (the ones whose name starts with a dot) and the status of files related to git, you launch broot with

```
br -gh
```

If you almost always want those flags, you may define them as default in the configuration file file, with the `default_flags` setting.

HjsonTOML

```
default_flags: gh
```

Those flags can still be overridden at launch with the negating ones. For example if you don't want to see hidden files at a specific launch, do

```
br -H
```

Broot usually captures the mouse so that you can click or double click on items. If you want to disable this capture, you may add this:

HjsonTOML

```
capture_mouse: false
```

You may map special paths to specific behaviors. You may especially want

-   to have some link to a directory to always automatically be handled as a normal directory
-   to exclude some path because it's on a slow device or non relevant

Example configuration:

HjsonTOML

```
special_paths: {
    "/media/slow-backup-disk"             : no-enter
    "/home/dys/useless"                   : hide
    "/home/dys/my-link-I-want-to-explore" : enter
}
```

Be careful that those paths (globs, in fact) are checked a lot when broot builds trees and that defining a lot of paths will impact the overall speed.

It's possible to redefine the mode mappings, for example if you usually prefer to do exact searches:

HjsonTOML

```
"search-modes": {
    <empty>: regex name
    /: fuzzy path
    z/: regex path
}
```

The search mode must be made of two parts :

-   the search kind: Either `exact`, `fuzzy`, `regex`, or `tokens`
-   the search object: Either `name`, `path`, or `content`

You can usually cancel the last state change on escape. If you want the escape key to quit broot when there's nothing to cancel (for example when you just opened broot), you can set `quit_on_last_cancel` to true. this parameter

HjsonTOML

```
quit_on_last_cancel: true
```

When the background colors aren't rendered in your terminal, aren't visible enough, or just aren't clear enough for you, you may have the selected lines marked with triangles with

HjsonTOML

```
show_selection_mark: true
```

You may change the order of file attributes in file lists:

-   mark: a small triangle flagging the selected line
-   git : Git file info
-   branch : shows the depth and parent in the tree
-   permission : mode, user, group
-   date : last modification date
-   size : ISO size (and size bar when sorting)
-   count : number of files in directories
-   name : file name

For example, if you prefer to have the branches left of the tree (as was the default in broot prior 0.18.1) you can use

HjsonTOML

```
cols_order: [
    mark
    git
    branch
    permission
    date
    size
    count
    name
]
```

The name should be kept at end as it's the only one with a variable size.

broot doesn't support `LS_COLORS` which isn't available on all systems and is limited to 16 system dependant colors.

But you can still give a color to files by extension:

HjsonTOML

```
ext_colors: {
    png: "rgb(255, 128, 75)"
    rs: "yellow"
    toml: "ansi(105)"
}
```

(see [here](https://dystroy.org/broot/skins#color) for precision about the color syntax in broot)

You can choose any of the following syntaxic coloring themes for previewed files:

-   base16-ocean.dark
-   base16-eighties.dark
-   base16-mocha.dark
-   base16-ocean.light
-   InspiredGitHub
-   Solarized (dark)
-   Solarized (light)

HjsonTOML

```
syntax_theme: base16-ocean.light
```

Those themes come from [syntect](https://github.com/trishume/syntect) and are bundled in broot.

Most users should not change this. In my measurements a number of 4 to 6 looks optimal.

I'm looking for people to try tune this and tell me what they find, what's their OS and disk type.

HjsonTOML

```
file_sum_threads_count: 10,
```

If you make experiments, please come to [Miaou](https://miaou.dystroy.org/3490) and tell me.