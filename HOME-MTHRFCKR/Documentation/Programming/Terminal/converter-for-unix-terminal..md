### Lessmd

[![npm version](https://camo.githubusercontent.com/34ac07da56ca0e6cfd8bf4cc8a71d6fb6ea0f6b7527a5f550185be8e087cd26f/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f6c6573736d642e7376673f7374796c653d666c61742d737175617265)](https://www.npmjs.com/package/lessmd) [![Build Status](https://camo.githubusercontent.com/4cb59406d47c2178c84a4cb7bcfa291fa3dd9132a4c5b7b30f1547e7e6395312/68747470733a2f2f696d672e736869656c64732e696f2f7472617669732f6c696e7578656e6b6f2f6c6573736d643f7374796c653d666c61742d737175617265)](https://travis-ci.org/linuxenko/lessmd) [![Coverage Status](https://camo.githubusercontent.com/7743a82b7db8c185a0d4f3cf748e96f4d086feffe21e12f8853def0e3a99cc20/68747470733a2f2f696d672e736869656c64732e696f2f636f766572616c6c732f6769746875622f6c696e7578656e6b6f2f6c6573736d643f7374796c653d666c61742d737175617265)](https://coveralls.io/github/linuxenko/lessmd) [![dependencies Status](https://camo.githubusercontent.com/ef790fa7bfd8277e7aacea654d7b9d4f571c9f063e5c53d77b1d21a381a2de2c/68747470733a2f2f64617669642d646d2e6f72672f6c696e7578656e6b6f2f6c6573736d642f7374617475732e7376673f7374796c653d666c61742d737175617265)](https://david-dm.org/linuxenko/lessmd) [![devDependencies Status](https://camo.githubusercontent.com/7dca8b89e8ce6dc0d84f51c4bfbcc720e7e52752cd53baa9f77107a5be67e0f2/68747470733a2f2f64617669642d646d2e6f72672f6c696e7578656e6b6f2f6c6573736d642f6465762d7374617475732e7376673f7374796c653d666c61742d737175617265)](https://david-dm.org/linuxenko/lessmd?type=dev)

[![asciicast](https://camo.githubusercontent.com/7fefaf6b325fd42743f7e30824aa01d936450e24144dd974021fc642e1e9ffff/68747470733a2f2f61736369696e656d612e6f72672f612f39303332332e706e67)](https://asciinema.org/a/90323)

[Lessmd](https://git.io/lessmd) is a terminal viewer/pager with markdown and piping support.

### Why ?

-   It is a JavaScript
-   Minimal and fast
-   Unix like pager with navigation
-   Displays markdown with colors
-   Can translate markdown into colored output
-   Configurable user interface
-   Supports files and pipes
-   With livereload (watch filechanges)
-   Markdown theming support

### Usage

Pager mode:

Shortcuts:

-   `q` or `ctrl+c` exit

Piping with another programs:

To save some output into a file, which you can use as a motd or an issue files.

 echo "\# welcome\\n \* do not touch anything \\n \* just press Ctrl+D" \\
 | lessmd | tee /etc/motd

[![pipe example](https://raw.githubusercontent.com/linuxenko/lessmd/master/misc/pipe-example.png)](https://raw.githubusercontent.com/linuxenko/lessmd/master/misc/pipe-example.png)

### Installation

### Configuration

Lessmd looks for user settings inside of a home directory, the filename is `.lessmd.js`.

Example of the `.lessmd.js`:

module.exports \= {
  colors : {    /// markdown theming colors
    text : ,    
    lang : ,
    heading : ,
    code : ,
    quote : ,
    em : ,
    codespan : ,
    strong : ,
    html : ,
    del : ,
    link : ,
    hr : ,
    listitem :,
  },
  theme : {
    draw : false       // disable any ui (header and footer bars)
    text : '',         // text style
    strong : ''        // bold text style
  },
  headerfn : function() { return 'header'; }, // custom header fn,
  footerfn : function() { return 'footer'; }  // custom footer fn
};

### ChangeLog

**1.2.1**

-   Dependencies update

**1.2.0**

-   Bug with long slices

**1.1.0 - 2016-11-15**

-   Html options for marked (sanityze, smartypants)
-   `h,j,k,l` bindings
-   Smaller chunks colorization for view mode

**1.0.1 - 2016-11-03**

-   Added original less keybindings

### License

MIT (c) Svetlana Linuxenko