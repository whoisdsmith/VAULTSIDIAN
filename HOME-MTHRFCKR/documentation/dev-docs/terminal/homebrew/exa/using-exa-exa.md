# Using exa · exa

> ## Excerpt
> Listing files is exa’s bread and butter.
You pass each file you want as an argument, as well as some options for how to display files, and exa will list them in the terminal.

---
### Listing files

Listing files is exa’s bread and butter. You pass each file you want as an argument, as well as some options for how to display files, and exa will list them in the terminal.

exa --long --header Barbados.jpg Singing.mp3
Permissions Size User Date Modified Name
drwxr\-xr\-x  7.2M ben  18 Mar  8:50  Barbados.jpg
.rwxr\-xr\-x  3.8M ben  25 May 14:29  Singing.mp3

If you’re dealing with the _very specific_ edge case where your files look like arguments, such as trying to list a file literally named “`--long`”, then insert the “`--`” argument before it. This special argument causes everything after it to be treated as file paths, rather than as options.

exa --long -- --long
.rwxr\-xr\-x 621 ben 23 Apr 09:13 \--long

### Listing directories

If you pass a directory to exa, it will list the _contents_ of that directory rather than listing the directory itself. And if you don’t specify _any_ files to list, it’ll list everything in the current directory.

Something like 90% of the time I just use `exa` with no files or options.

exa Documents
a.out  example.txt          Geocaching          Homework    skiing notes.md
code   Finance budget.xlsx  heart\_and\_soul.m4a  router.tar

You can prevent exa from recursing into directories with the `-d` or `--no-recurse` command-line option. This tells exa to treat directories as though they were files.

### Listing links

Another feature common among OSes is the **link**: a file that points to another file as its “actual” contents. Unix-style systems call these **symlinks**.

When using a view that displays one file per line (either lines, details, or tree), exa will display a link’s target path next to its filename. It will examine the target path and highlight the resulting file as though it were a regular file. If the link points to a file that does not exist, then exa will display its _intended_ path.

exa -l /etc/localtime /etc/resolv.conf
Permissions Size User Date Modified Name
drwxr\-xr\-x    33 root  31 Jan 18:14 /etc/localtime \-> /usr/share/zoneinfo/UTC
.rwxr\-xr\-x    22 root   1 May  2017 /etc/resolv.conf \-> ../var/run/resolv.conf

### Recursion

Finally, it’s possible for exa to recurse into a directory and list the contents of _every_ subdirectory beneath it. There are the `-R` or `--recurse` command-line options for this.

When recursing, exa will provide separate listings for any subdirectories discovered underneath the original.

exa --recurse
Complete         Worksheet 8.pdf   Worksheet 11.pdf  Worksheet 14.pdf
Worksheet 6.pdf  Worksheet 9.pdf   Worksheet 12.pdf  Worksheet 15.pdf
Worksheet 7.pdf  Worksheet 10.pdf  Worksheet 13.pdf  Worksheet 16.pdf

./Complete:
Worksheet 1.pdf  Worksheet 3.pdf  Worksheet 5.pdf
Worksheet 2.pdf  Worksheet 4.pdf

### Subsections

For a complete reference on what exa can do, select one of the pages below.

-   **[Command-line options](https://the.exa.website/docs/command-line-options)**
    
    The full list of command-line options.
    
-   **[Environment variables](https://the.exa.website/docs/environment-variables)**
    
    The full list of environment variables.
    
-   **[Colour themes](https://the.exa.website/docs/colour-themes)**
    
    The `LS_COLORS` and `EXA_COLORS` variables and how they can be used to theme exa’s output.
