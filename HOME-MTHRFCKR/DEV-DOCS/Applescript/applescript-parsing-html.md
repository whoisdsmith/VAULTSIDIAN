## Parsing HTML

The process of reading an HTML file is no different than the process of reading a standard text file—see [Reading a File](https://developer.apple.com/library/archive/documentation/LanguagesUtilities/Conceptual/MacAutomationScriptingGuide/ParseHTML.html#//apple_ref/doc/uid/TP40016239-CH50-SW1ReadandWriteFiles.html#//apple_ref/doc/uid/TP40016239-CH58-SW2) to learn how to do it. However, it’s often necessary to extract specific bits of information from HTML files, such as links, images, and table data, for further processing.

### Parsing an HTML File

The handler in Listing 33-1 extracts specific tags and their content from HTML text. Provide an HTML file to read, a closing and ending tag, and indicate whether to return only content between the tags, or the tags with their enclosed content. If no closing tag is provided, the handler extracts the opening tag data only. This feature could be used to extract image tags from HTML content, for example, which don’t have a separate closing tag.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=on%20parseHTMLFile%28theFile%2C%20theOpeningTag%2C%20theClosingTag%2C%20returnContentsOnly%29%0A%20%20%20%20try%0A%20%20%20%20%20%20%20%20set%20theFile%20to%20theFile%20as%20string%0A%20%20%20%20%20%20%20%20set%20theFile%20to%20open%20for%20access%20file%20theFile%0A%20%20%20%20%20%20%20%20set%20theCombinedResults%20to%20%22%22%0A%20%20%20%20%20%20%20%20set%20theCurrentOpeningTag%20to%20%22%22%0A%20%20%20%20%20%20%20%20repeat%0A%20%20%20%20%20%20%20%20%20%20%20%20read%20theFile%20before%20%22%3C%22%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20theCurrentTag%20to%20read%20theFile%20until%20%22%3E%22%0A%20%20%20%20%20%20%20%20%20%20%20%20if%20theCurrentTag%20does%20not%20start%20with%20%22%3C%22%20then%20set%20theCurrentTag%20to%20%28%22%3C%22%20%26%20theCurrentTag%29%20as%20string%0A%20%20%20%20%20%20%20%20%20%20%20%20if%20theCurrentTag%20begins%20with%20theOpeningTag%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theCurrentOpeningTag%20to%20theCurrentTag%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20if%20theClosingTag%20is%20%22%22%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20if%20theCombinedResults%20is%20%22%22%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theCombinedResults%20to%20theCombinedResults%20%26%20theCurrentOpeningTag%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20else%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theCombinedResults%20to%20theCombinedResults%20%26%20return%20%26%20theCurrentOpeningTag%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20end%20if%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20else%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theTextBuffer%20to%20%22%22%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20repeat%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theTextBuffer%20to%20theTextBuffer%20%26%20%28read%20theFile%20before%20%22%3C%22%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theTagBuffer%20to%20read%20theFile%20until%20%22%3E%22%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20if%20theTagBuffer%20does%20not%20start%20with%20%22%3C%22%20then%20set%20theTagBuffer%20to%20%28%22%3C%22%20%26%20theTagBuffer%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20if%20theTagBuffer%20is%20theClosingTag%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20if%20returnContentsOnly%20is%20false%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theTextBuffer%20to%20theCurrentOpeningTag%20%26%20theTextBuffer%20%26%20theTagBuffer%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20end%20if%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20if%20theCombinedResults%20is%20%22%22%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theCombinedResults%20to%20theCombinedResults%20%26%20theTextBuffer%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20else%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theCombinedResults%20to%20theCombinedResults%20%26%20return%20%26%20theTextBuffer%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20end%20if%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20exit%20repeat%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20else%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20set%20theTextBuffer%20to%20theTextBuffer%20%26%20theTagBuffer%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20end%20if%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20end%20repeat%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20end%20if%0A%20%20%20%20%20%20%20%20%20%20%20%20end%20if%0A%20%20%20%20%20%20%20%20end%20repeat%0A%20%20%20%20%20%20%20%20close%20access%20theFile%0A%20%20%20%20on%20error%20theErrorMessage%20number%20theErrorNumber%0A%20%20%20%20%20%20%20%20try%0A%20%20%20%20%20%20%20%20%20%20%20%20close%20access%20theFile%0A%20%20%20%20%20%20%20%20end%20try%0A%20%20%20%20%20%20%20%20if%20theErrorNumber%20is%20not%20-39%20then%20return%20false%0A%20%20%20%20end%20try%0A%20%20%20%20return%20theCombinedResults%0Aend%20parseHTMLFile%0A)

