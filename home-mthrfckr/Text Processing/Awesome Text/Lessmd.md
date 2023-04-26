# lessmd

---

![asciicast](https://camo.githubusercontent.com/7fefaf6b325fd42743f7e30824aa01d936450e24144dd974021fc642e1e9ffff/68747470733a2f2f61736369696e656d612e6f72672f612f39303332332e706e67)

[Lessmd](https://git.io/lessmd) is a terminal viewer/pager with markdown and piping support.

## Why ?

- It is a JavaScript
- Minimal and fast
- Unix like pager with navigation
- Displays markdown with colors
- Can translate markdown into colored output
- Configurable user interface
- Supports files and pipes
- With livereload (watch filechanges)
- Markdown theming support

## Usage

Pager mode:

Shortcuts:

- `q` or `ctrl+c` exit

Piping with another programs:

To save some output into a file, which you can use as a motd or an issue files.

 echo "\# welcome\\n \* do not touch anything \\n \* just press Ctrl+D" \\  
 | lessmd | tee /etc/motd

[![pipe example](https://raw.githubusercontent.com/linuxenko/lessmd/master/misc/pipe-example.png)](https://raw.githubusercontent.com/linuxenko/lessmd/master/misc/pipe-example.png)

## Installation

## Configuration

Lessmd looks for user settings inside of a home directory, the filename is `.lessmd.js`.

Example of the `.lessmd.js`:

```
module.exports \= {  
  colors : { /// markdown theming colors  
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
    draw : false // disable any ui (header and footer bars)  
    text : '', // text style  
    strong : '' // bold text style  
  },  
  headerfn : function() { return 'header'; }, // custom header fn,  
  footerfn : function() { return 'footer'; } // custom footer fn  
};
```

---
