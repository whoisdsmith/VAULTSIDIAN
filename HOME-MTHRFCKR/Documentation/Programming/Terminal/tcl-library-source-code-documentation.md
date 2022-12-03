textutil - Procedures to manipulate texts and strings.

The package **textutil** provides commands that manipulate strings or texts (a.k.a. long strings or string with embedded newlines or paragraphs). It is actually a bundle providing the commands of the six packages

in the namespace **textutil**.

The bundle is _deprecated_, and it will be removed in a future release of Tcllib, after the next release. It is recommended to use the relevant sub packages instead for whatever functionality is needed by the using package or application.

The complete set of procedures is described below.

-   **::textutil::adjust** _string args_
    
    Do a justification on the _string_ according to _args_. The string is taken as one big paragraph, ignoring any newlines. Then the line is formatted according to the options used, and the command return a new string with enough lines to contain all the printable chars in the input string. A line is a set of chars between the beginning of the string and a newline, or between 2 newlines, or between a newline and the end of the string. If the input string is small enough, the returned string won't contain any newlines.
    
    Together with **::textutil::indent** it is possible to create properly wrapped paragraphs with arbitrary indentations.
    
    By default, any occurrence of spaces characters or tabulation are replaced by a single space so each word in a line is separated from the next one by exactly one space char, and this forms a _real_ line. Each _real_ line is placed in a _logical_ line, which have exactly a given length (see **\-length** option below). The _real_ line may have a lesser length. Again by default, any trailing spaces are ignored before returning the string (see **\-full** option below). The following options may be used after the _string_ parameter, and change the way the command place a _real_ line in a _logical_ line.
    
    -   \-full _boolean_
        
        If set to **false**, any trailing space chars are deleted before returning the string. If set to **true**, any trailing space chars are left in the string. Default to **false**.
        
    -   **\-hyphenate** _boolean_
        
        if set to **false**, no hyphenation will be done. If set to **true**, the last word of a line is tried to be hyphenated. Defaults to **false**. Note: hyphenation patterns must be loaded prior, using the command **::textutil::adjust::readPatterns**.
        
    -   **\-justify** **center|left|plain|right**
        
        Set the justification of the returned string to **center**, **left**, **plain** or **right**. By default, it is set to **left**. The justification means that any line in the returned string but the last one is build according to the value. If the justification is set to **plain** and the number of printable chars in the last line is less than 90% of the length of a line (see **\-length**), then this line is justified with the **left** value, avoiding the expansion of this line when it is too small. The meaning of each value is:
        
        -   **center**
            
            The real line is centered in the logical line. If needed, a set of space characters are added at the beginning (half of the needed set) and at the end (half of the needed set) of the line if required (see the option **\-full**).
            
        -   **left**
            
            The real line is set on the left of the logical line. It means that there are no space chars at the beginning of this line. If required, all needed space chars are added at the end of the line (see the option **\-full**).
            
        -   **plain**
            
            The real line is exactly set in the logical line. It means that there are no leading or trailing space chars. All the needed space chars are added in the _real_ line, between 2 (or more) words.
            
        -   **right**
            
            The real line is set on the right of the logical line. It means that there are no space chars at the end of this line, and there may be some space chars at the beginning, despite of the **\-full** option.
            
    -   **\-length** _integer_
        
        Set the length of the _logical_ line in the string to _integer_. _integer_ must be a positive integer value. Defaults to **72**.
        
    -   **\-strictlength** _boolean_
        
        If set to **false**, a line can exceed the specified **\-length** if a single word is longer than **\-length**. If set to **true**, words that are longer than **\-length** are split so that no line exceeds the specified **\-length**. Defaults to **false**.
        
-   **::textutil::adjust::readPatterns** _filename_
    
    Loads the internal storage for hyphenation patterns with the contents of the file _filename_. This has to be done prior to calling command **::textutil::adjust** with "**\-hyphenate** **true**", or the hyphenation process will not work correctly.
    
    The package comes with a number of predefined pattern files, and the command **::textutil::adjust::listPredefined** can be used to find out their names.
    
-   **::textutil::adjust::listPredefined**
    
    This command returns a list containing the names of the hyphenation files coming with this package.
    
-   **::textutil::adjust::getPredefined** _filename_
    
    Use this command to query the package for the full path name of the hyphenation file _filename_ coming with the package. Only the filenames found in the list returned by **::textutil::adjust::listPredefined** are legal arguments for this command.
    
-   **::textutil::indent** _string_ _prefix_ ?_skip_?
    
    Each line in the _string_ indented by adding the string _prefix_ at its beginning. The modified string is returned as the result of the command.
    
    If _skip_ is specified the first _skip_ lines are left untouched. The default for _skip_ is **0**, causing the modification of all lines. Negative values for _skip_ are treated like **0**. In other words, _skip_ > **0** creates a hanging indentation.
    
    Together with **::textutil::adjust** it is possible to create properly wrapped paragraphs with arbitrary indentations.
    
-   **::textutil::undent** _string_
    
    The command computes the common prefix for all lines in _string_ consisting solely out of whitespace, removes this from each line and returns the modified string.
    
    Lines containing only whitespace are always reduced to completely empty lines. They and empty lines are also ignored when computing the prefix to remove.
    
    Together with **::textutil::adjust** it is possible to create properly wrapped paragraphs with arbitrary indentations.
    
-   **::textutil::splitn** _string_ ?_len_?
    
    This command splits the given _string_ into chunks of _len_ characters and returns a list containing these chunks. The argument _len_ defaults to **1** if none is specified. A negative length is not allowed and will cause the command to throw an error. Providing an empty string as input is allowed, the command will then return an empty list. If the length of the _string_ is not an entire multiple of the chunk length, then the last chunk in the generated list will be shorter than _len_.
    
