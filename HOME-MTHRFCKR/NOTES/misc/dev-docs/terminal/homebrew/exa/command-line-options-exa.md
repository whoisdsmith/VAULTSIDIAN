# Command-line options · exa

> ## Excerpt
> The main way to configure exa is by passing options on the command-line.

---
-   [Introduction](https://the.exa.website/introduction)
-   [Installing exa](https://the.exa.website/install)
-   [Features](https://the.exa.website/features)
-   [Using exa](https://the.exa.website/docs)
    -   [Command-line options](https://the.exa.website/docs/command-line-options)
    -   [Environment variables](https://the.exa.website/docs/environment-variables)
    -   [Colour themes](https://the.exa.website/docs/colour-themes)
-   [Contributing](https://the.exa.website/contributing)

The main way to configure exa is by passing options on the command-line.

### Display Options

#### `-1`, `--oneline`

Displays [one file per line](https://the.exa.website/features/grid-view#oneline).

#### `-G`, `--grid`

Displays files [as a grid](https://the.exa.website/features/grid-view).

This is the default.

#### `-l`, `--long`

Displays files [in a table](https://the.exa.website/features/long-view) along with their metadata.

#### `-x`, `--across`

Sort the grid [across](https://the.exa.website/features/grid-view#across), rather than downwards.

#### `-R`, `--recurse`

[Recurses](https://the.exa.website/docs#recurse) into directories.

#### `-T`, `--tree`

Recurses into directories [as a tree](https://the.exa.website/features/tree-view).

#### `-L`, `--level=DEPTH`

Limits the depth of [recursion](https://the.exa.website/docs#recurse), so exa only descends up to the given number of times.

#### `-F`, `--classify`

Displays [file type indicators](https://the.exa.website/colours#classify) by file names.

#### `--color`, `--colour=WHEN`

Configures when to use terminal colours. The default choice is `automatic`, meaning that colours are used when exa is writing to a terminal, and are switched off if it’s not.

-   `**automatic**` or `**auto**` only display colours when writing to a terminal.
-   `**always**` displays them even if it’s not.
-   `**never**` doesn’t display them even if it _is_.

#### `--icons`

Displays [Unicode icons](https://the.exa.website/icons) by file names.

#### `--no-icons`

Don’t display icons (overrides `--icons`).

### Filtering and Sorting Options

#### `-a`, `--all`

Shows [hidden and ‘dot’ files](https://the.exa.website/features/filtering#dotfiles).

Use this twice to also show the `.` and `..` directories.

#### `-d`, `--no-recurse`, `--list-dirs`

Lists directories [without recursing](https://the.exa.website/docs#dirs) into them, as though they were regular files.

#### `-r`, `--reverse`

Reverses the [sort order](https://the.exa.website/features/filtering#sorting).

#### `-s`, `--sort=SORT_FIELD`

Configures which field to [sort by](https://the.exa.website/features/filtering#sorting).

-   `**name**` or `**filename**` sorts by name, case-insensitively.
-   `**Name**` or `**Filename**` sorts by name, case-_sensitively_.
-   `**cname**` or `**cfilename**` sorts by name, case-insensitively and _canonically_.
-   `**Cname**` or `**Cfilename**` sorts by name, case-sensitively and canonically.
-   `**.name**` or `**.filename**` sorts by name _without a leading dot_, case-insensitively.
-   `**.Name**` or `**.Filename**` sorts by name without a leading dot, case-sensitively.
-   `**size**` or `**filesize**` sorts by size, with smaller files listed first.
-   `**ext**` or `**extension**` sorts by file extension, case-insensitively.
-   `**Ext**` or `**Extension**` sorts by file extension, case-_sensitively_.
-   `**mod**` or `**modified**` sorts by file modified date, with older files listed first.
-   `**acc**` or `**accessed**` sorts by file accessed date.
-   `**cr**` or `**created**` sorts by file created date.
-   `**inode**` sorts by file inode.
-   `**type**` sorts by the _type_ of file (directory, socket, link).
-   `**none**` disables sorting, and lists files in an arbitrary order.

The `modified` field has the aliases `date`, `time`, and `new`, and `newest`. Also, because we usually think about dates relatively, its _reverse_ has the aliases `age`, `old`, and `oldest`.

Fields starting with a capital letter will sort uppercase before lowercase.

_Canonical_ sorting means that numbers will be treated as strings of digits instead of numbers. Normally, `9` comes before `10`, but sorting by `Cname` will sort `10` before `9` because it sees the `1` digit first.

#### `-I`, `--ignore-glob=GLOBS`

Glob patterns, pipe-separated, of [files to ignore](https://the.exa.website/features/filtering#ignoring).

#### `--git-ignore`

Ignores files [mentioned in `.gitignore`](https://the.exa.website/features/git).

#### `--group-directories-first`

Lists directories before other files [when sorting](https://the.exa.website/features/filtering#sorting).

### Long View Options

These options are available when running with `--long` (`-l`):

#### `-b`, `--binary`

Lists [file sizes](https://the.exa.website/features/long-view#sizes) with _binary_ prefixes.

#### `-B`, `--bytes`

list [file sizes](https://the.exa.website/features/long-view#sizes) in bytes, without _any_ prefixes.

#### `-g`, `--group`

Lists each file’s [group](https://the.exa.website/features/long-view#owners-and-groups).

#### `-h`, `--header`

Adds a header row to each column in the table.

#### `-H`, `--links`

Lists each file’s [number of hard links](https://the.exa.website/features/long-view#metadata).

#### `-i`, `--inode`

Lists each file’s [inode number](https://the.exa.website/features/long-view#metadata).

#### `-m`, `--modified`

Uses the [modified timestamp field](https://the.exa.website/features/long-view#timestamps).

#### `-S`, `--blocks`

Lists each file’s [filesystem block count](https://the.exa.website/features/long-view#metadata).

#### `-t`, `--time=WORD`

Configures which [timestamp field](https://the.exa.website/features/long-view#timestamps) to list (`modified`, `accessed`, `created`).

#### `--time-style=STYLE`

Configures which format [timestamps](https://the.exa.website/features/long-view#timestamps) should be in.

-   `**default**` uses the current locale to print month names, specifies the timestamp down to the minute for times in the _current_ year, and down to the day for previous years.
-   `**iso**` does the same, except using a month for the number so it doesn’t need to look up the locale.
-   `**long-iso**` specifies the timestamp down to the minute without using the locale or current year.
-   `**full-iso**` specifies the timestamp down to the _millisecond_, including its offset down to the minute, without using the locale or current year.

#### `-u`, `--accessed`

Uses the [accessed timestamp field](https://the.exa.website/features/long-view#timestamps).

#### `-U`, `--created`

Uses the [created timestamp field](https://the.exa.website/features/long-view#timestamps).

#### `-@`, `--extended`

Lists each file’s [extended attributes](https://the.exa.website/features/xattrs) and sizes.

#### `--git`

Lists each file’s [Git status](https://the.exa.website/features/git), if tracked.

#### `--color-scale`, `--colour-scale`

Highlights levels of [file size](https://the.exa.website/features/long-view#sizes) distinctly.

#### `--no-permissions`

Suppress the permissions column.

#### `--no-filesize`

Suppress the file size column.

#### `--no-user`

Suppress the user column.

#### `--no-time`

Suppress the time column.
