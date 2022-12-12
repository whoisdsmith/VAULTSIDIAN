# Environment variables · exa

> ## Excerpt
> The other way to configure exa is through environment variables.

---
-   [Introduction](https://the.exa.website/introduction)
-   [Installing exa](https://the.exa.website/install)
-   [Features](https://the.exa.website/features)
-   [Using exa](https://the.exa.website/docs)
    -   [Command-line options](https://the.exa.website/docs/command-line-options)
    -   [Environment variables](https://the.exa.website/docs/environment-variables)
    -   [Colour themes](https://the.exa.website/docs/colour-themes)
-   [Contributing](https://the.exa.website/contributing)

The other way to configure exa is through environment variables.

Usually, if you want to change exa’s behaviour, you pass in a different command-line argument, or go to a different directory. Environment variables, on the other hand, are used to configure rarely-changed settings, override information usually provided by the OS, and change the way the command-line arguments are parsed.

You can run a one-off command with a different variable set by using the `env` command:

env TIME-STYLE="iso" exa

Setting these variables permanently depends on your shell and OS, but will probably involve editing a configuration file.

### `COLUMNS`

Overrides the width of the terminal, in characters, when using a [grid view](https://the.exa.website/features/grid-view). For example, with `COLUMNS=80`, exa will show a grid no more than 80 characters wide.

This option won’t do anything when not displaying files in a grid — all the other output modes don’t need to wrap.

### `TIME_STYLE`

Sets how to format the time used in the long view’s [time column](https://the.exa.website/features/long-view#timestamps).

This follows the same rules as the `--time-style` option, and will be overridden if one is specified.

### `EXA_STRICT`

Enables strict mode, which will make exa error when two command-line options are incompatible.

Usually, options can override each other going right-to-left on the command line. For example, the following command will [sort](https://the.exa.website/features/filtering#sorting) by `size` rather than `ext`, because it’s the option specified second:

`exa --sort=ext --sort=size`

In strict mode, the two options will not co-operate, and exa will error.

This option is intended for use with automated scripts and other situations where you want to be certain you’re typing in the right command.

### `EXA_GRID_ROWS`

Limits the [grid-details view](https://the.exa.website/features/long-view#long-grid) (`exa --grid --long`) so it’s only activated when at least the given number of rows of output would be generated.

When displaying a small directory on a widescreen monitor, it’s possible for the grid to look very wide and sparse, on just one or two lines with none of the columns lining up. By specifying a minimum number of rows, you can only use the view if it’s going to be worth using.

### `EXA_ICON_SPACING`

Specifies the number of spaces to print between [an icon](https://the.exa.website/features/icons) and its file name.

Different terminals display icons differently, as they usually take up more than one character width on screen, so there’s no “standard” number of spaces that exa can use to separate an icon from text. One space may place the icon too close to the text, and two spaces may place it too far away. So the choice is left up to the user to configure depending on their terminal emulator.

### `LS_COLORS` and `EXA_COLORS`

The `LS_COLORS` variable is the traditional way of customising the colours used by ls, and `EXA_COLORS` adds exa-specific extensions.

For more information, see the [Colour themes page](https://the.exa.website/docs/themes).