-   **::textutil::splitx** _string_ ?_regexp_?
    
    Split the _string_ and return a list. The string is split according to the regular expression _regexp_ instead of a simple list of chars. Note that if you add parenthesis into the _regexp_, the parentheses part of separator would be added into list as additional element. If the _string_ is empty the result is the empty list, like for **[split](https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/index.md#split)**. If _regexp_ is empty the _string_ is split at every character, like **[split](https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/index.md#split)** does. The regular expression _regexp_ defaults to "\[\\\\t \\\\r\\\\n\]+".
    
-   **::textutil::tabify** _string_ ?_num_?
    
    Tabify the _string_ by replacing any substring of _num_ space chars by a tabulation and return the result as a new string. _num_ defaults to 8.
    
-   **::textutil::tabify2** _string_ ?_num_?
    
    Similar to **::textutil::tabify** this command tabifies the _string_ and returns the result as a new string. A different algorithm is used however. Instead of replacing any substring of _num_ spaces this command works more like an editor. _num_ defaults to 8.
    
    Each line of the text in _string_ is treated as if there are tabstops every _num_ columns. Only sequences of space characters containing more than one space character and found immediately before a tabstop are replaced with tabs.
    
-   **::textutil::trim** _string_ ?_regexp_?
    
    Remove in _string_ any leading and trailing substring according to the regular expression _regexp_ and return the result as a new string. This apply on any _line_ in the string, that is any substring between 2 newline chars, or between the beginning of the string and a newline, or between a newline and the end of the string, or, if the string contain no newline, between the beginning and the end of the string. The regular expression _regexp_ defaults to "\[ \\\\t\]+".
    
-   **::textutil::trimleft** _string_ ?_regexp_?
    
    Remove in _string_ any leading substring according to the regular expression _regexp_ and return the result as a new string. This apply on any _line_ in the string, that is any substring between 2 newline chars, or between the beginning of the string and a newline, or between a newline and the end of the string, or, if the string contain no newline, between the beginning and the end of the string. The regular expression _regexp_ defaults to "\[ \\\\t\]+".
    
-   **::textutil::trimright** _string_ ?_regexp_?
    
    Remove in _string_ any trailing substring according to the regular expression _regexp_ and return the result as a new string. This apply on any _line_ in the string, that is any substring between 2 newline chars, or between the beginning of the string and a newline, or between a newline and the end of the string, or, if the string contain no newline, between the beginning and the end of the string. The regular expression _regexp_ defaults to "\[ \\\\t\]+".
    
-   **::textutil::trimPrefix** _string_ _prefix_
    
    Removes the _prefix_ from the beginning of _string_ and returns the result. The _string_ is left unchanged if it doesn't have _prefix_ at its beginning.
    
-   **::textutil::trimEmptyHeading** _string_
    
    Looks for empty lines (including lines consisting of only whitespace) at the beginning of the _string_ and removes it. The modified string is returned as the result of the command.
    
-   **::textutil::untabify** _string_ ?_num_?
    
    Untabify the _string_ by replacing any tabulation char by a substring of _num_ space chars and return the result as a new string. _num_ defaults to 8.
    
-   **::textutil::untabify2** _string_ ?_num_?
    
    Untabify the _string_ by replacing any tabulation char by a substring of at most _num_ space chars and return the result as a new string. Unlike **textutil::untabify** each tab is not replaced by a fixed number of space characters. The command overlays each line in the _string_ with tabstops every _num_ columns instead and replaces tabs with just enough space characters to reach the next tabstop. This is the complement of the actions taken by **::textutil::tabify2**. _num_ defaults to 8.
    
    There is one asymmetry though: A tab can be replaced with a single space, but not the other way around.
    
-   **::textutil::strRepeat** _text num_
    
    The implementation depends on the core executing the package. Used **string repeat** if it is present, or a fast tcl implementation if it is not. Returns a string containing the _text_ repeated _num_ times. The repetitions are joined without characters between them. A value of _num_ <= 0 causes the command to return an empty string.
    
-   **::textutil::blank** _num_
    
    A convenience command. Returns a string of _num_ spaces.
    
-   **::textutil::chop** _string_
    
    A convenience command. Removes the last character of _string_ and returns the shortened string.
    
-   **::textutil::tail** _string_
    
    A convenience command. Removes the first character of _string_ and returns the shortened string.
    
-   **::textutil::cap** _string_
    
    Capitalizes the first character of _string_ and returns the modified string.
    
-   **::textutil::uncap** _string_
    
    The complementary operation to **::textutil::cap**. Forces the first character of _string_ to lower case and returns the modified string.
    
-   **::textutil::longestCommonPrefixList** _list_
    
-   **::textutil::longestCommonPrefix** ?_string_...?
    
    Computes the longest common prefix for either the _string_s given to the command, or the strings specified in the single _list_, and returns it as the result of the command.
    
    If no strings were specified the result is the empty string. If only one string was specified, the string itself is returned, as it is its own longest common prefix.
    

This document, and the package it describes, will undoubtedly contain bugs and other problems. Please report such in the category _textutil_ of the [Tcllib Trackers](https://core.tcl.tk/tcllib/reportlist). Please also report any ideas for enhancements you may have for either package and/or documentation.

When proposing code changes, please provide _unified diffs_, i.e the output of **diff -u**.

Note further that _attachments_ are strongly preferred over inlined patches. Attachments can be made by going to the **Edit** form of the ticket immediately after its creation, and then using the left-most button in the secondary navigation bar.