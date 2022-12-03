The staging area is broot's solution to let you execute commands on several files in one go.

When the staging area is focused, commands apply to all the files it contains.

You can change the bindings to the `:stage`, `:unstage` and `:toggle_stage` verbs. The standard bindings are below

verb

default binding

comment

`:toggle_stage`

ctrlg

the easiest solution when not using broot in [modal](https://dystroy.org/broot/modal)

`:stage`

+

only in [command mode](https://dystroy.org/broot/modal#usage)

`:unstage`

\-

only in [command mode](https://dystroy.org/broot/modal#usage)

`:clear_stage`

shortcut: `:cls`

When staging a file, the staging area opens (but doesn't get focused) if it wasn't and there's not aleady the max number of panels open.

Focus the staging area (usually with ctrl→) then type the verb in the input.

The verb will be executed, in order, to all files of the staging area.

![staging mv](https://dystroy.org/broot/img/20210424-staging-mv.png)

Computed groups which would have the same value for all files are shown in the status bar. For example here, when you type `mv ../app-panels`, broot can tell you that it will run `mv {file} /home/dys/dev/broot/src/app-panels/` for each file of the staging area.

Some verbs aren't compatible with execution on the staging area:

-   Verbs which don't come back to broot after execution (for example `:cd` or any verb quitting broot)
-   [Sequences](https://dystroy.org/broot/conf_verbs#cmd-execution)

The staging area can be opened or closed with the `:open_staging_area`, `:close_staging_area`, and `:toggle_staging_area` verbs, which have shortcuts `:osa`, `:csa`, and `:tsa`. But you rarely need those verbs as the staging area opens when you add to it and closes when it goes empty.

You can filter, select, scroll, as in other panels. This may be convenient either to unstage a precise file from the staging area, or to check some files are present (or not) when there are many of them.

![staging filter](https://dystroy.org/broot/img/20210425-staging-filter.png)

The staging area is a new feature of broot. Some features (staging with globs for example) may be added, some may be changed, depending on your feedback.