**Listing 33-1**AppleScript: Handler that parses an HTML file for specific tagged content

1.  `on parseHTMLFile(theFile, theOpeningTag, theClosingTag, returnContentsOnly)`
2.  `try`
3.  `set theFile to theFile as string`
4.  `set theFile to open for access file theFile`
5.  `set theCombinedResults to ""`
6.  `set theCurrentOpeningTag to ""`
7.  `repeat`
8.  `read theFile before "<"`
9.  `set theCurrentTag to read theFile until ">"`
10.  `if theCurrentTag does not start with "<" then set theCurrentTag to ("<" & theCurrentTag) as string`
11.  `if theCurrentTag begins with theOpeningTag then`
12.  `set theCurrentOpeningTag to theCurrentTag`
13.  `if theClosingTag is "" then`
14.  `if theCombinedResults is "" then`
15.  `set theCombinedResults to theCombinedResults & theCurrentOpeningTag`
16.  `else`
17.  `set theCombinedResults to theCombinedResults & return & theCurrentOpeningTag`
18.  `end if`
19.  `else`
20.  `set theTextBuffer to ""`
21.  `repeat`
22.  `set theTextBuffer to theTextBuffer & (read theFile before "<")`
23.  `set theTagBuffer to read theFile until ">"`
24.  `if theTagBuffer does not start with "<" then set theTagBuffer to ("<" & theTagBuffer)`
25.  `if theTagBuffer is theClosingTag then`
26.  `if returnContentsOnly is false then`
27.  `set theTextBuffer to theCurrentOpeningTag & theTextBuffer & theTagBuffer`
28.  `end if`
29.  `if theCombinedResults is "" then`
30.  `set theCombinedResults to theCombinedResults & theTextBuffer`
31.  `else`
32.  `set theCombinedResults to theCombinedResults & return & theTextBuffer`
33.  `end if`
34.  `exit repeat`
35.  `else`
36.  `set theTextBuffer to theTextBuffer & theTagBuffer`
37.  `end if`
38.  `end repeat`
39.  `end if`
40.  `end if`
41.  `end repeat`
42.  `close access theFile`
43.  `on error theErrorMessage number theErrorNumber`
44.  `try`
45.  `close access theFile`
46.  `end try`
47.  `if theErrorNumber is not -39 then return false`
48.  `end try`
49.  `return theCombinedResults`
50.  `end parseHTMLFile`

Listing 33-2 shows how to call the handler in Listing 33-1 to extract all hyperlinks within a chosen HTML file.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=set%20theFile%20to%20choose%20file%20with%20prompt%20%22Select%20an%20HTML%20file%3A%22%0AparseHTMLFile%28theFile%2C%20%22%3CA%20HREF%3D%22%2C%20%22%3C%2FA%3E%22%2C%20false%29)

**Listing 33-2**AppleScript: Calling a handler to parse an HTML file for URLs

1.  `set theFile to choose file with prompt "Select an HTML file:"`
2.  `parseHTMLFile(theFile, "<A HREF=", "</A>", false)`
3.  `--> Example of Result: "<A HREF="http://www.apple.com/fileA.html">Click here to view fileA.</A>`
4.  `<A HREF="http://www.apple.com/fileB.html">Click here to view fileB.</A>"`

Listing 33-3 shows how to call the handler in Listing 33-1 to extract the destinations of all hyperlinks within a chosen HTML file.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=set%20theFile%20to%20choose%20file%20with%20prompt%20%22Select%20an%20HTML%20file%3A%22%0AparseHTMLFile%28theFile%2C%20%22%3CA%20HREF%3D%22%2C%20%22%3C%2FA%3E%22%2C%20true%29)

**Listing 33-3**AppleScript: Calling a handler to parse an HTML file for URLs

