# Bare Bones Software | BBEdit Expert Preferences

---

There are a number of behaviors in BBEdit for which there are no UI controls in the Preferences window; this is typically because the settings are so obscure that placing them in the Preferences window would just make it complicated. In fact, some of these settings *were* in the Preferences window, and have been removed in order to simplify the interface; in such cases, any changes you made previously will be honored, even though the UI in the Preferences window is gone.

**Note:** Adjusting the settings described here involves using the Unix command line (in the Terminal or a suitable replacement, or in a BBEdit shell worksheet). Most changes will not have any immediate visible effect, but will instead take effect the next time you perform a relevant action, or, at the latest, after quitting and restarting BBEdit.

#### Table of contents:

-   [Clippings, Editing and Text Completion](http://www.barebones.com/support/bbedit/ExpertPreferences.html#clip)
-   [FTP/SFTP](http://www.barebones.com/support/bbedit/ExpertPreferences.html#ftp)
-   [File Comparison](http://www.barebones.com/support/bbedit/ExpertPreferences.html#diff)
-   [HTML Tools](http://www.barebones.com/support/bbedit/ExpertPreferences.html#html)
-   [Interacting with Other Applications](http://www.barebones.com/support/bbedit/ExpertPreferences.html#inte)
-   [Language Support](http://www.barebones.com/support/bbedit/ExpertPreferences.html#lang)
-   [Projects](http://www.barebones.com/support/bbedit/ExpertPreferences.html#proj)
-   [Reading and Writing Files](http://www.barebones.com/support/bbedit/ExpertPreferences.html#read)
-   [Sleep and Auto-Save](http://www.barebones.com/support/bbedit/ExpertPreferences.html#slee)
-   [Source Control](http://www.barebones.com/support/bbedit/ExpertPreferences.html#sour)
-   [Text Display and Coloring](http://www.barebones.com/support/bbedit/ExpertPreferences.html#textd)
-   [Text Search and Replace](http://www.barebones.com/support/bbedit/ExpertPreferences.html#texts)
-   [Windows and UI Tweaking](http://www.barebones.com/support/bbedit/ExpertPreferences.html#wind)
-   [Miscellaneous](http://www.barebones.com/support/bbedit/ExpertPreferences.html#misc)

---

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Clippings, Editing and Text Completion

-   BBEdit supports "camel case" navigation: press Control-left-arrow or Control-right-arrow to jump to the next (or previous) transition from lower-case to upper-case characters (or a word boundary, whichever comes first).
    
    Note that this use of Control-left-arrow and Control-right-arrow replaces the pre-8.5 behavior of using these key combinations to scroll horizontally. If you prefer the old behavior, you can do the following from the command line:
    
    defaults write com.barebones.bbedit Editor\_ControlArrowCamelCase -bool NO
    
    defaults write com.barebones.bbedit Editor\_ControlArrowHScroll -bool YES
    
-   When using "camel case" navigation (see above), BBEdit does not include underscores ( `_` ) when moving or extending the selection range. If you would prefer that it do so, you can turn this on:
    
    defaults write com.barebones.bbedit CamelCaseNavigationIncludesUnderscores -bool YES
    
-   If there is a partial word to the immediate left of the insertion point, the "Insert Clipping..." command will attempt to autocomplete that word based clipping names in the current and universal set (using a "begins with" style match.) If you wish to disable the autocompletion:
    
    defaults write com.barebones.bbedit UseClippingsForCompletion -bool NO
    
-   When you backspace from the insertion point, BBEdit will delete a tab stop's worth of spaces if there are only spaces (and tabs) between the insertion point and the start of the line on which you're editing. This may be disabled by an expert preference if desired:
    
    defaults write com.barebones.bbedit Editor\_DeleteIndentationWhitespaceToTabStop -bool NO
    
-   Automatic word counting is disabled for documents over a set size threshold, in order to avoid needless delays when working on very large documents. The factory default is 16M characters, but you may change this limit as desired using the following expert preference:
    
    defaults write com.barebones.bbedit Editor\_AutoWordCountSizeThreshold -int 16777216
    
    #Setting it to zero disables the limit check entirely.
    
-   Since "Find All Misspelled Words" is pretty much pointless on files over a certain size, the maximum amount of text checked by this command is limited to 1M (1024 squared) characters. This may be adjusted with an expert preference:
    
    defaults write com.barebones.bbedit Editor\_SpellCheckLengthLimit -int NN
    
    where "NN" is some decimal value. Use `-int 0` to suppress the limit altogether.
    
-   Text completions that depend on examining the document's contents (both for tokens in the document, and for possible completions from the system spelling checker) are now skipped when the document is above a certain size. The cutoff can be adjusted:
    
    defaults write com.barebones.bbedit MaxDocumentLengthForCompletionTokenizer -int NN
    
    where "NN" is some decimal value. Use `-int 0` to suppress the limit altogether.
    
-   By default, the "Balance" command (or double-clicking on a delimiter to balance) does not include the delimiters in the resulting selection. If you would like for it to do so:
    
    defaults write com.barebones.bbedit BalanceIncludesDelimiters -bool YES
    
-   When using the Un/Comment command, if nothing is selected, BBEdit will use the line comment delimiter to comment (or uncomment) the entire line. If you would prefer that BBEdit insert the line-comment delimiter at the insertion point instead:
    
    defaults write com.barebones.bbedit CommentWholeLineWithInsertionPoint -bool NO
    
-   By default, the "Shift Right" command on the Text menu will not add indentation to lines that are empty or consist entirely of white space. If you would prefer to indent every line, regardless of its whitespace-only nature, you can do so:
    
    defaults write com.barebones.bbedit AllowShiftRightToIndentWhitespaceOnlyLines -bool YES
    
    Note that this preference can be set per-language in the usual fashion, by appending the language's name to the preference key:
    
    defaults write com.barebones.bbedit AllowShiftRightToIndentWhitespaceOnlyLines\_C++ -bool YES
    
-   When you use the right-arrow key to navigate over a closing delimiter (right paren/brace/bracket/curly quote), the opening delimiter will be briefly highlighted. If you wish to turn this off, there's an expert pref:
    
    defaults write com.barebones.bbedit FlashBalancePointsWhenNavigating -bool NO
    
      
    
-   If you find that you frequently need to bring in text which contains combining Unicode characters (as are frequently found in PDFs generated on other platforms, for example), it can be desirable to preprocess the combining characters into one composed character where possible. This is **not** a general need, but if you run into it often enough, you can tell BBEdit to combine the characters for you:
    
    defaults write com.barebones.bbedit PrecomposeUnicodeWhenPasting -bool YES
    
    (Despite the name, the precomposition is done when BBEdit imports the Clipboard from other applications, not when the paste is actually done.)
    
    Note that this requires an additional copy of the Clipboard when the application imports the text, and for very large pastes, there may be a noticeable delay while the text gets precomposed. Thus, you should only turn on this setting when you are frequently working with text that contains combining Unicode characters.
    
-   The progressive (BRIEF compatible) behavior of the Home and End keys operates within a specific time period; if you wait longer than that, the behavior state resets. The factory default timeout period is ten seconds; if you wish to modify this, you can do so as follows:
    
    defaults write com.barebones.bbedit BRIEFStateTimeout -float x.y
    
    \# "x.y" is some floating point value greater than zero
    
-   If you like, you can use the Tab key to trigger text completion:
    
    defaults write com.barebones.bbedit UseTabKeyAsCompletionTrigger -bool YES
    
-   When performing an Undo or Redo and the selection range changes, the Undo/Redo operation will select the affected text, rather than updating the Undo/Redo state to include the actual current selection range. If however you prefer the classic behavior (as implemented from the beginning of time up through BBEdit 11.6), you may obtain that as follows:
    
    defaults write com.barebones.bbedit LegacyUndoSelectionBehavior -bool YES
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### FTP/SFTP

-   If you have problems with your SSH server closing the connection after a period of non-use (which will subsequently cause errors in BBEdit), you can tell BBEdit to send a periodic "keepalive" message to while connected to the server.
    
    This is configurable per host, per domain, or globally. Determining the appropriate value may require some experimentation, but 90 seconds is probably a good starting point.
    
    \# only for "foobar.example.com"
    
    defaults write com.barebones.bbedit SSHServerKeepaliveInterval:foobar.example.com -int 90
    
    \# only for servers in "example.com"
    
    defaults write com.barebones.bbedit SSHServerKeepaliveInterval:example.com -int 90
    
    \# global preference
    
    defaults write com.barebones.bbedit SSHServerKeepaliveInterval -int 90
    
    We recommend that that you adjust this setting per host whenever possible, rather than globally or per-domain.
    
-   Settings are available for disabling passive FTP, in order to deal with hosts that misbehave when sent the `PASV` command.
    
    Passive FTP can be disabled per host, per domain, or globally:
    
    \# only for "foobar.example.com"
    
    defaults write com.barebones.bbedit DisablePassiveFTP:foobar.example.com -bool YES
    
    \# only for servers in "example.com"
    
    defaults write com.barebones.bbedit DisablePassiveFTP:example.com -bool YES
    
    \# global preference
    
    defaults write com.barebones.bbedit DisablePassiveFTP -bool YES
    
    We recommand that that you disable passive FTP per host whenever possible, rather than globally or per-domain.
    
-   Some servers don't work correctly when SSH compression is enabled. To work around this, SSH compression can be disabled per host, per domain, or globally:
    
    \# only for "foobar.example.com"
    
    defaults write com.barebones.bbedit EnableSSHCompression:foobar.example.com -bool NO
    
    \# only for servers in "example.com"
    
    defaults write com.barebones.bbedit EnableSSHCompression:example.com -bool NO
    
    \# global preference
    
    defaults write com.barebones.bbedit EnableSSHCompression -bool NO
    
    Our recommendation is that you disable per host in preference to globally or per-domain.
    
-   Most of the time, the default timeout for connecting to an SFTP server will suffice; however, if the server is heavily loaded it may take longer to respond. To adjust the SFTP connection timeout:
    
    \# set the timeout to 20 seconds -- note that "-int" is required
    
    defaults write com.barebones.bbedit SFTPConnectionTimeout -int 20
    
-   On FTP servers, when using ‘Show items starting with “.”,’ the FTP server may return the \`.\` and \`..\` items as part of the listing. This is normal, but if you don't want to see these items, you can hide them:
    
    defaults write com.barebones.bbedit FTPShowParentDir -bool NO
    
-   Ordinarily, BBEdit will use the `MLSD` command to obtain directory listings if the server supports it; and will fall back to more primitive methods if not. On some servers, however, `MLSD` works, but does not return the same results as the older methods. Therefore, there is a method to disable use of `MLSD`.
    
    `MLSD` can be disabled per host, per domain, or globally:
    
    \# only for "foobar.example.com"
    
    defaults write com.barebones.bbedit FTPDisableMLSD:foobar.example.com -bool YES
    
    \# only for servers in "example.com"
    
    defaults write com.barebones.bbedit FTPDisableMLSD:example.com -bool YES
    
    \# global preference
    
    defaults write com.barebones.bbedit FTPDisableMLSD -bool YES
    
    We recommand that that you disable `MLSD` per host whenever possible, rather than globally or per-domain.
    
    **Note:** In some cases, the server may be configured to never list files whose names begin with a period (`.`). In that case, there is nothing you can do in BBEdit to have these files listed in FTP/SFTP browsers, and you will need to contact your server administrator or hosting service to have the server configured appropriately.
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### File Comparison

-   When comparing text files, BBEdit will canonicalize RCS keywords to their unexpanded state, so that the values of RCS keywords are not significant to the differences calculations. If you wish, you can disable this, so that any chance in the RCS keywords on a line will cause the line to appear in the differences:
    
    \# Ignore variances in RCS keyword values when comparing
    
    defaults write com.barebones.bbedit Diff\_IgnoreRCSKeywords -bool NO
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### HTML Tools

-   When doing Check Syntax, Check Links, Update, or Update Images on a folder (including a web site), BBEdit will skip XML files (that is, files determined to be XML either by mapping their file name extensions, or by inspection of their contents). If you prefer to include such files:
    
    defaults write com.barebones.bbedit MarkupToolsMisc\_SkipXMLFilesWhenScanningFolders -bool NO
    
-   Ordinarily, BBEdit will generate XHTML-style markup in HTML5 documents (those with a "<!DOCTYPE HTML>" declaration). If you wish, you can suppress this:
    
    defaults write com.barebones.bbedit UseXMLMarkupRulesForHTML5 -bool NO
    
-   When generating image markup as a result of dropping an image file into an HTML document, BBEdit will generate an "alt" attribute for the image tag, whose value is the file's name. If you would prefer for the "alt" attribute to be omitted (which will result in an error when checking syntax), you can disable this:
    
    defaults write com.barebones.bbedit HTMLImageMarkupUsesFileNameForAlt -bool NO
    
-   When you drop an image file into an HTML document to generate an image tag, BBEdit will generate "width" and "height" tags based on information in the file itself. If you would prefer to omit these:
    
    defaults write com.barebones.bbedit HTMLImageMarkupCreatesSizeAttributes -bool NO
    
-   If `HTMLImageMarkupCreatesSizeAttributes` is turned on, you can instruct BBEdit to generate inline styles for image sizes, instead of height and width:
    
    defaults write com.barebones.bbedit HTMLImageMarkupUseInlineStyleForImageSize -bool YES
    
-   When you invoke the Markup Panel to create a new tag, it will automatically fill in attribute names for "promoted" attributes. If there are any attributes that you don't want to be present in the generated markup, just leave their values blank, and the panel will omit them (unless the attributes are required).
    
    If you wish, you can suppress the auto fill with an expert preference:
    
    defaults write com.barebones.bbedit MarkupPanelAutoPrefillRecommendedAttributeNames -bool NO
    
    Turning off the auto fill will cause the "gear" to appear in the markup panel, and clicking it will manually fill in the promoted attribues for you.
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Interacting with Other Applications

-   if Xcode is running, Open Selection and Open File by Name will ask it for a path to the file name; if something useful comes back, BBEdit will open it. If for some reason you are using Xcode but don't want BBEdit to do this, you can turn it off:
    
    defaults write com.barebones.bbedit AskXcodeForOpenFileByName -bool NO
    
-   By default, BBEdit will open AppleScript files using whatever application the OS claims is capable of doing so. If you wish to override this, change the "ScriptEditorBundleID" preference to the bundle ID of your preferred script editor. For example, to set the script editor to Script Debugger:
    
    defaults write com.barebones.bbedit ScriptEditorBundleID com.latenightsw.ScriptDebugger
    
-   The "Run in Terminal" and "Go Here in Terminal" commands will use Apple's "Terminal" application by default. If you would like to use a different one:
    
    defaults write com.barebones.bbedit TerminalBundleID -string "com.example.TerminalAppBundleID"
    
    (Use the actual terminal's bundle ID in place of "com.example.TerminalAppBundleID"…)
    
-   If [Dash](http://kapeli.com/dash) is installed, BBEdit will use it for "Find in Reference", in preference to any predefined or custom reference lookup URLs. This can be controlled via an expert preference, on a per-language basis if desired:
    
    defaults write com.barebones.bbedit UseDashForReferenceLookups -bool NO
    
    \# turn off Dash support entirely
    
    defaults write com.barebones.bbedit UseDashForReferenceLookups\_Ruby -bool NO
    
    #turn off Dash support only for Ruby
    
    You could, if you wanted, turn off Dash support by default and then enable it for specific languages, e.g.:
    
    defaults write com.barebones.bbedit UseDashForReferenceLookups -bool NO
    
    \# turn off Dash support entirely
    
    defaults write com.barebones.bbedit UseDashForReferenceLookups\_C++ -bool YES
    
    #turn on Dash support only for C++
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Language Support

-   Most of the factory supplied language modules generate fold ranges for any brace-delimited block that has at least one line. You can adjust this from the command line, using a language-specific preference key, which consists of "MinimumLinesForBlockFold\_" (note the underscore) and the language name; for example:
    
    defaults write com.barebones.bbedit MinimumLinesForBlockFold\_Objective-C
    
    defaults write com.barebones.bbedit MinimumLinesForBlockFold\_Objective-C++ 4
    
    defaults write com.barebones.bbedit MinimumLinesForBlockFold\_JavaScript 4
    
-   Here are some language-specific settings for PHP. The settings with "Opaque" in their names refer to how certain structures are treated when scanning PHP code that's embedded in HTML; when the preference is YES (the factory default in most cases), the corresponding structure is skipped so that any syntactic elements within it are ignored. When the preference is NO, the comment/string/etc delimiters are ignored and the structure's contents are interpreted. (This is generally not desirable, but currently preserved for legacy compatibility.)
    
    defaults write com.barebones.bbedit OpaqueStrings\_PHP -bool NO
    
    defaults write com.barebones.bbedit OpaqueBlockComments\_PHP -bool NO
    
    defaults write com.barebones.bbedit OpaqueLineComments\_PHP -bool NO
    
    defaults write com.barebones.bbedit OpaqueHereDoc\_PHP -bool NO
    
    If you want variables to appear in the function menu in PHP documents:
    
    defaults write com.barebones.bbedit ShowVariablesInFunctionList\_PHP -bool YES
    
-   When the active document is either a source or a header file, the "Open Counterpart" command will now search the siblings of this file's parent for eligible counterparts. By default, BBEdit will only search in such folders if their names match one of the following patterns (including wildcards): \`inc\*\`, \`source\`, \`src\`, or \`\*priv\*\`. If you wish to add additional qualifying names, you may do so by setting "CounterpartSiblingSearchNames" to contain a comma-delimited list of folder name patterns:
    
    defaults write com.barebones.bbedit CounterpartSiblingSearchNames -string "foo\*, bar, \*mumble\*, wumpus"
    
    (Any whitespace surrounding the provided names will be stripped.)
    
-   When running a Python script, if `python3` is anywhere in your `$PATH`, BBEdit will use it *instead of* `python`. While this is generally useful in a teaching environment, if you are using a custom Python installation (such as Anaconda), it may prove inconvenient. In that case, disabling automatic use of `python3` will help:
    
    defaults write com.barebones.bbedit RunUsingPython3 -bool NO
    
-   The Python language module will use `flake8` for syntax checking, if you have it installed and it is available in your `$PATH`. If you want to disable this and use Python’s built-in syntax checking:
    
    defaults write com.barebones.bbedit UseFlakeForPythonSyntaxChecking -bool NO
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Projects

-   In project windows, the file list does not accept keyboard focus by default, unless the editing view is hidden. You can modify this so that the file list gets the focus whenever you click on it:
    
    defaults write com.barebones.bbedit ProjectsListCanAcquireKeyboardFocus -bool YES
    
-   Project windows will ordinarily open an item in the file list for editing when you click on it and the editing view is visible. To require a double-click:
    
    defaults write com.barebones.bbedit ProjectsOpenItemsOnSingleClick -bool NO
    
-   BBEdit will not automatically reveal documents in the project list when you select them; `View => Reveal in Project List` works for this purpose. If you want automatic revealing:
    
    defaults write com.barebones.bbedit AutoRevealSelectedDocumentInProjectList -bool YES
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Reading and Writing Files

-   By default, PDFs are considered text files and so may be opened and searched along with all other text files. To have PDFs treated as a special file type (they will be ignored for any operation that requires a text file):
    
    defaults write com.barebones.bbedit OpenPDFsAsText -bool NO
    
    Changes to this setting will take effect the next time you start BBEdit.
    
-   To control whether BBEdit warns you when opening a malformed UTF-8 file:
    
    defaults write com.barebones.bbedit WarnMalformedUTF8 -bool YES
    
-   Ordinarily, BBEdit will only ask you to choose a file's encoding when it can't otherwise figure out what the encoding is, and your "if the file's encoding can't be guessed" preference is a UTF-8 or UTF-16 variant. This should be fine for general use, but if for some reason you *always* want BBEdit to ask you when it can't guess a file's encoding, even if your preference would do the job, you can:
    
    defaults write com.barebones.bbedit AskForUnguessableFileEncoding -bool YES
    
-   Beginning with version 8.0, BBEdit stores document state (window position and various settings) in a central repository in your BBEdit preferences folder. If you wish, you can ask BBEdit to store document state with the document's file:
    
    defaults write com.barebones.bbedit UseResourceForkForDocumentState -bool YES
    
    BBEdit will use an extended attribute for this purpose.
    
-   By default, BBEdit will not store document state for documents located in any of the canonical locations for temporary files. (This also includes the "svn-commit.tmp" files used for Subversion commits.) If desired, you can change this::
    
    defaults write com.barebones.bbedit SaveDocumentStateForTempFiles -bool YES
    
-   By default, BBEdit will avoid writing extended attributes to volumes which don't natively support them (i.e. to avoid creating the .\_FILE) when it is safe to do so (i.e. we'll be able to re-open the document correctly later.) If desired, you can fine-tune this behavior:
    
    defaults write com.barebones.bbedit WriteExtendedAttributes *<value>*
    
    “*value*” should be one of the following:
    
    -   *Always*: Always write the HFS file type and creator (the pre-8.6 behavior)
        
    -   *Never*: Never set the HFS file type and creator (even if the document’s volume supports it).
        
    -   *Smart*: Write HFS file type and creator only if the document’s volume supports it
        
-   For text documents whose size exceeds a certain threshold (expressed in bytes, factory default 1MB), BBEdit will ignore the Soft Wrap Text preference and leave wrapping off in order to improve the performance of opening very large files. The threshold may be adjusted if desired:
    
    defaults write com.barebones.bbedit Editor\_SoftWrapLengthThreshold -int 1048576
    
    If you set the limit to zero, BBEdit will always honor the Soft Wrap Text preference, even in situations where soft-wrapping a large file may cause it to take a very long time to open.
    
-   The "Text Files Only" filtering in project lists and disk browsers looks inside of files if necessary, for improved filtering accuracy. This may be disabled, if desired:
    
    defaults write com.barebones.bbedit InspectTextFileContentsForListFiltering -bool NO
    
-   When inspecting files to determine whether they're Zip archives for file filtering and searching, BBEdit will ordinarily only inspect the contents of the file if its metadata does not indicate that it’s a Zip archive. If for some reason you have files whose metadata indicates that they're Zip archives, but aren't really, you can use this setting to tell BBEdit to always inspect Zip archive contents:
    
    defaults write com.barebones.bbedit InspectZipArchiveContentsForFileFiltering -bool YES
    
    Note that you must quit and relaunch BBEdit for a change to this setting to take effect.
    
-   BBEdit makes a reasonable guess at a filename extension when using "Save As" for a new document. You can also set the preferred extension on a per-language basis:
    
    defaults write com.barebones.bbedit PreferredFilenameExtension\_<LanguageName> -string "abc"
    
    Replace `<LanguageName>` with the actual language name; for example:
    
    defaults write com.barebones.bbedit PreferredFilenameExtension\_C++ -string "cxx"
    
    defaults write com.barebones.bbedit PreferredFilenameExtension\_YAML -string "yaml"
    
    Note that the extension you specify should **not** include the leading period.
    
-   macOS works best when you specify a file name extension when saving a new document. If you don't, the OS will often behave unpredictably when you double-click on the resulting file.
    
    For this reason, when creating a new file which has no filename extension, BBEdit will add an extended attribute which tells the OS to open that file in BBEdit specifically. If you wish, you can change the assigned application for that file using the “Open with:” setting the Finder's “Get Info” window.
    
    You can prevent BBEdit from adding this extended attribute as follows:
    
    defaults write com.barebones.bbedit SaveOpenWithDataInTypelessFiles -bool NO
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Sleep and Auto-Save

-   Document auto-save (for crash recovery) is on by default, with a save interval of one minute. To change either setting:
    
    defaults write com.barebones.bbedit EnableAutoSave\_v2 -bool YES
    
    defaults write com.barebones.bbedit AutoSaveIntervalInMinutes\_v2 -int 10
    
-   The "Sleep" command does not save any documents in place, since it creates an auto-save file for any open documents with unsaved changes. However, if you want BBEdit to save any titled (i.e. opened from an existing file) documents to disk before sleeping, you can do so as follows:
    
    defaults write com.barebones.bbedit SaveTitledDocumentsBeforeSleeping -bool YES
    
-   BBEdit provides control over whether documents on remote servers (FTP/SFTP) or unmounted volumes are opened when automatically reopening documents at application startup. You can modify its behavior with these settings:
    
    defaults write com.barebones.bbedit AllowVolumeMountDuringStateRestore -bool YES
    
    \# If set to YES, BBEdit will attempt to mount a volume
    
    \# containing a document it wants to reopen. defaults to NO.
    
    defaults write com.barebones.bbedit PromptToReopenRemoteDocuments -bool YES
    
    \# If set to YES (the default), BBEdit will prompt to give you the
    
    \# opportunity to skip remote documents.
    
    \# If set to NO, BBEdit will open remote documents without
    
    \# asking, if ReopenRemoteDocuments is set to YES.
    
    \# Has no effect if ReopenRemoteDocuments is set to NO.
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Source Control

-   When scanning folders for various purposes (multi-file search, Find differences, and others), SCM administrative directories are specifically ignored, even if "Search Invisible Folders" is turned on: CVS, .svn, .git, .hg, .bzr. This avoids potential disasters that can result from indiscriminate search and replace in such directories. If, however, you choose to live dangerously, you can allow BBEdit to see inside of these directories:
    
    defaults write com.barebones.bbedit SkipSCMAdminDirsWhenScanningFolders -bool NO
    
-   "Show Working Copy Status" for svn does not include switched items. If this affects you and you would prefer to see switched items, you may make them visibile with:
    
    defaults write com.barebones.bbedit ShowSVNSwitchedItems -bool YES
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Text Display and Coloring

-   Whether or not BBEdit uses text smoothing (antialiasing) may be adjusted separately for fixed-width and for proportional fonts:
    
    defaults write com.barebones.bbedit FixedWidthFontSmoothingThreshold -int 8
    
    defaults write com.barebones.bbedit FontSmoothingThreshold -int 4
    
    The factory default smoothing thresholds are 8pt for fixed width fonts, and 4pt for proportional fonts, respectively. Font sizes above the specified threshold are smoothed; font sizes below the threshold are not.
    
-   If you want to unconditionally disable text smoothing for a specific font, you can do so as follows:
    
    defaults write com.barebones.bbedit DisableFontSmoothing\_FONTNAME -bool YES
    
    "FONTNAME" is the display name of the font, as it appears in the Fonts panel or the Font Book application. For example, this will disable font smoothing for Monaco:
    
    defaults write com.barebones.bbedit DisableFontSmoothing\_Monaco -bool YES
    

**Important:** These font smoothing settings only affect behavior when using BBEdit on a non-Retina display. On Retina displays, text is always smoothed.

-   BBEdit will calculate an appropriate size for font used in the line number bar, based on the point size of the font used for editing. The maximum size of the line number bar font is limited to 24 points. If you would prefer a lower (or higher) limit, you can adjust this:
    
    defaults write com.barebones.bbedit MaximumLineBarPointSize -float NN
    
    "NN" is a decimal number, and should be greater than zero.
    
    Changes to this setting take effect immediately, and do not require restarting the application.
    
-   BBEdit uses the document's display font to draw line numbers in the line number bar. This may be less than ideal if the display font isn't monospaced. If desired, you can instruct BBEdit to use the system font with monospaced numbers for the line number bar:
    
    defaults write com.barebones.bbedit UseSystemFontForLineBar -bool YES
    
    Changes to this setting take effect immediately, and do not require restarting the application.
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Text Search and Replace

-   Like many macOS applications, BBEdit supports the "Find Scrap", a feature of the OS that enables sharing of the "search for" string between applications. Some applications put inappropriate content (such as Web search strings) on the Find Scrap, which can cause the "search for" string in BBEdit's Find dialog to be replaced when you didn't expect it.
    
    To tell BBEdit not to import the Find Scrap into its Find window, nor to export the "search for" string to the Find Scrap:
    
    defaults write com.barebones.bbedit FindDialog\_UsesFindScrap -bool NO
    
-   The Live Search bar is not visible by default, but appears when you choose "Live Search" from the Search menu. If you would like the Live Search bar to be visible in each new document that you create or open:
    
    defaults write com.barebones.bbedit Editor\_AlwaysOpenQuickFind -bool YES
    
-   When performing a single-file "Replace All" operation, BBEdit can show a confirmation sheet showing the number of replacements performed. If you would like to see this confirmation:
    
    defaults write com.barebones.bbedit ReportReplaceAllResults -bool YES
    
-   If you want to amaze and impress your friends and family with just how fast BBEdit's Replace All is, there's an expert preference for that:
    
    defaults write com.barebones.bbedit ReplaceAllResultsIncludeTiming -bool YES
    
    When turned on, the sheet (or notification) will display the amount of time required for the Replace All operation.
    
-   If you like, BBEdit will show the full paths of files listed in search results windows:
    
    defaults write com.barebones.bbedit ShowFullPathsInSearchResults -bool YES
    
-   By default, BBEdit will remember the 16 most recent search and replace strings/patterns for the popup menu in the Find and Multi-File Search windows. The size of this history is adjustable:
    
    defaults write com.barebones.bbedit FindAndReplaceHistorySize -int \[some number\]
    
    A minimum history size of 2 is enforced. Setting the history to zero makes it infinite.
    
-   If you need to **completely** disable the search history in the Find and Multi-File Search windows, you can do so now, using the following command:
    
    defaults write com.barebones.bbedit DisableFindAndReplaceHistory -bool YES
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Windows and UI Tweaking

-   When using the "Previous Document" and "Next Document" commands on the View menu, the order in which BBEdit navigates documents is determined by the order in which they were opened. If you prefer, these commands can be made to navigate the documents in the order shown in the file list.
    
    defaults write com.barebones.bbedit SurfNextPreviousInDisplayOrder -bool YES
    
-   BBEdit attempts to move windows as little as possible when you zoom them. To override this and let BBEdit place the window in the upper left-hand corner of the screen:
    
    defaults write com.barebones.bbedit ZoomWindowsInPlace -bool NO
    
-   By default, the application will allow windows to take up the entire screen when entering full screen mode. If desired, you may prevent this and instruct the application to figure out whether a window should be made the full width of the screen:
    
    defaults write com.barebones.bbedit FullScreenWindowsHogScreen -bool NO
    
    You can toggle this behavior on the fly by holding down the Command key when clicking on the "enter full screen" button.
    
-   When entering full screen mode, the application figures out whether the window width should be increased to take up the full screen width, or not, based on the width of the window relative to the width of the screen that it's on. The threshold at which the window is made to take up the entire screen width can be set thus:
    
    defaults write com.barebones.bbedit FullScreenWidthThreshold -float 0.65
    
    This setting requires that `FullScreenWindowsHogScreen` be turned on (see above) *or* that you hold down the `Command` key while clicking the "enter full screen" button. The threshold is a percentage, so (in the example above), if the window is 65% or more of the width of the screen that it's on, it will take up the full width of the screen when entering full screen mode.
    
    Note that when setting the threshold, you **must** set it as a decimal number, using "`-float <some number between 0 and 1>`".
    
-   The "Remember the ... most recently used items" setting in the Application preferences applies to all item types. So, if it's set to 15, BBEdit will remember 15 text documents, 15 folders, 15 projects, 15 images, and so on. If you want finer control, you can construct an expert pref using the name of the document type as it appears in the menu (and if that name contains spaces, you'll need to quote it). So, for example, if you only wanted to remember the five most recent projects:
    
    \# remember only the five most recent projects
    
    defaults write com.barebones.bbedit NSRecentDocumentsLimit\_Projects -int 5
    
    Or the ten most recent folders:
    
    \# remember only the ten most recent folders
    
    defaults write com.barebones.bbedit NSRecentDocumentsLimit\_Folders -int 10
    
    Or only the most recent shell worksheet:
    
    \# remember only the most recent worksheet
    
    defaults write com.barebones.bbedit "NSRecentDocumentsLimit\_Shell Worksheets" -int 1
    
    If you don't want to remember any recent documents of a particular type (they won't appear in the menu, either), you can set its limit to zero:
    
    \# don't remember any images
    
    defaults write com.barebones.bbedit NSRecentDocumentsLimit\_Images -int 0
    
    You can also control the number of items shown in the “Most Recently Used” group:
    
    \# Show up to 15 items in the “Most Recently Used” group:
    
    defaults write com.barebones.bbedit MostRecentItemsGroupLimit -int 15
    
    Note that when setting any recent items limit, you **must** set it as an integer, using "`-int <some number>`".
    
    By default, BBEdit does not remember recent items opened from any of the canonical locations for temporary files. (This also includes the "svn-commit.tmp" files used for Subversion commits.) If desired, you can change this:
    
    defaults write com.barebones.bbedit RecentItems\_RememberTempFiles -bool YES
    
-   By default, the “Open File by Name” window stays open when you click the “Open” button. However, if you would prefer for it to act more like a modal dialog, you may do so:
    
    defaults write com.barebones.bbedit CloseOFBNWindowAfterOpeningSelection -bool YES
    
-   The Window menu and Windows palette will list windows (and documents within them) sorted by name. If you would like them to be sorted by windowing order, use this command:
    
    defaults write com.barebones.bbedit SortWindowsAndDocumentsByName -bool NO
    
-   BBEdit will color patterns (the left-hand column) in the Grep Cheat Sheet menu according to the active color scheme. If you would prefer monochromatic patterns for any reason:
    
    defaults write com.barebones.bbedit ColorPatternsInGrepCheatSheet -bool NO
    
-   If necessary, you can disable the cursor blink in BBEdit's editing windows by using this Terminal command:
    
    defaults write com.barebones.bbedit DisableCursorBlink -bool YES
    
    Note that this will **not** affect cursor blinking in dialog boxes and certain edit fields; but if you need to use this expert preference, you probably already know how to turn that off.
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)

---

#### Miscellaneous

-   The "Copy as Styled HTML" and "Save as Styled HTML" commands normally generate style information inline. If you want to use an embedded style sheet instead, set the expert preference thusly:
    
    defaults write com.barebones.bbedit UseInlineStylesForCopiedHTML -bool NO
    
-   When editing files that are on remote file servers (AFP, NFS, SMB, etc), BBEdit will not look for directory-relative ctags data files. This is a particular performance win when the file is located on a volume mounted via MacFUSE/SSH or similar, or if the file server is over a slow or high-latency link.
    
    To enable scanning for tags files on remote volumes, use these separately or together:
    
    defaults write com.barebones.bbedit DisableCtagsScanOnRemoteVolumes -bool NO
    
-   When searching for matches, Open File by Name limits the number of matches to a reasonable maximum. The factory default is 200, and may be adjusted:
    
    defaults write com.barebones.bbedit OpenByNameMaxWildcardMatches -int 200
    
-   Ordinarily, the output from Unix scripts run within BBEdit is delimited with line separators (except when the script output is sent to a new untitled document). If you wish to suppress the separators, you can do so:
    
    defaults write com.barebones.bbedit UseSeparatorsInUnixScriptOutput -bool NO
    
-   By default, the Open panel implements the standard system behavior of displaying the same folder that was viewed the last time you used the Open command. If you wish, you may instead have the Open panel display the directory containing the active document:
    
    defaults write com.barebones.bbedit OpenPanelShowsFrontDocumentDirectory -bool YES
    
    If the active document is untitled or was opened from an FTP/SFTP server (or if there are no documents open), the Open panel will show you the last-used directory.
    
-   When scanning folders for various purposes (multi-file search, Find Differences, text factories, Open File by Name, and others), BBEdit will not explore `node_modules` directories that it encounters. If you want BBEdit to search `node_modules` directories:
    
    defaults write com.barebones.bbedit SkipNodeModulesWhenScanningFolders -bool NO
    
-   While drag-scrolling (that is, making a selection with the mouse and dragging it beyond the view boundaries, or using drag-and-drop for the same purpose), BBEdit will not normally limit the vertical scrolling speed. If this is too fast for you:
    
    defaults write com.barebones.bbedit ThrottleVerticalScrollingSpeed -bool YES
    
-   Beginning with version 12.5, BBEdit provides the selection range in the active document (or the active document's contents, if there is no selection) as `stdin` when running a Unix script or executable from the Scripts menu. If the script isn't expecting this **and** never reads from `stdin`, this can cause a problem if there is more than 64K of data provided. The result will usually be a `100032` error.
    
    If this is a regular occurrence for you, you can turn the feature off using a Terminal command:
    
    defaults write com.barebones.bbedit ProvideSTDINToUnixScripts -bool NO
    
    This takes effect immediately without needing to restart the application.
    
-   When searching for text, or using the spelling checker to navigate, BBEdit will ordinarily play the system alert sound when no appropriate match is found. If it detects that the sound is muted, BBEdit will instead show an overlay alert. To skip the sound check and always have BBEdit show the overlay alert instead of beeping:
    
    defaults write com.barebones.bbedit AlwaysShowAnnunciatorForNotFound -bool YES
    
    This takes effect immediately without needing to restart the application.
    

[Back to top](http://www.barebones.com/support/bbedit/ExpertPreferences.html#toc)
