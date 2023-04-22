# Textutil

---

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

textutil - Procedures to manipulate texts and strings.

The package **textutil** provides commands that manipulate strings or texts (a.k.a. long strings or string with embedded newlines or paragraphs). It is actually a bundle providing the commands of the six packages

in the namespace **textutil**.

The bundle is *deprecated*, and it will be removed in a future release of Tcllib, after the next release. It is recommended to use the relevant sub packages instead for whatever functionality is needed by the using package or application.

The complete set of procedures is described below.

- **::textutil::adjust** *string args*

Do a justification on the *string* according to *args*. The string is taken as one big paragraph, ignoring any newlines. Then the line is formatted according to the options used, and the command return a new string with enough lines to contain all the printable chars in the input string. A line is a set of chars between the beginning of the string and a newline, or between 2 newlines, or between a newline and the end of the string. If the input string is small enough, the returned string won't contain any newlines.

Together with **::textutil::indent** it is possible to create properly wrapped paragraphs with arbitrary indentations.

By default, any occurrence of spaces characters or tabulation are replaced by a single space so each word in a line is separated from the next one by exactly one space char, and this forms a *real* line. Each *real* line is placed in a *logical* line, which have exactly a given length (see **\-length** option below). The *real* line may have a lesser length. Again by default, any trailing spaces are ignored before returning the string (see **\-full** option below). The following options may be used after the *string* parameter, and change the way the command place a *real* line in a *logical* line.

￼- \-full *boolean*

files.

Textutil first appeared in OS X 10.4

**Examples**:

Display information about foo.rtf.  

```
$ textutil -info foo.rtf
```

Convert foo.rtf into foo.html.  

```
$ textutil -convert html foo.rtf
```

Convert foo.txt into foo.rtf, using Times 10 for the font.  

```
$ textutil -convert rtf -font Times -fontsize 10 foo.txt
```

Load all RTF files in the current directory, concatenate their contents, and write the result out as index.html with the HTML title set to Several Files".

```
$ textutil -cat html -title "Several Files" -output index.html \*.rtf
```

Create a .txt file for each .doc file in the directory.  

```
$ textutil -convert txt \*.doc
```

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

# Convert with Textutil

---

There are a number of ways you can convert a text document to another format, by simply opening it in a text editor like TextEdit and then choosing Save As from the File menu to export it. With TextEdit, you can choose Word, Rich Text, Plain Text, and OpenDocument Text, among others, as the formats in which to save your current file; however, if you are a Terminal user then you might enjoy knowing you can do this right from the command line.

One command-line tool Apple includes in OS X is “textutil” which can be used for a number of manipulations of supported text documents, with one of them being to convert a targeted document to a specified format:

1. Open the Terminal
2. Type the following command, replacing FORMAT with one of txt, html, rtf, rtfd, doc, docx, wordml, odt, or webarchive to specify the desired format:

```
textutil -convert FORMAT
```

1. Ensure there is a space after the format specification, and then drag your target document to the Terminal window, so the command looks something like this (in this case, converting a webarchive called “mypage” to docx):

```
textutil -convert docx ~/Desktop/mypage.webarchive
```

When this command is executed, the resulting file will appear in the same folder as the original.

While the use of the Terminal for this might seem unnecessary given the ability to use various word processing programs for converting files, you can use it when managing text documents in automator routines, shell scripts, or applescripts where conversion of these documents might be desired.

One prime use for this routine is to batch-convert files, so if you have a folder of txt documents you would like to convert to docx, then you can do so by using Terminal wildcards with this command to target all or at least a group of desired files in the folder:

```
textutil -convert docx ~/Desktop/TextDocuments/\*.txt
```

In the above command, any .txt documents in the folder called “TextDocuments” on the current user’s desktop will be converted to docx format.

The textutil command can be used for these format conversion routines, but also supports a number of other features such as specifying encoding, changing font sizes and type faces, and modifying file metadata.

---
