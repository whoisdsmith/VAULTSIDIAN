So the ***Regex Cookbook*** (buy it!) gives a couple of regular-expression replacement scenarios for this:

**Find-what** zone: `(?s)^([^\r\n]*)$(.*?)(?:(?:\r?\n|\r)\1$)+`  
***OR***  
**Find-what** zone: `(?-s)^(.*)$([\s\S]*?)(?:(?:\r?\n|\r)\1$)+`  
For either choice the **Replace-with** zone is set to `\1\2`

Some changes may be made to these expressions for more typical use in Notepad++:

**Find-what** zone: `(?-s)^(.*)$(?s)(.*?)(?:\R\1$)+`  
**Replace-with** zone: `\1\2`  
**Wrap around** checkbox: ticked  
**Action**: Press **Replace All** button REPEATEDLY until status bar indicates: “*Replace All: 0 occurrences were replaced.*”

But…there are some interesting things to note in the Cookbook regexes:

- `[^\r\n]` may be used in place of “`(?-s)` with a later occurring `.`” to mean “any character but not including (or across) line-ending characters”
- `[\s\S]` may be used in place of “`(?s)` with a later occurring `.`” to mean “any character at all (including line-ending characters)”

I like these as they put all the functionality in one place in the regex.

[1 Reply Last reply](https://community.notepad-plus-plus.org/topic/14835/remove-duplicate-lines-from-unsorted-keeping-first?sort=newest_to_oldest#) [Reply](https://community.notepad-plus-plus.org/topic/14835/remove-duplicate-lines-from-unsorted-keeping-first?sort=newest_to_oldest#) [Quote](https://community.notepad-plus-plus.org/topic/14835/remove-duplicate-lines-from-unsorted-keeping-first?sort=newest_to_oldest#)[](https://community.notepad-plus-plus.org/topic/14835/remove-duplicate-lines-from-unsorted-keeping-first?sort=newest_to_oldest#)
