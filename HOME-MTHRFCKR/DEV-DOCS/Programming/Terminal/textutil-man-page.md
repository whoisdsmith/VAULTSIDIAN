textutil Man Page - macOS - SS64.com 

Manipulate text files in various formats.

Syntax

       textutil -info \[_options_\] _file_ ...

       textutil -convert _fmt_ \[_options_\] _file_ ...

       textutil -cat _fmt_ \[_options_\] _file_ ...

       textutil -help \[_options_\] _file_ ...

Key
     -info         Display information about the specified files.

     -convert _fmt_  Convert the files to format _fmt_ and write each one 
                   back to the file system.

     -cat _fmt_      Read the specified files, concatenate them, and write the
                   result out as a single file in the indicated format.

     -help         Show usage information and exit.

     _fmt_           One of:  txt, html, rtf, rtfd, doc, wordml, or webarchive

Options

     -encoding _IANA\_name_ | _NSStringEncoding_
                     The encoding to be used for plain text or HTML output
                     (by default, the output encoding will be UTF-8).

     -extension _ext_  Specify an extension to be used for output files (by
                     default, the extension will be determined from the format).

     -format _fmt_     Force all input files to be interpreted using the indicated 
                     format (by default, a file's format will be determined from
                     its contents).

     -font _font_      The font to be used when converting to rich text.

     -fontsize _size_  Font size (in points) to be used for converting plain to rich text.

     -inputencoding _IANA\_name_ | _NSStringEncoding_
                     Force all plain text input files to be interpreted using
                     the specified encoding (by default, a file's encoding
                     will be determined from its BOM).

     -output _path_    The file name to be used for the first output file.

     -stdout         Send the first output file to stdout.

     --              Specify that all further arguments are file names.

Additional options for HTML and WebArchive files:

     -noload          Do not load subsidiary resources.
     -nostore         Do not write out subsidiary resources.
     -baseurl _url_     Specify a base URL to be used for relative URLs.
     -timeout _t_       The time in seconds to wait for resources to load.
     -textsizemultiplier _x_   A numeric factor by which to multiply font sizes.
     -excludedelements (_tag1, tag2_, ...)
                      Specify which HTML elements should not be used in generated 
                      HTML (the list should be a single argument, and so will
                      usually need to be quoted in a shell context).
     -prefixspaces _n_  The number of spaces by which to indent nested
                      elements in generated HTML (default is 2).

Additional options for the output file metadata:

     -strip        Do not copy metadata from input files to output files.
     -title _val_    The title metadata attribute for output files.
     -author _val_   The author metadata attribute for output files.
     -subject _val_  The subject metadata attribute for output files.
     -keywords (_val1, val2_, ...)
                   The keywords metadata attribute for output files
                   (the list should be a single argument, and so will usually
                   need to be quoted in a shell context).

     -comment _val_  The comment metadata attribute for output files.
     -editor _val_   The editor metadata attribute for output files.
     -company _val_  The company metadata attribute for output files.
     -creationtime _yyyy-mm-ddThh:mm:ssZ_
                   The creation time metadata attribute for output files.
     -modificationtime _yyyy-mm-ddThh:mm:ssZ_
                   The modification time metadata attribute for output
                   files.

Textutil first appeared in OS X 10.4

**Examples**:

Display information about foo.rtf.  
$ textutil -info foo.rtf

Convert foo.rtf into foo.html.  
$ textutil -convert html foo.rtf

Convert foo.txt into foo.rtf, using Times 10 for the font.  
$ textutil -convert rtf -font Times -fontsize 10 foo.txt

Load all RTF files in the current directory, concatenate their contents, and write the result out as index.html with the HTML title set to Several Files".

$ textutil -cat html -title "Several Files" -output index.html \*.rtf

Create a .txt file for each .doc file in the directory.  
$ textutil -convert txt \*.doc

Notes:  
The textutil command exits 0 on success, and 1 on failure.  
Some options may require a connection to the window server.

_“A lot of people are afraid to say what they want, that's why a lot of people don't get what they want” ~ Madonna_

**Related macOS commands:**

[GetFileInfo](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/getfileinfo.html) - Get attributes of HFS+ files.  
[pr](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/pr.html) - Convert text files for printing.  
[say](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/say.html) - Convert text to audible speech.  
[setfile](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/setfile.html) - Set attributes of HFS+ files.  
[sips](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/sips.html) - Scriptable image processing system.

___

Copyright © 1999-2022 [SS64.com](https://ss64.com/)  
Some rights reserved