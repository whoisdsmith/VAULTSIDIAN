![NewTerminalIconX](https://macissues.comwp-content/uploads/2014/06/NewTerminalIconX-150x150.png)There are a number of ways you can convert a text document to another format, by simply opening it in a text editor like TextEdit and then choosing Save As from the File menu to export it. With TextEdit, you can choose Word, Rich Text, Plain Text, and OpenDocument Text, among others, as the formats in which to save your current file; however, if you are a Terminal user then you might enjoy knowing you can do this right from the command line.

One command-line tool Apple includes in OS X is “textutil” which can be used for a number of manipulations of supported text documents, with one of them being to convert a targeted document to a specified format:

1.  Open the Terminal
2.  Type the following command, replacing FORMAT with one of txt, html, rtf, rtfd, doc, docx, wordml, odt, or webarchive to specify the desired format:
    
    textutil -convert FORMAT
    
3.  Ensure there is a space after the format specification, and then drag your target document to the Terminal window, so the command looks something like this (in this case, converting a webarchive called “mypage” to docx):
    
    textutil -convert docx ~/Desktop/mypage.webarchive
    

When this command is executed, the resulting file will appear in the same folder as the original.

While the use of the Terminal for this might seem unnecessary given the ability to use various word processing programs for converting files, you can use it when managing text documents in automator routines, shell scripts, or applescripts where conversion of these documents might be desired.

One prime use for this routine is to batch-convert files, so if you have a folder of txt documents you would like to convert to docx, then you can do so by using Terminal wildcards with this command to target all or at least a group of desired files in the folder:

textutil -convert docx ~/Desktop/TextDocuments/\*.txt

In the above command, any .txt documents in the folder called “TextDocuments” on the current user’s desktop will be converted to docx format.

The textutil command can be used for these format conversion routines, but also supports a number of other features such as specifying encoding, changing font sizes and type faces, and modifying file metadata.