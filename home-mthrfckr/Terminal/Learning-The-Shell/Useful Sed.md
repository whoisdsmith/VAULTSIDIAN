# Useful Sed

Useful sed tips, techniques and tricks for daily usage.

# TABLE OF CONTENTS

* [One liners with short explanation](#one-liners-with-short-explanation) :bulb:

* [Short sed tut](#short-sed-tut) :books:

* [About](#about)

* [Please consider donating to support this type of content!](#buy-me-a-coffee) :pray:

* [Credits](#credits-and-links)

# Recommended Books (not Written by me)

[Definitive Guide to sed - by Daniel Goldman](https://amzn.to/3cnzQCS)  
<br>
[Sed & Awk - Dale Dougherty & Arnold Robbins](https://amzn.to/3kKck7Y)  
<br>
[Effective awk programming - by Arnold Robbins](https://amzn.to/30scfhM)

# More Guides that I Wrote

[text-processing-recipes-linux](https://github.com/adrianscheff/text-processing-recipes-linux) - Comprehensive list of text processing tools and techniques. Featuring `vim, tr, cat, tac, sort, shuf, seq, pr, paste, fmt, cut, nl, split, csplit, sed, awk, grep and regex.`  
<br>
[simple-awk](https://github.com/adrianscheff/simple-awk) - A simple but practical guide to awk.  
<br>
[wizardly-tips-vim](https://github.com/adrianscheff/wizardly-tips-vim) - Less known Vim tips & tricks  
<br>
[quick-grep](https://github.com/adrianscheff/quick-grep) - Quick grep reference and tutorial.  
<br>
[convenient-utils-linux](https://github.com/adrianscheff/convenient-utils-linux) - Linux utils to make life easier and more convenient. 

# BUY ME A COFFEE

I love teaching others. Time is limited but donations will allow me to to help the community more. **How useful was this to you?** If it was I would be humbly grateful for your donation.:pray:

[paypal.me/adrianscheff](https://www.paypal.com/paypalme/adrianscheff) |  [patreon.com/adrianscheff](https://www.patreon.com/adrianscheff) | bitcoin (1NrkpsgbmmLDoDcvAvsGEMGEQhvvtw36x1) - **are some ways to help me help you better.**

Thank you! May you be rich as Crassus and happy as Buddha! :) 

-----

# ONE LINERS WITH SHORT EXPLANATION

## Print One line

`sed -n '10p' myfile.txt` 

## Do Replacement on All Lines except line 5

`sed '5!/s/foo/bar/' file.txt`

## Do Replacement on Lines Matching Regex (eg: Lines Starting with 'hello')

`sed '/^hello/ s/h/H/' file.txt ` 

## Do Replacement from line 5 to End of File

`sed '5,$ s/foo/bar/' file.txt `

## Delete Empty Files

`sed  '/^$/d' file`

## Print Lines between Two Regex Matches

`sed -nE '/^foo/,/^bar/p' file.txt`

## Use Custom Delimiters to Make it Easy for Some Strings that Contain Slashes

`sed 's_/bin/bash_/bin/sh_' file.txt ` 

## Custom Delimiters for Regex Address Combined with the Classical Delimiter for Substitute Command (you Could also Use there a Custom delimiter). Useful for Paths

`sed '\_/bin/bash_s/grep/egrep/' file.txt`

* or using the same delimiter for clarity `sed '\_/bin/bash_s_grep_egrep_' file.txt`

## Insert a Space between lowercase/Uppercase Characters Using & (which Represents the Regex match)

`sed 's/[a-zA-Z]/& /g' file.txt `

## Keep the First Word of Every line (where Word is Defined by Alphanumeric Chars + Underscores for Simplicity sake)

`sed -E 's_[a-zA-Z0-9_]+.*_\1_' file.txt `

## Switch the First Two Words

`sed -E 's_([a-zA-Z0-9_]*) ([a-zA-Z0-9_]*)_\2 \1_' f1`

## Remove Duplicate Words Separated by a Single Space (but not triplicate)

`sed -E 's_([a-zA-Z0-9_]+) \1_\1_ig' f1`

## Search and Replace for Pattern, Write just the Lines with the Replacements in a New File

`sed  's_foo_bar_w replaced.txt' file.txt  `

## Multiple Replacements

`sed -e 's_foo_bar_' -e 's_hello_HELLO_' file.txt `

## Multiple Replacements by Using a Sed Script

```
#!/usr/bin/sed -f
s/a/A/
s/foo/BAR/
s/hello/HELLO/
```

* Make executable with `chmod +x myscript.sed`, call with `./myscript.sed myfile.txt`

## Multiple Commands Using the ; Operator Which in Theory Concatenates Commands (WARNING! It Won't Work as Expected with Certain Commands such as 'r' or 'w'. Use a Sed Script instead OR Put the Command Dealing with Filenames last). Print line 10 and Insert before line 5

`sed '10p;5i\"INSERTED BEFORE LINE 5" file.txt ` 

## Remove Comments between Lines Starting with These Two Keywords. Empty Lines Will Be Put there instead

`sed -E '/start/,/end/ s/#.*//' file.txt `

## Delete Comments Starting with # (no Empty Lines Left behind)

`sed -E '/^#/d' f1`

## Insert an Empty line after Pattern (after Each line Containing Comment in This case)

`sed '/^#/G' file.txt `

## View Lines minus Lines between line Starting with Pattern and End of File

`sed  '/start/,$ d' file.txt `

## View Lines except Lines between line Starting with Pattern and line Ending with Pattern

`sed -rn '/start/,/end/ !p' file.txt `

## Print until You Encounter Pattern then Quit

`sed  '/start/q' file.txt `

## Insert Contents of File after a Certain line

`sed  '5 r newfile.txt' file.txt `

## Append Text after Lines Containing Regex (AFTER FOO)

`sed '/foo/a\AFTER FOO' file.txt `

## Insert Text after Lines Containing Regex (BEFORE FOO)

`sed '/foo/i\BEFORE FOO' file.txt `

## Change line Containing Regex Match

`sed '/foo/c\FOO IS CHANGED' file.txt `

## Nested Sed Ranges with Inversion. Between Lines 1,100 Apply Actions where the Pattern DOESN'T Match

```
#!/usr/bin/sed -f
1,100 {
	/foo/ !{
		s_hello_HELLOOOOWORLD_
		s_yes_YES_
	}
}

```

## Use Nested Addresses with Change, Insert and Append to Modify: the line before Match, the line with Match, the line after Match

```
#!/usr/bin/sed -f
/^#/ {
i\
#BEFFORE ORIGINAL COMMENt
a\
#AFTER ORIGINAL COMMENT
c\
# ORIGINAL COMMENT IS NOW THIS LINE
}

```

## Insert New line before the First Comment, after the First Comment Put in the Contents of File and Quit Immediately afterwards

```
#!/usr/bin/sed -f
/^#/ {
i\#BEFORE COMMENT
r myotherfile.txt
q
}
```

## Transform Text

`sed 'y/abc/ABC/' file.txt `

## Copy All the Comments (starting with #) to a New File

`sed -E '/^#/w comments.txt' file.txt `

## Print Every Second line (substitute ~3 for Third Line, etc)

`sed -n '1~2p' file.txt `

## Edit File in place but also Create a Backup

`sed -i.bak 's/hello/HELLO/' file.txt `

## Append Two Extra Lines after Regex Match

 `sed -E '/^#/G G' file.txt ` 

-----

# Short Sed Tut

## Sed Commands Use an Address Based on Which They Operate. The Address Can Be

1. **Single lines** `sed '10d' file.txt ` - delete line 10
2. **Line range** `sed '1,10d' file.txt` - delete from line 1 to 10
3. **Line range2**  `sed '6,$d' file.txt ` - delete from line 6 to end of file ($ is end of file)
4. **Regex** `sed -E '/^#/d' file.txt ` - delete lines where regex matches
5. **Regex ranges** `sed -E '/DEBUG/,/END_DEBUG/d' file.txt ` - delete lines between regex matches (including lines where regex matches)
6. **Regex and line ranges** `sed -E '/DEBUG/,30d' file.txt ` - delete from line matching DEBUG to line 30
7. **all lines** `sed 'a\AFTER EVERY LINE' file.txt ` - append this after every line (when no address is present apply to all lines)
8. **Nested** - use this with a sed script (see below)

<br>

```
#!/usr/bin/sed -f
1,100 { 
	/DEBUG/{
		/DONE/d
		/NOT DONE/a\TO BE DONE URGENTLY 
	}
}
```

<br>

- between lines 1 and 100:

> > where matches DEBUG, 
> > 
> > > delete lines containing /DONE/ and after lines containing /NOT DONE/ append.

<br>

## You Can Invert the Address by Putting a ! in front of **the command**, not the Address

1. `sed '/PRODUCTION/!d' file.txt ` - delete all lines not containing regex match. Note the ! in front of d.
2. Everything inside curly brace (for nested) is a command. You put the ! in front of the curly brace.

<br>

```
#!/usr/bin/sed -f
1,100 { 
	/DEBUG/ !{
		/DONE/d
		/NOT DONE/a\TO BE DONE URGENTLY 
	}
}
```

<br>

* between lines 1,100

> > on lines NOT containing /DEBUG/
> > 
> > > Perform operations

<br>

3. "Double" nested inversion

<br>

```
#!/usr/bin/sed -f
1,100 { 
	/DEBUG/ !{
		/DONE/!d
	}
}
```

<br>

* between lines 1,100

> > on lines not containing DEBUG
> > 
> > > delete lines NOT containing /DONE/

<br>

## Basic Commands

1. `5d` - **delete** - Delete line 5.
2. `5p` - **print.** - print line 5 (you should call sed with `-n` option when using print to only print the specified lines)
3. `5q` - **quit**  - after line 5 quit
4. `5a\Appended` - **append** - after line 5. Note the backward slash in front of 'a'
5. `5c\Changed` - **change** - change line 5 to 'Changed'
6. `5i\Before` - **insert** - insert before line 5.
7. `5r newfile.txt` - **read** - put the contents of file 'newfile.txt' after line 5
8. `5w written.txt` - **write** - write line 5 to 'written.txt'
9. `5s/foo/bar` - **substitute** - on line 5 search for foo and replace with bar

<br>

## Advanced & Less Used Commands

1. `sed -E '/^#/G G' file.txt ` - **append newline to pattern space then append hold space to pattern space** - insert two blank lines after every line that matches regex

<br>

## Regex Tricks

1. `&` is the matched regex. `sed -E '/foo/& & &/' file.txt` will triplicate the foo word
2. `\1` to `\9` are the groups id's. You use a group like `sed -E 's/(foo) (bar)/\2 \1' file.txt '. In this very simple example we search for 'foo' followed by space followed by 'bar'. Then we switch these words (instead of 'foo bar' we have 'bar foo')
3. Flags. `sed 's/foo/bar/gi' file.txt `. 'g' will replace all occurrences on the line (instead of just the first as it is by default). 'i' will make the substitute case insensitive.

<br>

[TO BE CONTINUED]

------

# About

This was born in 4-5 hours of recapping sed (and many hours learning it in the first place). Since then I've spent some more hours (and counting) fixing & improving. A good way to learn something well is to also explain to others. And if I'm honest this is also for myself, later, when I forget. :) 

It was Number 1 on Hacker News in hours after publication and 300+ stars on Github. Hours. Damn! All other projects combined (some of which took much more time) are in the double digit range. The low range. And this quick and  dirty sed tips collection took off. I consider myself lucky to have experienced this and I'm grateful to the people who made it possible. For you I'll try and make this as good as I can. 

------

# Credits and Links

I've learned sed from the manual and various internet links. Here are some of them:<br>
http://sed.sourceforge.net/sed1line.txt<br>
https://www.grymoire.com/Unix/Sed.html<br>
`info sed` and `man sed`<br>

<sub>**NOTES**</sub><br>
<sub> * This is not absolutely perfect and up to the highest standards of Posix and sed usage. It was kindly pointed to me by people from HN. I'll try and make this the best possible version I can and I'll listen to your feedback. I'm not a sed guru after all, just someone trying to follow the 20/80 formula (even though sometimes I go waaay overboard). </sub><br>
<sub> * There is no mention of the hold space (and other registers) usage. Personally I found their usage quite confusing. If this might change in the future I'll adjust this. After all, this is not "The ultimate sed reference" but "useful sed". </sub><br>
<sub> * There might be examples where I use -E (regexp extended option) when it is not necessarily needed. Chances are you'll want to use this in most of your operations so it might not be a bad reflex to have. Sure, you could make an alias for it in your .bashrc. Personally I try and delay usage of aliases until I feel it's absolutely necessary (as it hides some verbosity which makes the commands clearer).</sub><br>