1.  `set theFile to choose file with prompt "Select an HTML file:"`
2.  `parseHTMLFile(theFile, "<A HREF=", "</A>", true)`
3.  `--> Example of Result: "Click here to view fileA.`
4.  `Click here to view fileB."`

Listing 33-4 shows how to call the handler in Listing 33-1 to extract all images within a chosen HTML file.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=set%20theFile%20to%20choose%20file%20with%20prompt%20%22Select%20an%20HTML%20file%3A%22%0AparseHTMLFile%28theFile%2C%20%22%3CIMG%20%22%2C%20%22%22%2C%20false%29%0A)

**Listing 33-4**AppleScript: Calling a handler to parse an HTML file for images

1.  `set theFile to choose file with prompt "Select an HTML file:"`
2.  `parseHTMLFile(theFile, "<IMG ", "", false)`
3.  `--> Example of Result: "<IMG SRC="gfx/clipboard.gif" BORDER="0">`
4.  `<IMG SRC="printer_stopped.gif" ALIGN=TOP WIDTH="32" HEIGHT="32" BORDER="0">`
5.  `<IMG SRC="printer_on.gif" ALIGN=TOP WIDTH="32" HEIGHT="32" BORDER="0">"`

Listing 33-5 shows how to call the handler in Listing 33-1 to extract any tables within a file.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=set%20theFile%20to%20choose%20file%20with%20prompt%20%22Select%20an%20HTML%20file%3A%22%0AparseHTMLFile%28theFile%2C%20%22%3CTABLE%22%2C%20%22%3C%2FTABLE%3E%22%2C%20false%29%0A)

**Listing 33-5**AppleScript: Calling a handler to parse an HTML file for tables

1.  `set theFile to choose file with prompt "Select an HTML file:"`
2.  `parseHTMLFile(theFile, "<TABLE", "</TABLE>", false)`
3.  `--> Example of Result:"<TABLE WIDTH="440">`
4.  `<TR>`
5.  `<TD ALIGN="CENTER" VALIGN="TOP">`
6.  `<IMG SRC="gfx/clipboard.gif" BORDER="0">`
7.  `</TD>`
8.  `</TR>`
9.  `</TABLE>"`

### Parsing an HTML Tag

The handler in Listing 33-6 extracts the contents—first instance of text contained within quotes—of an HTML tag.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=on%20parseHTMLTag%28theHTMLTag%29%0A%20%20%20%20set%20AppleScript%27s%20text%20item%20delimiters%20to%20%22%5C%22%22%0A%20%20%20%20set%20theHTMLTagElements%20to%20text%20items%20of%20theHTMLTag%0A%20%20%20%20set%20AppleScript%27s%20text%20item%20delimiters%20to%20%22%22%0A%20%20%20%20if%20length%20of%20theHTMLTagElements%20is%20greater%20than%201%20then%20return%20item%202%20of%20theHTMLTagElements%0A%20%20%20%20return%20%22%22%0Aend%20parseHTMLTag)

**Listing 33-6**AppleScript: Handler that parses an HTML tag for content

1.  `on parseHTMLTag(theHTMLTag)`
2.  `set AppleScript's text item delimiters to "\""`
3.  `set theHTMLTagElements to text items of theHTMLTag`
4.  `set AppleScript's text item delimiters to ""`
5.  `if length of theHTMLTagElements is greater than 1 then return item 2 of theHTMLTagElements`
6.  `return ""`
7.  `end parseHTMLTag`

Listing 33-7 shows how to call the handler in Listing 33-6 to extract the destination of a hyperlink tag.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=set%20theHTMLTag%20to%20%22%3CA%20HREF%3D%5C%22http%3A%2F%2Fwww.apple.com%2FfileA.html%5C%22%3EClick%20here%20to%20view%20fileA.%3C%2FA%3E%22%0AparseHTMLTag%28theHTMLTag%29)

**Listing 33-7**AppleScript: Calling a handler to parse an HTML tag for content

1.  `set theHTMLTag to "<A HREF=\"http://www.apple.com/fileA.html\">Click here to view fileA.</A>"`
2.  `parseHTMLTag(theHTMLTag)`
3.  `--> Result: "http://www.apple.com/fileA.html"`