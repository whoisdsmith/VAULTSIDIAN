# Colour themes · exa

> ## Excerpt
> ls supports changing this behaviour by setting the LS_COLORS variable. Its format is a list of pairs of file name globs and colour codes, separated by equals signs, and then separated again with colons between the pairs:

---
`ls` supports changing this behaviour by setting the `LS_COLORS` variable. Its format is a list of pairs of file name globs and colour codes, separated by equals signs, and then separated _again_ with colons between the pairs:

LS\_COLORS=" glob = code : glob = code : ..."

The file name globs use the same format as [ignoring files by glob](https://the.exa.website/features/filtering#ignoring "The glob syntax used by exa.") does.

So in order to highlight `.xyz` files in an extremely visible colour — let’s say white on red — you would set:

LS\_COLORS="\*.xyz=37;41"

To additionally set `.ts` files to a more calming blue, you would set:

LS\_COLORS="\*.xyz=37;41:\*.ts=34"

It’s not the easiest syntax to read, so it’s important to notice the difference between the _colons_ used to separate pairs from the _semicolons_ used to write the colour codes.

### File class colours

Before looking at a file’s extension, exa looks at the file’s _class_ in the filesystem — whether it’s a directory, a socket, a link, or (in a special case) an executable file.

You can customise the colours used for each file by using one of these two-character-long keys with a colour:

-   `fi` Normal file
-   `di` Directory
-   `ex` Executable file
-   `pi` Named pipe
-   `so` Socket
-   `bd` Block device
-   `cd` Character device
-   `ln` Symlink
-   `or` Broken symlink

For example, if you wanted to change both block and character devices to purple, you’d use:

LS\_COLORS="bd=35:cd=35"

### Customising exa’s interface

exa has its own environment variable, `EXA_COLORS`, which can be used as an exa-specific version of `LS_COLORS`. File classes and globs in this variable will be read by exa but won’t be read by `ls`.

The other more important use of `EXA_COLORS` is that you can use it to customise parts of exa’s interface, including the colours for the permission bits, the date, user, inode, and other metadata columns, and punctuation such as arrows and tree characters.

To change these colours, set the relevant key in `EXA_COLORS` to the colour code you want.

##### Permissions

-   `ur` User `+r` bit
-   `uw` User `+w` bit
-   `ux` User `+x` bit (files)
-   `ue` User `+x` bit (file types)
-   `gr` Group `+r` bit
-   `gw` Group `+w` bit
-   `gx` Group `+x` bit
-   `tr` Others `+r` bit
-   `tw` Others `+w` bit
-   `tx` Others `+x` bit
-   `su` Higher bits (files)
-   `sf` Higher bits (other types)
-   `xa` Extended attribute marker

##### File sizes

-   `sn` Size numbers
-   `sb` Size unit
-   `df` Major device ID
-   `ds` Minor device ID

##### Owners and Groups

-   `uu` A user that’s you
-   `un` A user that’s not
-   `gu` A group with you in it
-   `gn` A group without you

##### Hard links

-   `lc` Number of links
-   `lm` A multi-link file

##### Git

-   `ga` New
-   `gm` Modified
-   `gd` Deleted
-   `gv` Renamed
-   `gt` Type change

##### Details and metadata

-   `xx` Punctuation
-   `da` Timestamp
-   `in` File inode
-   `bl` Number of blocks
-   `hd` Table header row
-   `lp` Symlink path
-   `cc` Control character

##### Overlays

-   `bO` Broken link path

Here’s how you make timestamps a brighter shade of blue:

EXA\_COLORS="da=1;34"

### Colour codes

The colour codes used in `LS_COLORS` and `EXA_COLORS` are [ANSI escape codes](https://en.wikipedia.org/wiki/ANSI_escape_code "ANSI escape codes on Wikipedia."). These codes can tell the terminal emulator to do all sorts of things, including moving the cursor around and scrolling up and down, but exa only uses the ones that change the text colour.

To use them, combine one or more of the following with semicolons:

##### Foreground

-   `30` Black
-   `31` Red
-   `32` Green
-   `33` Yellow
-   `34` Blue
-   `35` Purple
-   `36` Cyan
-   `37` White

##### Background

-   `40` On black
-   `41` On red
-   `42` On green
-   `43` On yellow
-   `44` On blue
-   `45` On purple
-   `46` On cyan
-   `47` On white

##### Effects

-   `01` Bold
-   `04` Underline

##### 256 colours

-   `38;5;nnn` Foreground
-   `48;5;nnn` Background

Here’s what you’d use for a bold-and-white-on-red file that means Java just crashed:

EXA\_COLORS="hs\_err\_pid\*=37;41;1"
