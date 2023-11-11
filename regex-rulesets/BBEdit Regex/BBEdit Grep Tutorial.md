# BBEdit Grep Tutorial

---

Last Modified September 28, 2004

Grep is perhaps one of the most powerful and least understood features of BBEdit. The version of grep that is used in BBEdit is a very basic version, similar to UNIX's egrep. If you don't know how to use it, it's time you learned, because it is immensely useful. BBEdit discusses how to use grep in the Apple Guide (and in the manual), but it may be a little short of an explanation for those unfamilar with it, so here's my explanation.

## Contents

- [Characters to Use in Search Patterns](http://www.anybrowser.org/bbedit/grep.html#SearchChars)
- [Representing Multiple Character Patterns in Searches](http://www.anybrowser.org/bbedit/grep.html#MultiChars)
- [Saving Patterns in Searches](http://www.anybrowser.org/bbedit/grep.html#SavingPats)
- [Characters to Use in Replacement Patterns](http://www.anybrowser.org/bbedit/grep.html#ReplaceChars)
- [Example Patterns](http://www.anybrowser.org/bbedit/grep.html#ExamplePatterns)
- [Grep Tips](http://www.anybrowser.org/bbedit/grep.html#GrepTips)
- [Troubleshooting Grep Patterns](http://www.anybrowser.org/bbedit/grep.html#TroubleshootingGrep)
- [For More Information](http://www.anybrowser.org/bbedit/grep.html#ForMoreInfo)
- [BBEdit Tips and Tricks](http://www.anybrowser.org/bbedit/index.shtml)

---

## Characters to Use in Search Patterns

| Character Typed | What it Represents | Example  
 |  
| --- | --- | --- |  
| *any character* | represents the character typed, with the exception of the special characters defined below | a represents a, b represents b, etc.  
 |  
| `.` | any character (except line breaks) | will match c, 3, space, etc.  
 |  
| `#` | any digit | will match 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9  
 |  
| `\d` | any digit | will match 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 (same as #)

**Note:** Only present in BBEdit Pro 5.1 and Lite 4.6 or greater  
 |  
| `\D` | any non digit | will match anything except 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 (anything not matched by \\d)  
**Note:** Only present in BBEdit Pro 5.1 and Lite 4.6 or greater  
 |  
| `^` | beginning of line  
 |  
| `$` | end of line  
 |  
| `\t` | tab  
 |  
| `\r` | line break (return)  
 |  
| `\n` | newline | matches a Unix line break (line feed)  
 |  
| `\f` | form feed  
 |  
| `\s` | whitespace | matches any whitespace character (space, tab, line break, newline, form feed)  
**Note:** Only present in BBEdit Pro 5.1 and Lite 4.6 or greater  
 |  
| `\S` | non whitespace | matches any non whitespace character (anything not matched by \\s)  
**Note:** Only present in BBEdit Pro 5.1 and Lite 4.6 or greater  
 |  
| `\w` | word character | matches any word character. According to the release notes: "A word is any run of non-word-break characters bounded by word breaks. Word characters in the ASCII range are generally alphanumeric, and characters whose value is greater than 127 are also considered word characters." Typically this is letters, numbers, and underscores, but also includes some other characters you might not cosinder word characters.  
**Note:** Only present in BBEdit Pro 5.1 and Lite 4.6 or greater  
 |  
| `\W` | non word character | matches any non word character (anything not matched by \\w)  
**Note:** Only present in BBEdit Pro 5.1 and Lite 4.6 or greater  
 |  
| `\`*character* | represents a character that is normally a [special character](http://www.anybrowser.org/bbedit/grep.html#star1) | \\\\ means \\, \\. means ., etc.  
 |  
| `[`*any series of characters*`]` | represents any of the characters inside the brackets | \[abc\] represents an a, b, or c  
 |  
| `[`*any character-another character*`]` | represents any characters within the range of characters specified | \[a-c\] represents a, b, or c  
 |  
| `[^`*any series of characters*`]` | represents any character except the ones specified after the ^ | \[^c3\] represents any character except c or 3  
 |

## Representing Multiple Character Patterns in Searches

| Character Typed | What it Represents | Example  
 |  
| --- | --- | --- |  
| `?` | represents 0 or 1 of the previous character | ba?t matches bat or bt, but not baat  
 |  
| `*` | represents 0 or more of the previous character | ba\*t matches bt, bat, baat, etc. but not boat  
 |  
| `+` | represents 1 or more of the previous character | ba+t matches bat, baat, etc. but not bt  
 |  
| *pattern1*`|`*pattern2* | represents either of the patterns specified (or) | ba|t matches ba or t but not bat (it will match ba and then t for two matches instead of one)  
 |  
| `(`*pattern*`)`*one of the above special characters* | same as above, but treats the characters within the parenthesis as a group | (ba)\*t will match t, bat, babat, but not bt  
 |

## Saving Patterns in Searches

| Character Typed | What it Represents | Example  
 |  
| --- | --- | --- |  
| `(`*pattern*`)` | saves the match to the pattern to be used for replacement, in order of the patterns matched. The first pattern is saved in \\1, the second in \\2, etc. These can be used in the replacement to enter the pattern that was matched. | a(b.c) would save whatever b.c matched in \\1 for replacement, so if it were to match bjc, and you use \\1 in the replacement, bjc gets entered in its place  
 |

## Characters to Use in Replacement Patterns

| Character Typed | What it Represents | Example  
 |  
| --- | --- | --- |  
| `&` | the entire pattern matched in the search | if you search for a@b.c and BBEdit finds, a@bjc then that is what & will represent in the replacement pattern  
 |  
| `\`*digit* | the saved pattern for the digit you specified. BBEdit saves patterns in order from \\1 to \\9, then \\0 | if you search for (a@b.)c, then the part matched within the parenthesis is the first saved pattern, and you can use \\1 in the replacement pattern for it  
 |  
| `\`*character* | represents a character that is normally a [special character](http://www.anybrowser.org/bbedit/grep.html#star1) | \\\\ means \\, \\& means &, etc.  
 |

**Special characters** in search patterns that need to be escaped with a `\` are: `.#^$\?+*|[]()`  
Inside `[]`'s, you also need to escape `-`  
In replacement patterns, only the following characters need escaping: `&\`.

## Example Patterns

Here are some example search and replace patterns that may be useful and will hopefully give you an idea of how grep works.

Search: `<(/?)B>`  
Replace: `<\1STRONG>`

The above pattern will search for any start or end B tags and replace them with STRONG tags. You can easily change this pattern to work for any tags you want, as long as they don't have any attributes.

But let's say you want to replace all BIG tags with a FONT SIZE="+1". Now you need to change the pattern because you have to take the attributes into account, and distinguish between beginning and the end of the tag. You could do it on two steps, one by replacing the <BIG> and a second step to replace the </BIG>. But if you prefer, you can use grep to do this in one step.

If you knew all the BIG start and end tags were on the same line, and there was only one of them per line, you could do this:

Search: `<BIG>(.*)</BIG>`  
Replace: `<FONT SIZE="+1">\1</FONT>`

There are problems with the above example. First of all, `.` doesn't match returns, so if your start tag is on one line, and your end tag on another, it won't get replaced. Second of all, BBEdit's grep is greedy, which means it goes for the biggest match it can, even if there are smaller matches inside it. So if you have a line that looks like this:

<BIG>test</BIG> another <BIG>test</BIG>

it would get turned into this:

<FONT SIZE="+1">test</BIG> another <BIG>test</FONT>

So how do you solve it? You can do this:

Search: `<BIG>([^<]*)<BIG>`  
Replace: `<FONT SIZE="+1">\1</FONT>`

`[^<]*` will match zero or more of any character except <, so it will terminate the match at the first < it sees. This will still not work if you have other tags inside the BIG tags, but it's better than the previous example.

One more examplelets remove all leading whitespace from the beginning of lines.

Search: `^[ \t]+`  
Replace:

Here we look for one or more spaces or tabs at the beginning of a line, and replace them with nothing. This time, it pays for BBEdit to be greedy. If BBedit stopped at the first match it found, it would only replace one space or tab at a time, which would require the search/replace to be run a lot of times to finish. This way you catch all the spaces in one fell swoop. Another way to do the same search would be:

Search: `^[ \t]+([^ \t])`  
Replace: `\1`

In this case we look for one or more spaces or tabs at the beginning of a line, and then one character which isn't a space or tab, and replace the whole thing with just the ending character. It isn't as pretty as the previous example, and there don't seem to be any advantages to doing it this way, other than just showing an alternate way to do it.

To extend this example to deal with a common problem, let's say you wanted to replace all instances of **more** than one space with a tab (such as when converting a space delimited file to tab delimited). You could create this expression based on either of the above examples. I will use **\\s** below to represent a space to make it easier to see.

Search: `\s\s+`  
Replace: `\t`

This would look for a space, followed by one or more spaces, thereby not replacing spaces standing alone. Another method of doing this is:

Search: `\s\s+([^\s])`  
Replace: `\t\1`

This would work similarly, as above, but uses a non-space to identify where to stop the match, and then puts that character back in the replace. The first method is better for most uses, but this alternate method can be extended to more complicated matches that require a boundary to be set.

## Grep Tips

Make sure to use the "add this pattern…" option in the find window to save commonly used patterns for reuse. Ideally it's a good idea to save a general pattern, rather than the exact one you use, so you can remember what to replace with later, i.e. save Search: <(/?)TAG1> Replace: <\\1TAG2> instead of using the B and STRONG from the example. It makes it easier to remember you can use it for other tags later.

You can remove patterns you don't use from the saved pattern list under the Preferences, Grep Patterns section. If you see ones in there you'll never have a need for, go ahead and remove themit'll make it easier to access the ones you do use.

If you want to do multiple searches and replaces in one fell swoop, or you need to do a search and replace that requires more complex grep support than what BBEdit will handle, you may want to look at the Perl Filters option in BBEdit Pro (I believe these tools are also available separately for Lite users). If you learn a little about Perl regular expressions (which are very similar to those in BBEdit, but have a lot more options available), you can write very useful filters that are easy to run from BBEdit. Another option is AppleScript, which can make it possible to automate the process of multiple search/replaces.

If you have any really useful patterns that are complex enough to be difficult to come by on your own, and general enough to be useful to other BBEdit users, [mail](http://www.anybrowser.org/sendmail.shtml) them to me and I'll post them here.

## Troubleshooting Grep Patterns

If your pattern isn't doing what you think it should, here are some possible reasons:

- You may be using a [special character](http://www.anybrowser.org/bbedit/grep.html#star1) without meaning to, and you should escape it with a `\` to keep it from being interpreted incorrectly.
- You may be using a grep expression not supported in BBEdit. Many of the extended features of grep, such as those found in Perl, aren't supported in BBEdit. Using \\w won't match word characters in BBEdit like it does in Perl. Also, some things, like digits, are represented differently in different programs supporting grep expressions (for instance, BBEdit uses # to represent a digit, while Perl uses \\d).
- Your pattern may be too long. There is a limit in BBEdit on the length of patterns. If you need to use a really long pattern, you may want to Perl Filters or a MacPerl script called adsfind instead.

## For More Information

To learn more about regular expressions, here are some other references:

- O'Reilly and Associates [Mastering Regular Expressions](http://www.ora.com/catalog/regex/)
- O'Reilly and Asssociates [Learning Perl](http://www.ora.com/catalog/lperl2/)

---

[Cari D. Burstein](http://www.anybrowser.org/cdaveb/) - [cdaveb **AT** anybrowser **DOT** org](http://www.anybrowser.org/sendmail.shtml)

[![Built With BBEdit](http://www.anybrowser.org/images/bbedit_badge1.gif)](http://www.barebones.com/builtwith.html) [![Content Enhanced- use any browser](http://www.anybrowser.org/campaign/bvgraphics/enhanced.gif)](http://www.anybrowser.org/campaign/)

---
