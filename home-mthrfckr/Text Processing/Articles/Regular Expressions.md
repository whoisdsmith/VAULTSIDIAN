# Regular Expressions

## Regular Expressions–The Eclectic Light Company

![](https://eclecticlightdotcom.files.wordpress.com/2015/07/oyster.png?w=973) Oyster is a great way to develop your own collection of regex phrases.  
*Although most are familiar with some shorthand notation used in searching, Regular Expressions turn this into a programming language. Are they just for Unix wizards?*  
Most searches, using Spotlight, Google, or any other engine of your choice, return too many results, of which the great majority are usually irrelevant. Despite increasingly smart search engines, getting the best out of them requires us to learn how to refine searches, to focus them so that they return just the ‘hits’ that we want.  
Instead of looking just for ‘publisher’, you would normally supply additional terms to help select more relevant results, such as ‘book’ and ‘non-fiction’, although this will still return millions of hits using Google. Often we have partial information: we cannot recall whether the publisher’s name was Chaplin, Chapman, or something similar, so to narrow the field further we might add a term that would pick up all those.  
Depending on the search engine we are using, this might be ‘Chap\*’, although Google will not accept the \* character as indicating a ‘wild card’, so as to include any words starting with the letters ‘Chap’. Spotlight is quite happy to deal with partial terms, and searching for ‘publisher book non-fiction Chap’ should produce a usefully refined search. There is detailed information on improving Google searches [here](https://eclecticlight.co/2015/07/10/qa-using-google-advanced-search/), and local Spotlight search [here](https://eclecticlight.co/2015/05/06/under-the-spotlight-local-search/).  
**How to access regex**  
The most common and most powerful method of constructing compound search terms (and more) is by means of *Regular Expressions,* normally abbreviated to *regex.* To some degree or other, these are available in most scripting languages, including PHP, Perl, Python, Tcl, Ruby, and Java, some command line tools such as grep, and in more sophisticated text and other editors such as BBEdit and Microsoft Word, as well as some modules basic on the Open Office suite.  
Despite the name, their implementations are by no means consistent or regular: to find all words beginning with ‘Chap’ or ‘chap’ and ending with ‘n’, you might search for `\b[Cc]hap[a-z]+n\b` in BBEdit, but `<[Cc](hap)*n>` in Microsoft Word.  
[![Microsoft Word allows its own limited version of regex in searches.](https://eclecticlightdotcom.files.wordpress.com/2015/07/wordregex.png?w=940)](https://eclecticlightdotcom.files.wordpress.com/2015/07/wordregex.png)  
Microsoft Word allows its own limited version of regex in searches.  
In *Microsoft Word,* use the Edit menu, Find item and select the Advanced Find and Replace… command to display the Find and Replace dialog. Open its extended options by clicking on the disclose button at the lower left of that dialog, and check the ‘Use wildcards’ option to engage its limited regex mode.  
[![Using grep-style regex in BBEdit.](https://eclecticlightdotcom.files.wordpress.com/2015/07/bbeditregex.png?w=940)](https://eclecticlightdotcom.files.wordpress.com/2015/07/bbeditregex.png)  
Using grep-style regex in BBEdit.  
In *BBEdit,* a whole menu is devoted to Search: use its first command, Find…, and in the Find dialog, ensure that the rightmost option of Matching, Grep, is checked. Support in different scripting languages also varies, with Perl for instance appearing to be largely written in regex form, or you may need to load additional support, for instance in the java.util.regex package in Java 1.4 and later.  
**Basic expressions**  
The core terms used in regular expressions are not hard to learn or use.  
*Single characters* can be matched in several ways:

- you can give an explicit character,
- a dot `.` to denote any character at all,
- a character class specified in square brackets, such as `[a-z]` for the lower case alphabet,
- or a special character prefaced by the escape character `\`, such as `\*` for a literal asterisk.  
Those single characters can be multiplied using *quantifiers:*
- `?` for 0 or 1,
- `*` being any number including 0,
- `+` meaning 1 or more,
- or if you wish to be more precise about numbers, you can specify a range inside curly brackets, such as `{2,5}`.  
The other major class of core terms provides *positional specification:*
- a caret `^` matches positions at the start of lines,
- a dollar `$` at the end,
- `\<` at the start of a word,
- and `\>` at the end;
- a common alternative to the latter is to employ `\b` to denote work breaks;
- when enclosed in square brackets, a caret has a different meaning, that of negating the character class: for instance `[^a-z]` means any character except those in the lower case alphabet.  
There are also some *miscellaneous terms* that are both important and in wide use:
- the vertical bar `|` means ‘or’, and allows matching to either of the regular expressions that it separates,
- normal parentheses `(` and `)` are used to limit the scope of expressions, for example each side of `|`,
- and you may be able to refer back to text matched within the first or subsequent set of parentheses using escaped references such as `\1`, `\2`, and so on.  
*Escape characters* are used widely in different programming languages and systems, and are fairly standard across them:
- `\t` is a tab,
- `\n` newline,
- `\r` carriage return,
- `\s` any whitespace character including space, tab, and newline,
- `\w` is any alphanumeric character or `[a-zA-Z0-9_]`,
- `\W` is anything not `\w` or `[^a-zA-Z0-9_]`,
- `\d` is any digit, or `[0-9]`.  
You may well have already encountered these and other escape characters in Perl.  
Dave Child provides an excellent printable cheat sheet to regular expressions [here](http://www.cheatography.com/davechild/cheat-sheets/regular-expressions/ "Cheatography") that summarise those and others.  
**Phrases and more**  
Just as in natural language, as you use regular expressions you will discover and develop phrases that are effectively idioms. [RegExLib.com](http://regexlib.com/ "RegExLib.com") has now collected more than 4900 different idioms, drawn from a very wide range of different applications.  
These can be as simple as `^.+@[^\.].*\.[a-z]{2,}$` (by Thor Larholm), or as complex as `^([\w\-\.]+)@((\[([0-9]{1,3}\.){3}[0-9]{1,3}\])|(([\w\-]+\.)+)([a-zA-Z]{2,4}))$` (by David Lott), both of which match email addresses with differing degrees of specificity. Long and complex regular expressions can be daunting at first, but are worth parsing out on paper, term by term, breaking them down into smaller parts so that you can see how they are assembled into the working whole.  
Regular expressions tend to be more ephemeral than more formal programming languages, in that you often deploy them in one-off circumstances, perhaps when looking for a particular file. Despite that, they are worth investing time and care over, perhaps using a testing tool to get it right, and then to record your regex in your own idiom library. If novel and of more general use, submit it to [RegExLib.com](http://regexlib.com/ "RegExLib.com") for others to discuss, rate, and deploy.  
**Dialects**  
You should also be careful to understand which terms and conventions are available in the particular implementation of regular expressions that you are using. Extensive information and tutorials are available at [Regular-Expressions.info](http://www.regular-expressions.info/ "Regular-Expressions.info"), whilst [RegexAdvice](http://regexadvice.com/ "RegexAdvice") offers advice, discussions, and even a regular expressions blog. Occasional users may find these helpful to solve specific problems that they may come across: if they seem a bit geeky, remember that regex is a form of programming language, and there are plenty of people who spend of lot of their working days developing and using them.  
By now, you should be happier making your searches and scripts more powerful using regex, and less scared of advanced search features. Use these thoughtfully to refine searches: it is better to invest a few minutes thinking out how to refine a search to make it more effective. That small investment of time will be repaid handsomely in the time that it saves you trudging through pages of dross that would result from something less focussed.  
***Tools:* Developing Regular Expressions**  
Terse languages that are not easy to understand are best developed interactively, using an environment that allows you to assemble, test, and debug its code. If you only use regex occasionally, this [online workbench](http://osteele.com/tools/rework/ "OSteele") should suffice. This is particularly useful if you need to deploy your regex in a language such as JavaScript, PHP, Ruby, or Python, as the site can perform translation into the regex variants supported by those languages.  
[![Oyster is a great way to develop your own collection of regex phrases.](https://eclecticlightdotcom.files.wordpress.com/2015/07/oyster.png?w=940)](https://eclecticlightdotcom.files.wordpress.com/2015/07/oyster.png)  
Oyster is a great way to develop your own collection of regex phrases.  
If you use regex more, you need your own offline tool for development. There is no shortage in the Mac App Store, ranging in cost from free to £10.99. Among those Oyster (£3.99) and RegExRX (£3.99) are generally very well liked, and worth considering first.  
[![RegExRX is another excellent tool for developing and testing regex phrases.](https://eclecticlightdotcom.files.wordpress.com/2015/07/regexrx.png?w=940)](https://eclecticlightdotcom.files.wordpress.com/2015/07/regexrx.png)  
RegExRX is another excellent tool for developing and testing regex phrases.  
***Tools:* Applying Regular Expressions**  
In addition to those general applications that offer regex support, and scripting languages, there are some specialist tools that are designed to exploit regex to their full.  
A free implementation of the command line utility grep with a basic GUI interface is available [here](http://www.joar.com/grep/ "Joar"), and may be useful for searching large text files.  
[![Using regex in Nisus.](https://eclecticlightdotcom.files.wordpress.com/2015/07/nisusregex.png?w=940)](https://eclecticlightdotcom.files.wordpress.com/2015/07/nisusregex.png)  
Using regex in Nisus.  
[BBEdit](http://www.barebones.com/products/bbedit/ "Barebones") is not the only text editor with regex support built in. [Nisus](http://www.nisus.com/ "Nisus") word processors have always included sophisticated search and replace functions based on grep and regex, that have been used to work with markup languages.  
SubEthaEdit (App Store, £22.99) is a collaborative text editor which allows you to choose which flavour of regex it employs in enhanced search and replace operations, a feature that could make it attractive for those developing for two or more different scripting languages. Smultron 7 (App Store, £3.99) also allows a regex option in its Advanced Find feature.  
The outright winner when it comes to unusual applications of regex must have been Le Decroiseur, sadly now discontinued, which was a crossword tool that allowed you to search English and foreign language dictionaries using regular expressions, to aid in setting or solving crosswords, playing Scrabble, and other word games.  
*Updated from the original, which was first published in MacUser volume 23 issue 13, 2007*
