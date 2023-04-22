# Textutil

Documentation can be found at

- [https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/tcllib/files/modules/textutil/textutil.md](https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/tcllib/files/modules/textutil/textutil.md)
- [http://docs.activestate.com/activetcl/8.5/tcl/tcllib/textutil/textutil.html](http://docs.activestate.com/activetcl/8.5/tcl/tcllib/textutil/textutil.html)

Contains for example the core of the template and macro processor [expand](https://wiki.tcl-lang.org/page/expand). Released since Tcllib 1.2.

Module contains:

- **textutil::adjust** *string* ?*option value…*?
- **textutil::adjust::getPredefined** *filename*
- **textutil::adjust::listPredefined**
- **textutil::adjust::readPatterns** *filename*
- **textutil::indent** *string prefix* ?*skip*?
- **textutil::undent** *string*
    - See also [ycl dedent](https://wiki.tcl-lang.org/page/ycl), which considers tabs when determining how to remove indentation.
- **textutil::strRepeat** *string num*
- **textutil::blank** *num*
- **textutil::[splitn](https://wiki.tcl-lang.org/page/splitn)** *string* ?*len*?  
    *len* defaults to 1
- **textutil::[splitx](https://wiki.tcl-lang.org/page/splitx)** *string* ?*regexp*?  
    *regexp* defaults to \[\\t \\r\\n\]+
- **textutil::cap** *string*
- **textutil::chop** *string*
- **textutil::longestCommonPrefixList** *list*
- **textutil::longestCommonPrefix** ?*string*?
- **textutil::tail** *string*
- **textutil::uncap** *string*
- **textutil::tabify** *string* ?*num*?
- **textutil::tabify2** *string* ?*num*?
- **textutil::untabify** *string* ?*num*?
- **textutil::untabify2** *string* ?*num*?  
    *tab* above defaults to 8
- **textutil::trim** *string* ?*regexp*?
- **textutil::trimleft** *string* ?*regexp*?
- **textutil::trimright** *string* ?*regexp*?
- **textutil::trimPrefix** *string prefix*
- **textutil::trimEmptyHeading** *string*  
    *regexp* above defaults to \[\\t \\r\\n\]+
- textutil::expand  
    **Note:** This command comes in its own package
- textutil::expander  
    This package is used by [doctools](https://wiki.tcl-lang.org/page/doctools).

*[escargo](https://wiki.tcl-lang.org/page/escargo) 30 May 2007* - This seems to be documentation for a version prior to Tcl 8.2, textutil 0.7.1.

___

# Textutil

textutil - Procedures to manipulate texts and strings.

The package **textutil** provides commands that manipulate strings or texts (a.k.a. long strings or string with embedded newlines or paragraphs). It is actually a bundle providing the commands of the six packages

in the namespace **textutil**.

The bundle is *deprecated*, and it will be removed in a future release of Tcllib, after the next release. It is recommended to use the relevant sub packages instead for whatever functionality is needed by the using package or application.

The complete set of procedures is described below.

- **::textutil::adjust** *string args*
    

    Do a justification on the *string* according to *args*. The string is taken as one big paragraph, ignoring any newlines. Then the line is formatted according to the options used, and the command return a new string with enough lines to contain all the printable chars in the input string. A line is a set of chars between the beginning of the string and a newline, or between 2 newlines, or between a newline and the end of the string. If the input string is small enough, the returned string won't contain any newlines.

    

    Together with **::textutil::indent** it is possible to create properly wrapped paragraphs with arbitrary indentations.

    

    By default, any occurrence of spaces characters or tabulation are replaced by a single space so each word in a line is separated from the next one by exactly one space char, and this forms a *real* line. Each *real* line is placed in a *logical* line, which have exactly a given length (see **\-length** option below). The *real* line may have a lesser length. Again by default, any trailing spaces are ignored before returning the string (see **\-full** option below). The following options may be used after the *string* parameter, and change the way the command place a *real* line in a *logical* line.

    
    - \-full *boolean*
        

        If set to **false**, any trailing space chars are deleted before returning the string. If set to **true**, any trailing space chars are left in the string. Default to **false**.

        
    - **\-hyphenate** *boolean*
        

        if set to **false**, no hyphenation will be done. If set to **true**, the last word of a line is tried to be hyphenated. Defaults to **false**. Note: hyphenation patterns must be loaded prior, using the command **::textutil::adjust::readPatterns**.

        
    - **\-justify** **center|left|plain|right**
        

        Set the justification of the returned string to **center**, **left**, **plain** or **right**. By default, it is set to **left**. The justification means that any line in the returned string but the last one is build according to the value. If the justification is set to **plain** and the number of printable chars in the last line is less than 90% of the length of a line (see **\-length**), then this line is justified with the **left** value, avoiding the expansion of this line when it is too small. The meaning of each value is:

        
        - **center**
            

            The real line is centered in the logical line. If needed, a set of space characters are added at the beginning (half of the needed set) and at the end (half of the needed set) of the line if required (see the option **\-full**).

            
        - **left**
            

            The real line is set on the left of the logical line. It means that there are no space chars at the beginning of this line. If required, all needed space chars are added at the end of the line (see the option **\-full**).

            
        - **plain**
            

            The real line is exactly set in the logical line. It means that there are no leading or trailing space chars. All the needed space chars are added in the *real* line, between 2 (or more) words.

            
        - **right**
            

            The real line is set on the right of the logical line. It means that there are no space chars at the end of this line, and there may be some space chars at the beginning, despite of the **\-full** option.

            
    - **\-length** *integer*
        

        Set the length of the *logical* line in the string to *integer*. *integer* must be a positive integer value. Defaults to **72**.

        
    - **\-strictlength** *boolean*
        

        If set to **false**, a line can exceed the specified **\-length** if a single word is longer than **\-length**. If set to **true**, words that are longer than **\-length** are split so that no line exceeds the specified **\-length**. Defaults to **false**.

        
- **::textutil::adjust::readPatterns** *filename*
    

    Loads the internal storage for hyphenation patterns with the contents of the file *filename*. This has to be done prior to calling command **::textutil::adjust** with "**\-hyphenate** **true**", or the hyphenation process will not work correctly.

    

    The package comes with a number of predefined pattern files, and the command **::textutil::adjust::listPredefined** can be used to find out their names.

    
- **::textutil::adjust::listPredefined**
    

    This command returns a list containing the names of the hyphenation files coming with this package.

    
- **::textutil::adjust::getPredefined** *filename*
    

    Use this command to query the package for the full path name of the hyphenation file *filename* coming with the package. Only the filenames found in the list returned by **::textutil::adjust::listPredefined** are legal arguments for this command.

    
- **::textutil::indent** *string* *prefix* ?*skip*?
    

    Each line in the *string* indented by adding the string *prefix* at its beginning. The modified string is returned as the result of the command.

    

    If *skip* is specified the first *skip* lines are left untouched. The default for *skip* is **0**, causing the modification of all lines. Negative values for *skip* are treated like **0**. In other words, *skip* > **0** creates a hanging indentation.

    

    Together with **::textutil::adjust** it is possible to create properly wrapped paragraphs with arbitrary indentations.

    
- **::textutil::undent** *string*
    

    The command computes the common prefix for all lines in *string* consisting solely out of whitespace, removes this from each line and returns the modified string.

    

    Lines containing only whitespace are always reduced to completely empty lines. They and empty lines are also ignored when computing the prefix to remove.

    

    Together with **::textutil::adjust** it is possible to create properly wrapped paragraphs with arbitrary indentations.

    
- **::textutil::splitn** *string* ?*len*?
    

    This command splits the given *string* into chunks of *len* characters and returns a list containing these chunks. The argument *len* defaults to **1** if none is specified. A negative length is not allowed and will cause the command to throw an error. Providing an empty string as input is allowed, the command will then return an empty list. If the length of the *string* is not an entire multiple of the chunk length, then the last chunk in the generated list will be shorter than *len*.

    
- **::textutil::splitx** *string* ?*regexp*?
    

    Split the *string* and return a list. The string is split according to the regular expression *regexp* instead of a simple list of chars. Note that if you add parenthesis into the *regexp*, the parentheses part of separator would be added into list as additional element. If the *string* is empty the result is the empty list, like for **[split](https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/index.md#split)**. If *regexp* is empty the *string* is split at every character, like **[split](https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/index.md#split)** does. The regular expression *regexp* defaults to "\[\\\\t \\\\r\\\\n\]+".

    
- **::textutil::tabify** *string* ?*num*?
    

    Tabify the *string* by replacing any substring of *num* space chars by a tabulation and return the result as a new string. *num* defaults to 8.

    
- **::textutil::tabify2** *string* ?*num*?
    

    Similar to **::textutil::tabify** this command tabifies the *string* and returns the result as a new string. A different algorithm is used however. Instead of replacing any substring of *num* spaces this command works more like an editor. *num* defaults to 8.

    

    Each line of the text in *string* is treated as if there are tabstops every *num* columns. Only sequences of space characters containing more than one space character and found immediately before a tabstop are replaced with tabs.

    
- **::textutil::trim** *string* ?*regexp*?
    

    Remove in *string* any leading and trailing substring according to the regular expression *regexp* and return the result as a new string. This apply on any *line* in the string, that is any substring between 2 newline chars, or between the beginning of the string and a newline, or between a newline and the end of the string, or, if the string contain no newline, between the beginning and the end of the string. The regular expression *regexp* defaults to "\[ \\\\t\]+".

    
- **::textutil::trimleft** *string* ?*regexp*?
    

    Remove in *string* any leading substring according to the regular expression *regexp* and return the result as a new string. This apply on any *line* in the string, that is any substring between 2 newline chars, or between the beginning of the string and a newline, or between a newline and the end of the string, or, if the string contain no newline, between the beginning and the end of the string. The regular expression *regexp* defaults to "\[ \\\\t\]+".

    
- **::textutil::trimright** *string* ?*regexp*?
    

    Remove in *string* any trailing substring according to the regular expression *regexp* and return the result as a new string. This apply on any *line* in the string, that is any substring between 2 newline chars, or between the beginning of the string and a newline, or between a newline and the end of the string, or, if the string contain no newline, between the beginning and the end of the string. The regular expression *regexp* defaults to "\[ \\\\t\]+".

    
- **::textutil::trimPrefix** *string* *prefix*
    

    Removes the *prefix* from the beginning of *string* and returns the result. The *string* is left unchanged if it doesn't have *prefix* at its beginning.

    
- **::textutil::trimEmptyHeading** *string*
    

    Looks for empty lines (including lines consisting of only whitespace) at the beginning of the *string* and removes it. The modified string is returned as the result of the command.

    
- **::textutil::untabify** *string* ?*num*?
    

    Untabify the *string* by replacing any tabulation char by a substring of *num* space chars and return the result as a new string. *num* defaults to 8.

    
- **::textutil::untabify2** *string* ?*num*?
    

    Untabify the *string* by replacing any tabulation char by a substring of at most *num* space chars and return the result as a new string. Unlike **textutil::untabify** each tab is not replaced by a fixed number of space characters. The command overlays each line in the *string* with tabstops every *num* columns instead and replaces tabs with just enough space characters to reach the next tabstop. This is the complement of the actions taken by **::textutil::tabify2**. *num* defaults to 8.

    

    There is one asymmetry though: A tab can be replaced with a single space, but not the other way around.

    
- **::textutil::strRepeat** *text num*
    

    The implementation depends on the core executing the package. Used **string repeat** if it is present, or a fast tcl implementation if it is not. Returns a string containing the *text* repeated *num* times. The repetitions are joined without characters between them. A value of *num* <= 0 causes the command to return an empty string.

    
- **::textutil::blank** *num*
    

    A convenience command. Returns a string of *num* spaces.

    
- **::textutil::chop** *string*
    

    A convenience command. Removes the last character of *string* and returns the shortened string.

    
- **::textutil::tail** *string*
    

    A convenience command. Removes the first character of *string* and returns the shortened string.

    
- **::textutil::cap** *string*
    

    Capitalizes the first character of *string* and returns the modified string.

    
- **::textutil::uncap** *string*
    

    The complementary operation to **::textutil::cap**. Forces the first character of *string* to lower case and returns the modified string.

    
- **::textutil::longestCommonPrefixList** *list*
    
- **::textutil::longestCommonPrefix** ?*string*…?
    

    Computes the longest common prefix for either the _string_s given to the command, or the strings specified in the single *list*, and returns it as the result of the command.

    

    If no strings were specified the result is the empty string. If only one string was specified, the string itself is returned, as it is its own longest common prefix.

    

This document, and the package it describes, will undoubtedly contain bugs and other problems. Please report such in the category *textutil* of the [Tcllib Trackers](https://core.tcl.tk/tcllib/reportlist). Please also report any ideas for enhancements you may have for either package and/or documentation.

When proposing code changes, please provide *unified diffs*, i.e the output of **diff -u**.

Note further that *attachments* are strongly preferred over inlined patches. Attachments can be made by going to the **Edit** form of the ticket immediately after its creation, and then using the left-most button in the secondary navigation bar.

# Textutil-man-page-macos

textutil Man Page - macOS - SS64.com

Manipulate text files in various formats.

Syntax

       textutil -info \[_options_\] _file_ ...

       textutil -convert _fmt_ \[_options_\] _file_ ...

       textutil -cat _fmt_ \[_options_\] _file_ ...

       textutil -help \[_options_\] _file_ ...

Key  
     -info Display information about the specified files.

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

*“A lot of people are afraid to say what they want, that's why a lot of people don't get what they want” ~ Madonna*

**Related macOS commands:**

[GetFileInfo](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/getfileinfo.html) - Get attributes of HFS+ files.  
[pr](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/pr.html) - Convert text files for printing.  
[say](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/say.html) - Convert text to audible speech.  
[setfile](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/setfile.html) - Set attributes of HFS+ files.  
[sips](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/sips.html) - Scriptable image processing system.

___

Copyright © 1999-2022 [SS64.com](https://ss64.com/)  
Some rights reserved

# Convert-with-textutil

---

There are a number of ways you can convert a text document to another format, by simply opening it in a text editor like TextEdit and then choosing Save As from the File menu to export it. With TextEdit, you can choose Word, Rich Text, Plain Text, and OpenDocument Text, among others, as the formats in which to save your current file; however, if you are a Terminal user then you might enjoy knowing you can do this right from the command line.

One command-line tool Apple includes in OS X is “textutil” which can be used for a number of manipulations of supported text documents, with one of them being to convert a targeted document to a specified format:

1. Open the Terminal
2. Type the following command, replacing FORMAT with one of txt, html, rtf, rtfd, doc, docx, wordml, odt, or webarchive to specify the desired format:
    

    textutil -convert FORMAT

    
3. Ensure there is a space after the format specification, and then drag your target document to the Terminal window, so the command looks something like this (in this case, converting a webarchive called “mypage” to docx):
    

    textutil -convert docx ~/Desktop/mypage.webarchive

    

When this command is executed, the resulting file will appear in the same folder as the original.

While the use of the Terminal for this might seem unnecessary given the ability to use various word processing programs for converting files, you can use it when managing text documents in automator routines, shell scripts, or applescripts where conversion of these documents might be desired.

One prime use for this routine is to batch-convert files, so if you have a folder of txt documents you would like to convert to docx, then you can do so by using Terminal wildcards with this command to target all or at least a group of desired files in the folder:

textutil -convert docx ~/Desktop/TextDocuments/\*.txt

In the above command, any .txt documents in the folder called “TextDocuments” on the current user’s desktop will be converted to docx format.

The textutil command can be used for these format conversion routines, but also supports a number of other features such as specifying encoding, changing font sizes and type faces, and modifying file metadata.
