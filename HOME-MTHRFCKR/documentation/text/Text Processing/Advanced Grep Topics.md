# Advanced Grep Topics

**Advanced Grep Topics**  
If you are new to grep, it is possible that the topics covered in this section will not make much sense to you. That's OK. The best way to learn grep is to use it in real life, not by reading example patterns. In many cases, the basic grep syntax covered previously in this chapter will be all that you need.  
**Matching Nulls**  
The grep engine used in previous versions of BBEdit was unable to search text that contained null characters (ASCII value zero). This limitation is removed in BBEdit 6.5. Here's one way to match a null:

```
    \x{0}
```

**Backreferences**  
The following charts explain the rules BBEdit uses for determining backreferences.  
**In Search Patterns**

<table><tbody><tr><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Modifier</b>&nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Effect</b>&nbsp;&nbsp;</span></td></tr><tr><td colspan="3"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">\0 &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">A backslash followed by a zero is an octal character reference. Up to two further octal characters are read. Thus, "\040" will match a space character, and "\07" will match the ASCII BEL (\x07), but "\08" will match an ASCII null followed by the digit 8 (because octal characters only range from 0-7).&nbsp;&nbsp;</span></td></tr><tr><td colspan="3"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">\1-9 &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">A backslash followed by a single decimal digit from one to nine is always a backreference to the Nth captured subpattern.&nbsp;&nbsp;</span></td></tr><tr><td colspan="3"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">\10-99 &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">A backslash followed by two decimal digits, which taken together form the integer N (ranging from 10 to 99), is a backreference to the Nth captured subpattern, *if* there exist N capturing sets of parentheses in the pattern. If there are fewer than N captured subpatterns, the grep engine will instead look for up to three octal digits following the backslash. Any subsequent digits stand for themselves. So, in a search pattern, "\11" is a backreference if there are 11 or more sets of capturing parenthesis in the pattern. If not, it matches a tab. "\011" always matches a tab. "\81" is a backreference if there are 81 or more captured subpatterns, but matches an ASCII null followed by the two characters "8" and "1" otherwise. &nbsp;&nbsp;</span></td></tr></tbody></table>
**In Character Classes**
<table><tbody><tr><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Modifier</b>&nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Effect</b>&nbsp;&nbsp;</span></td></tr><tr><td colspan="3"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">\OCTAL &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">Inside a character class, a backslash followed by up to three octal digits generates a single byte character reference from the least significant eight bits of the value. Thus, the character class "[\7]" will match a single byte with octal value 7 (equivalent to "\x07"). "[\8]" will match a literal "8" character.&nbsp;&nbsp;</span></td></tr></tbody></table>
**In Replacement Patterns**
<table><tbody><tr><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Modifier</b>&nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Effect</b>&nbsp;&nbsp;</span></td></tr><tr><td colspan="3"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">\NNN+ &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">If more than two decimal digits follow the backslash, only the first two are considered part of the backreference. Thus, "\111" would be interpreted as the 11th backreference, followed by a literal '1'. You may use a leading zero; for example, if in your replacement pattern you want the first backreference followed by a literal '1', you can use "\011". (If you use "\11", you'll get the 11th backreference, even if it is empty.)&nbsp;&nbsp;</span></td></tr><tr><td colspan="3"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">\NN &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">If two decimal digits follow the backslash, which taken together represent the value N, and if there is an Nth captured substring, then all three characters are replaced with that substring. If there is not an Nth captured substring, then all three characters are discarded, i.e., the backreference is replaced with the empty string.&nbsp;&nbsp;</span></td></tr><tr><td colspan="3"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">\N &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">If there is only a single digit N following the backslash and there is an Nth captured substring, then both characters are replaced with that substring. Otherwise, both characters are discarded, i.e., the backreference is replaced with the empty string. In replacement patterns, \0 is a backreference to the entire match (exactly equivalent to '&amp;'). &nbsp;&nbsp;</span></td></tr></tbody></table>
**POSIX-Style Character Classes**
BBEdit now provides support for POSIX-style character classes. These classes are used in the form \[:CLASS:\] , and are only available inside regular character classes (in other words, inside another set of square brackets).
```
Class Meaning
alnum letters and digits
alpha letters
ascii character codes 0 - 127
cntrl control characters
digit decimal digits (same as \d)
graph printing characters, excluding space
lower lower case letters
print printing characters, including space
punct punctuation characters
space white space (same as \s)
upper upper case letters
word "word" characters (same as \w)
xdigit hexadecimal digits
```
For example: \[\[:digit:\]\]+ is the same as: \[\\d\]+
POSIX-style character class names are case-sensitive.
It is easy to forget that POSIX-style character classes are only available inside regular character classes. The pattern \[:space:\] , without enclosing square brackets, is just a character class consisting of the characters \`:', 'a', 'c', 'e', 'p', and 's'.
The names "ascii" and "word" are Perl extensions; the others are defined by the POSIX standard. Another Perl extension supported by BBEdit is negated POSIX-style character classes, which are indicated by a ^ after the colon. For example, to match any run of non-digit characters:
```
    [[:^digit:]]+
```
**Non-Capturing Parentheses**
As in previous versions of BBEdit, bare parentheses cluster and capture the subpatterns they contain. The portion of the matching pattern contained within the first pair of parentheses is available in the backreference \\1, the second in \\2, etc.
Opening parentheses are counted from left to right to determine the numbers of the captured subpatterns. For example, if the following grep pattern:
```
    ((red|white) (king|queen))
```
is matched against the text "red king", the backreferences will be set as follows:
```
    \1 "red king"
```
```
    \2 "red"
```
```
    \3 "king"
```
Sometimes, however, parentheses are needed for only for clustering, not capturing. BBEdit now supports non-capturing parentheses, using the syntax:
```
    (?:PATTERN)
```
That is, if an open parenthesis is followed by "?:", the subpattern matched by that pair of parentheses is not counted when computing the backreferences. For example, if the text "red king" is matched against the pattern:
```
    (?:(red|white) (king|queen))
```
the backreferences will be set as follows:
```
\1 "red"
\2 "king"
```
**Perl-Style Pattern Extensions**
BBEdit 6.5's grep engine supports several extended sequences, which provide grep patterns with super-powers from another universe. Their syntax is in the form:
```
    (?KEY…)
```
in other words, an open parenthesis followed by a question mark, followed by a KEY for the particular grep extension, followed by the rest of the subpattern and a closing parenthesis. This syntax--specifically, an open parenthesis followed by a question mark--was not valid in older versions of BBEdit, thus, none of these extensions will conflict with old patterns.
We have already seen one such extension in the previous section of this document--non-capturing parentheses: (?:…). The remainder are listed in the chart below, and discussed in detail afterward.
```
Extension Meaning
(?:…) Cluster-only parentheses, no capturing
(?#…) Comment, discard all text between the parens
(?imsx-imsx) Enable/disable pattern modifiers
(?imsx-imsx:…) Cluster-only parens with modifiers
(?=…) Positive lookahead assertion
(?!…) Negative lookahead assertion
(?<=…) Positive lookbehind assertion
(?<!…) Negative lookbehind assertion
(?()…|…) Match with if-then-else
(?()…) Match with if-then
(?>…) Match non-backtracking subpattern ("once-only")
(?R) Recursive pattern
```
**Comments**
The sequence (?# marks the start of a comment which continues up to the next closing parenthesis. Nested parentheses are not permitted. The characters that make up a comment play no part in the pattern matching at all.
```
Search for: foo(?# Hello, this is a comment)bar
Will match: foobar
```
**Pattern Modifiers**
The settings for case sensitivity, multi-line matching, whether the dot character can match returns, and "extended syntax" can be turned on and off within a pattern by including sequences of letters between "(?" and ")".
<table><tbody><tr><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Modifier</b>&nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Meaning</b>&nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2"><b>Default</b>&nbsp;&nbsp;</span></td></tr><tr><td colspan="5"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">i &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">case insensitive &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">according to Case Sensitive checkbox in Find dialog &nbsp;&nbsp;</span></td></tr><tr><td colspan="5"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">m &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">allow ^ and $ to match at \r &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">ON &nbsp;&nbsp;</span></td></tr><tr><td colspan="5"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">s &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">allow . to match \r &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">OFF &nbsp;&nbsp;</span></td></tr><tr><td colspan="5"><hr></td></tr><tr><td nowrap=""><span face="Lucida Grande,Geneva,Arial" size="2">x &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">ignore most whitespace and allow inline commentsin grep patterns &nbsp;&nbsp;</span></td><td></td><td><span face="Lucida Grande,Geneva,Arial" size="2">OFF &nbsp;&nbsp;</span></td></tr><tr><td colspan="5"><hr noshade="" size="1"></td></tr></tbody></table>
i -- By default, BBEdit obeys the "Case Sensitive" checkbox in the Find dialog (or the corresponding property of the search options when using the scripting interface). The (?i) option overrides this setting.
m -- By default, BBEdit's grep engine will match the ^ and $ metacharacters after and before returns, respectively. If you turn this option off with (?-m) , ^ will only match at the beginning of the document, and $ will only match at the end of the document. (If that's what you want, however, you should consider using the new \\A, \\Z, and \\z metacharacters instead of ^ and $.)
s -- By default, the magic dot metacharacter . matches any character except return (\`\\r'). If you turn this option on with (?s) , however, dot will match any character. Thus, the pattern (?s).+ will match an entire document.
x -- When turned on, this option changes the meaning of most whitespace characters (notably, tabs and spaces) and #. Literal whitespace characters are ignored, and the # character starts a comment that extends until a literal return or the \`\\r' escape sequence is encountered. Ostensibly, this option intends to let you write more "readable" patterns.
Perl programmers should already be familiar with these options, as they correspond directly to the -imsx options for Perl's m// and s/// operators. Unadorned, these options turn their corresponding behavior on; when preceded by a hyphen (-), they turn the behavior off. Setting and unsetting options can occur in the same set of parentheses.
The scope of these option changes depends on where in the pattern the setting occurs. For settings that are outside any subpattern, the effect is the same as if the options were set or unset at the start of matching. The following patterns all behave in exactly the same way:
```
    (?i)abc
```
```
    a(?i)bc
```
```
    ab(?i)c
```
```
    abc(?i)
```
In other words, all four of the above patterns will match without regard to case. Such "top level" settings apply to the whole pattern (unless there are other changes inside subpatterns). If there is more than one setting of the same option at the top level, the right-most setting is used.
If an option change occurs inside a subpattern, the effect is different. An option change inside a subpattern affects only that part of the subpattern that follows it, so, if the "Case Sensitive" checkbox is turned on:
```
Search for: (a(?i)b)c
Will match: "abc" or "aBc"
```
and won't match anything else. (But if "Case Sensitive" is turned off, the " (?i) " in the above pattern is superfluous and has no effect.) By this means, options can be made to have different settings in different parts of the pattern. Any changes made in one alternative do carry on into subsequent branches within the same subpattern. For example:
```
Search for: (a(?i)b|c)
```
matches "ab", "aB", "c", and "C", even though when matching "C", the first branch is abandoned before the option setting.
These options can also be set using the clustering (non-capturing) parentheses syntax defined earlier, by inserting the option letters between the \`?' and \`:'. The scope of options set in this manner is limited to the subpattern contained therein. Examples:
```
Search for: (?i:saturday|sunday)
Will match: "SATURDAY" or "Saturday" or "SUNday" (etc.)
Search for: (?i:foo)(?-i:bar)
Will match: "foobar" or "FOObar"
Won't match: "FOOBAR" or "fooBAR"
```
**Positional Assertions**
Positional assertions "anchor" a pattern, without actually matching any characters. Simple assertions have already been described: those which are invoked with the escape sequences \\b, \\B, \\A, \\Z, \\z, ^ and $. For example, the pattern \\bfoo\\b will only match the string "foo" if it has word breaks on both sides, but the \\b's do not themselves match any characters; the entire text matched by this pattern are the three characters 'f', 'o', and 'o'.
Lookahead and lookbehind assertions work in a similar manner, but allow you to test for arbitrary patterns to anchor next to. If you have ever said to yourself, "I would like to match 'foo', but only when it is next to 'bar'," lookaround assertions fill that need.
Positive lookahead assertions begin with " (?= ", and negative lookahead assertions begin with " (?! ". For example:
```
    \w+(?=;)
```
will match any word followed by a semicolon, but the semicolon is not included as part of the match.
```
    foo(?!bar)
```
matches any occurrence of "foo" that is not followed by "bar". Note that the apparently similar pattern:
```
    (?!foo)bar
```
does not find an occurrence of "bar" that is preceded by something other than "foo"; it finds any occurrence of "bar" whatsoever, because the assertion (?!foo) is always true when the next three characters are "bar". A lookbehind assertion is needed to achieve this effect.
Positive lookbehind assertions start with " (?<= ", and negative lookbehind assertions start with " (?<! ". For example:
```
    (?<!foo)bar
```
does find an occurrence of "bar" that is not preceded by "foo". The contents of a lookbehind assertion are restricted such that all the strings it matches must have a fixed length. However, if there are several alternatives, they do not all have to have the same fixed length. Thus
```
    (?<=Martin|Lewis)
```
is permitted, but
```
    (?<!dogs?|cats?)
```
causes an error. Branches that match different length strings are permitted only at the top level of a lookbehind assertion. This is different compared with Perl 5.005, which requires all branches to match the same length of string. An assertion such as
```
    (?<=ab(c|de))
```
is not permitted, because its single top-level branch can match two different lengths, but it is acceptable if rewritten to use two top-level branches:
```
    (?<=abc|abde)
```
The implementation of lookbehind assertions is, for each alternative, to temporarily move the current position back by the fixed width and then try to match. If there are insufficient characters before the current position, the match is deemed to fail. (Lookbehinds in conjunction with non-backtracking \[a.k.a. "once-only"\] subpatterns can be particularly useful for matching at the ends of strings; an example is given in the section on once-only subpatterns below.)
Several assertions (of any sort) may occur in succession. For example,
```
    (?<=\d{3})(?<!999)foo
```
matches "foo" preceded by three digits that are not "999". Notice that each of the assertions is applied independently at the same point in the subject string. First there is a check that the previous three characters are all digits, and then there is a check that the same three characters are not "999". This pattern does not match "foo" preceded by six characters, the first of which are digits and the last three of which are not "999". For example, it doesn't match "123abcfoo". A pattern to do that is:
```
    (?<=\d{3}…)(?<!999)foo
```
This time the first assertion looks at the preceding six characters, checking that the first three are digits, and then the second assertion checks that the preceding three characters are not "999". Assertions can be nested in any combination. For example,
```
    (?<=(?<!foo)bar)baz
```
matches an occurrence of "baz" that is preceded by "bar" which in turn is not preceded by "foo", while
```
    (?<=\d{3}(?!999)…)foo
```
is another pattern which matches "foo" preceded by three digits and any three characters that are not "999".
Assertion subpatterns are not capturing subpatterns, and may not be repeated, because it makes no sense to assert the same thing several times. If any kind of assertion contains capturing subpatterns within it, these are counted for the purposes of numbering the capturing subpatterns in the whole pattern. However, substring capturing is carried out only for positive assertions, because it does not make sense for negative assertions.
**Conditional Subpatterns**
Conditional subpatterns allow you to apply "if-then" or "if-then-else" logic to pattern matching. The "if" portion can either be an integer between 1 and 99, or an assertion. The two forms of syntax are:
```
if-then: (?(condition)yes-pattern)
if-then-else: (?(condition)yes-pattern|no-pattern)
```
If the condition evaluates as true, the "yes-pattern" portion attempts to match. Otherwise, the "no-pattern" portion does (if there is a "no-pattern").
If the "condition" text between the parentheses is an integer, it corresponds to the backreferenced subpattern with the same number. (Don't precede the number with a backslash.) If the corresponding backreference has previously matched in the pattern, then the condition is satisfied. Here's an example of how this can be used. Let's say we want to match the words "red" or "blue", and refer to whichever word is matched in the replacement pattern. That's easy:
```
    (red|blue)
```
To make it harder, let's say that if (and only if) we match "blue", we want to optionally match a space and the word "car" if they follow directly afterward. In other words, we want to match "red", "blue", or if possible, "blue car", but we do not want to match "red car". We can't use the pattern:
```
    (red|blue)( car)?
```
because that will match "red car". Nor can we use:
```
    (red|blue car|blue)
```
because in our replacement pattern, we want the backreference to only contain "red" or "blue", without the " car". Using a conditional subpattern, however, we can search for:
```
    ((blue)|(red))(?(2) car)?
```
Here's how this pattern works. First, we start with " ((blue)|(red)) ". When this subpattern matches "blue", \\1 and \\2 are set to "blue", and \\3 is empty. When it matches "red", \\1 and \\3 are set to "red", and \\2 is empty.
Next comes the conditional subpattern " (?(2) car)? ". The conditional test is on "2", the second backreferenced subpattern: if \\2 is set, which in our case means it has matched the word "blue", then it will try to match " car". If \\2 is not set, however, the entire conditional subpattern is skipped. The question mark at the end of the pattern makes this conditional match optional, even if \\2 is set to "blue".
Here's an example that uses an assertion for the condition, and the if-then-else form. Let's say we want to match a run of digits of any length, followed by either " is odd" or " is even", depending on whether the matched digits end with an odd or even digit.
```
    \d+(?(?<=[13579]) is odd| is even)
```
This pattern starts with "\\d+" to match the digits. Next comes a conditional subpattern, with a positive lookbehind assertion as the condition to be satisfied. The lookbehind assertion is true only if the last character matched by \\d+ was also in the character class \[13579\]. If that's true, then we next try to match " is odd"; if it isn't, we try to match " is even". Thus, this pattern will match "123 is odd", "8 is even", etc., but will not match "9 is even" or "144 is odd".
**Once-Only Subpatterns**
With both maximizing (greedy) and minimizing (non-greedy) repetition, failure of what follows normally causes the repeated item to be reevaluated to see if a different number of repeats allows the rest of the pattern to match. Sometimes it is useful to prevent this, either to change the nature of the match, or to cause it to fail earlier than it otherwise might, when the author of the pattern knows there is no point in carrying on.
Consider, for example, the pattern " \\d+foo " when matching against the text "123456bar".
After matching all 6 digits and then failing to match "foo", the normal action of the grep engine is to try again with only 5 digits matching the \\d+ item, and then with 4, and so on, before ultimately failing. Once-only subpatterns provide the means for specifying that once a portion of the pattern has matched, it is not to be re-evaluated in this way, so the matcher would give up immediately on failing to match "foo" the first time. The notation is another kind of special parenthesis, starting with " (?> ", as in this example:
```
    (?>\d+)bar
```
This kind of parentheses "locks up" the part of the pattern it contains once it has matched, and a failure further into the pattern is prevented from backtracking into it. Backtracking past it to previous items, however, works as normal.
In most situations, such as in the example above, the time saved by using once-only subpatterns is insignificant--a few small fractions of a second, at most. With some complicated grep patterns or with humongous lines of text, however, you can save tremendous amounts of time using once-only subpatterns.
Once-only subpatterns are not capturing subpatterns. Simple cases such as the above example can be thought of as a maximizing repeat that must swallow everything it can. So, while both \\d+ and \\d+? are prepared to adjust the number of digits they match in order to make the rest of the pattern match, (?>\\d+) can only match an entire sequence of digits.
Once-only subpatterns can be used in conjunction with lookbehind assertions to specify efficient matching at the end of a line of text. Consider a simple pattern such as:
```
    abcd$
```
when applied to a long line of text which does not match (in other words, a long line of text that does not end with "abcd"). Because matching proceeds from left to right, the grep engine will look for each "a" in the subject and then see if what follows matches the rest of the pattern. If the pattern is specified as:
```
    ^.*abcd$
```
the initial .\* matches the entire line at first, but when this fails (because there is no following "a"), it backtracks to match all but the last character, then all but the last two characters, and so on. Once again the search for "a" covers the entire string, from right to left, so we are no better off. However, if the pattern is written as:
```
    ^(?>.*)(?<=abcd)
```
there can be no backtracking for the .\* item; it can match only the entire line. The subsequent lookbehind assertion does a single test on the last four characters. If it fails, the whole match fails immediately. For long strings, this approach makes a significant difference to the processing time.
When a pattern contains an unlimited repeat inside a subpattern that can itself be repeated an unlimited number of times, the use of a once-only subpattern is the only way to avoid some failing matches taking a very long time (literally millions or even billions of years, in some cases!). The pattern:
```
    (\D+|<\d+>)*[!?]
```
matches an unlimited number of substrings that either consist of non-digits, or digits enclosed in <>, followed by either ! or ?. When it matches, it runs quickly. However, if it is attempts to match this line of text:
```
    aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
```
it takes a long time before reporting failure. So long, in fact, that it will effectively "freeze" BBEdit. This isn't really a crash, per se, but left to run on its own, it might take years before it finally fails. (We're not sure, frankly, because much like determining how many licks it takes to get to the center of a Tootsie Pop, we don't feel like waiting long enough to find out.)
The reason this takes so long to fail is because the string can be divided between the two repeats in a large number of ways, and all have to be tried before the grep engine knows for certain that the pattern won't match. (The example used \[!?\] rather than a single character at the end, because both PCRE and Perl have an optimization that allows for fast failure when a single character is used. They remember the last single character that is required for a match, and fail early if it is not present in the string.) If the pattern is changed to
```
    ((?>\D+)|<\d+>)*[!?]
```
sequences of non-digits cannot be broken, and failure happens quickly.
**Recursive Patterns**
Consider the problem of matching a string in parentheses, allowing for unlimited nested, balanced parentheses. Without the use of recursion, the best that can be done is to use a pattern that matches up to some fixed depth of nesting. It is not possible to handle an arbitrary nesting depth. Perl 5.6 has provided an experimental facility that allows regular expressions to recurse (amongst other things). It does this by interpolating Perl code in the expression at run time, and the code can refer to the expression itself. Obviously, BBEdit's grep engine cannot support the interpolation of Perl code. Instead, the special item (?R) is provided for the specific case of recursion. The following recursive pattern solves the parentheses problem:
```
    \(((?>[^()]+)|(?R))*\)
```
First it matches an opening parenthesis. Then it matches any number of substrings which can either be a sequence of non-parentheses, or a recursive match of the pattern itself (i.e. a correctly parenthesized substring). Finally there is a closing parenthesis.
This particular example pattern contains nested unlimited repeats, and so the use of a once-only subpattern for matching strings of non-parentheses is important when applying the pattern to strings that do not match. For example, when it tries to match against this line of text:
```
    (aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa()
```
it yields "no match" quickly. However, if a once-only subpattern is not used, the match runs for a very long time indeed because there are so many different ways the + and \* repeats can carve up the subject, and all have to be tested before failure can be reported.
