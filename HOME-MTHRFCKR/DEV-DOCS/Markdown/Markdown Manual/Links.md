{{($page.frontmatter.start = 493) ? null : null}}
### Links

A link contains [link text](https://github.github.com/gfm/#link-text) (the visible text), a [link destination](https://github.github.com/gfm/#link-destination) (the URI that is the link destination), and optionally a [link title](https://github.github.com/gfm/#link-title). There are two basic kinds of links in Markdown. In [inline links](https://github.github.com/gfm/#inline-link) the destination and title are given immediately after the link text. In [reference links](https://github.github.com/gfm/#reference-link) the destination and title are defined elsewhere in the document.  
A [link text](https://github.github.com/gfm/#link-text) consists of a sequence of zero or more inline elements enclosed by square brackets (`[` and `]`). The following rules apply:  

*   Links may not contain other links, at any level of nesting. If multiple otherwise valid link definitions appear nested inside each other, the inner-most definition is used.
*   Brackets are allowed in the [link text](https://github.github.com/gfm/#link-text) only if (a) they are backslash-escaped or (b) they appear as a matched pair of brackets, with an open bracket `[`, a sequence of zero or more inlines, and a close bracket `]`.
*   Backtick [code spans](https://github.github.com/gfm/#code-spans), [autolinks](https://github.github.com/gfm/#autolinks), and raw [HTML tags](https://github.github.com/gfm/#html-tag) bind more tightly than the brackets in link text. Thus, for example, ``[foo`]` `` could not be a link text, since the second `]` is part of a code span.
*   The brackets in link text bind more tightly than markers for [emphasis and strong emphasis](https://github.github.com/gfm/#emphasis-and-strong-emphasis). Thus, for example, `*[foo*](url)` is a link.

A [link destination](https://github.github.com/gfm/#link-destination) consists of either  

*   a sequence of zero or more characters between an opening `<` and a closing `>` that contains no spaces, line breaks, or unescaped `<` or `>` characters, or
*   a nonempty sequence of characters that does not start with `<`, does not include ASCII space or control characters, and includes parentheses only if (a) they are backslash-escaped or (b) they are part of a balanced pair of unescaped parentheses.(Implementations may impose limits on parentheses nesting to avoid performance issues, but at least three levels of nesting should be supported.)

A [link title](https://github.github.com/gfm/#link-title) consists of either  

*   a sequence of zero or more characters between straight double-quote characters (`"`), including a `"`character only if it is backslash-escaped, or
*   a sequence of zero or more characters between straight single-quote characters (`'`), including a `'`character only if it is backslash-escaped, or
*   a sequence of zero or more characters between matching parentheses (`(...)`), including a `(` or `)` character only if it is backslash-escaped.
                                                 
Although [link titles](https://github.github.com/gfm/#link-title) may span multiple lines, they may not contain a [blank line](https://github.github.com/gfm/#blank-line).  
An [inline link](https://github.github.com/gfm/#inline-link) consists of a [link text](https://github.github.com/gfm/#link-text) followed immediately by a left parenthesis `(`, optional [whitespace](https://github.github.com/gfm/#whitespace), an optional [link destination](https://github.github.com/gfm/#link-destination), an optional [link title](https://github.github.com/gfm/#link-title) separated from the link destination by [whitespace](https://github.github.com/gfm/#whitespace), optional [whitespace](https://github.github.com/gfm/#whitespace), and a right parenthesis `)`. The link’s text consists of the inlines contained in the [link text](https://github.github.com/gfm/#link-text)(excluding the enclosing square brackets). The link’s URI consists of the link destination, excluding enclosing `<...>` if present, with backslash-escapes in effect as described above. The link’s title consists of the link title, excluding its enclosing delimiters, with backslash-escapes in effect as described above.  
Here is a simple inline link:  
<Example :index="$page.frontmatter.start++"/>

The title may be omitted:  
<Example :index="$page.frontmatter.start++"/>

Both the title and the destination may be omitted:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The destination can only contain spaces if it is enclosed in pointy brackets:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The destination cannot contain line breaks, even if enclosed in pointy brackets:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The destination can contain `)` if it is enclosed in pointy brackets:
<Example :index="$page.frontmatter.start++"/>

Pointy brackets that enclose links must be unescaped:
<Example :index="$page.frontmatter.start++"/>

These are not links, because the opening pointy bracket is not matched properly:
<Example :index="$page.frontmatter.start++"/>

Parentheses inside the link destination may be escaped:  
<Example :index="$page.frontmatter.start++"/>

Any number of parentheses are allowed without escaping, as long as they are balanced:  
<Example :index="$page.frontmatter.start++"/>

However, if you have unbalanced parentheses, you need to escape or use the `<...>` form:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Parentheses and other symbols can also be escaped, as usual in Markdown:  
<Example :index="$page.frontmatter.start++"/>

A link can contain fragment identifiers and queries:  
<Example :index="$page.frontmatter.start++"/>

Note that a backslash before a non-escapable character is just a backslash:  
<Example :index="$page.frontmatter.start++"/>

URL-escaping should be left alone inside the destination, as all URL-escaped characters are also valid URL characters. Entity and numerical character references in the destination will be parsed into the corresponding Unicode code points, as usual. These may be optionally URL-escaped when written as HTML, but this spec does not enforce any particular policy for rendering URLs in HTML or other formats. Renderers may make different decisions about how to escape or normalize URLs in the output.  
<Example :index="$page.frontmatter.start++"/>

Note that, because titles can often be parsed as destinations, if you try to omit the destination and keep the title, you’ll get unexpected results:  
<Example :index="$page.frontmatter.start++"/>

Titles may be in single quotes, double quotes, or parentheses:  
<Example :index="$page.frontmatter.start++"/>

Backslash escapes and entity and numeric character references may be used in titles:  
<Example :index="$page.frontmatter.start++"/>

Titles must be separated from the link using a [whitespace](https://github.github.com/gfm/#whitespace). Other [Unicode whitespace](https://github.github.com/gfm/#unicode-whitespace) like non-breaking space doesn’t work.  
<Example :index="$page.frontmatter.start++"/>

Nested balanced quotes are not allowed without escaping:  
<Example :index="$page.frontmatter.start++"/>

But it is easy to work around this by using a different quote type:  
<Example :index="$page.frontmatter.start++"/>

(Note: `Markdown.pl` did allow double quotes inside a double-quoted title, and its test suite included a test demonstrating this. But it is hard to see a good rationale for the extra complexity this brings, since there are already many ways—backslash escaping, entity and numeric character references, or using a different quote type for the enclosing title—to write titles containing double quotes. `Markdown.pl`’s handling of titles has a number of other strange features. For example, it allows single-quoted titles in inline links, but not reference links. And, in reference links but not inline links, it allows a title to begin with `"` and end with `)`.`Markdown.pl` 1.0.1 even allows titles with no closing quotation mark, though 1.0.2b8 does not. It seems preferable to adopt a simple, rational rule that works the same way in inline links and link reference definitions.)  
[Whitespace](https://github.github.com/gfm/#whitespace) is allowed around the destination and title:  
<Example :index="$page.frontmatter.start++"/>

But it is not allowed between the link text and the following parenthesis:  
<Example :index="$page.frontmatter.start++"/>

The link text may contain balanced brackets, but not unbalanced ones, unless they are escaped:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The link text may contain inline content:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

However, links may not contain other links, at any level of nesting.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

These cases illustrate the precedence of link text grouping over emphasis grouping:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that brackets that _aren’t_ part of links do not take precedence:  
<Example :index="$page.frontmatter.start++"/>

These cases illustrate the precedence of HTML tags, code spans, and autolinks over link grouping:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

There are three kinds of [reference link](https://github.github.com/gfm/#reference-link)s: [full](https://github.github.com/gfm/#full-reference-link), [collapsed](https://github.github.com/gfm/#collapsed-reference-link), and [shortcut](https://github.github.com/gfm/#shortcut-reference-link).  
A [full reference link](https://github.github.com/gfm/#full-reference-link) consists of a [link text](https://github.github.com/gfm/#link-text) immediately followed by a [link label](https://github.github.com/gfm/#link-label) that [matches](https://github.github.com/gfm/#matches) a [link reference definition](https://github.github.com/gfm/#link-reference-definition) elsewhere in the document.  
A [link label](https://github.github.com/gfm/#link-label) begins with a left bracket (`[`) and ends with the first right bracket (`]`) that is not backslash-escaped. Between these brackets there must be at least one [non-whitespace character](https://github.github.com/gfm/#non-whitespace-character). Unescaped square bracket characters are not allowed inside the opening and closing square brackets of [link labels](https://github.github.com/gfm/#link-label). A link label can have at most 999 characters inside the square brackets.  
One label [matches](https://github.github.com/gfm/#matches) another just in case their normalized forms are equal. To normalize a label, strip off the opening and closing brackets, perform the _Unicode case fold_, strip leading and trailing [whitespace](https://github.github.com/gfm/#whitespace) and collapse consecutive internal [whitespace](https://github.github.com/gfm/#whitespace) to a single space. If there are multiple matching reference link definitions, the one that comes first in the document is used. (It is desirable in such cases to emit a warning.)  
The contents of the first link label are parsed as inlines, which are used as the link’s text. The link’s URI and title are provided by the matching [link reference definition](https://github.github.com/gfm/#link-reference-definition).  
Here is a simple example:  
<Example :index="$page.frontmatter.start++"/>

The rules for the [link text](https://github.github.com/gfm/#link-text) are the same as with [inline links](https://github.github.com/gfm/#inline-link). Thus:  
The link text may contain balanced brackets, but not unbalanced ones, unless they are escaped:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The link text may contain inline content:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

However, links may not contain other links, at any level of nesting.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

(In the examples above, we have two [shortcut reference links](https://github.github.com/gfm/#shortcut-reference-link) instead of one [full reference link](https://github.github.com/gfm/#full-reference-link).)  
The following cases illustrate the precedence of link text grouping over emphasis grouping:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

These cases illustrate the precedence of HTML tags, code spans, and autolinks over link grouping:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Matching is case-insensitive:  
<Example :index="$page.frontmatter.start++"/>

Unicode case fold is used:  
<Example :index="$page.frontmatter.start++"/>

Consecutive internal [whitespace](https://github.github.com/gfm/#whitespace) is treated as one space for purposes of determining matching:  
<Example :index="$page.frontmatter.start++"/>

No [whitespace](https://github.github.com/gfm/#whitespace) is allowed between the [link text](https://github.github.com/gfm/#link-text) and the [link label](https://github.github.com/gfm/#link-label):  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

This is a departure from John Gruber’s original Markdown syntax description, which explicitly allows whitespace between the link text and the link label. It brings reference links in line with [inline links](https://github.github.com/gfm/#inline-link), which (according to both original Markdown and this spec) cannot have whitespace after the link text. More importantly, it prevents inadvertent capture of consecutive [shortcut reference links](https://github.github.com/gfm/#shortcut-reference-link). If whitespace is allowed between the link text and the link label, then in the following we will have a single reference link, not two shortcut reference links, as intended:  

    [foo]
    [bar]
    
    [foo]: /url1
    [bar]: /url2

(Note that [shortcut reference links](https://github.github.com/gfm/#shortcut-reference-link) were introduced by Gruber himself in a beta version of `Markdown.pl`, but never included in the official syntax description. Without shortcut reference links, it is harmless to allow space between the link text and link label; but once shortcut references are introduced, it is too dangerous to allow this, as it frequently leads to unintended results.)  
When there are multiple matching [link reference definitions](https://github.github.com/gfm/#link-reference-definition), the first is used:  
<Example :index="$page.frontmatter.start++"/>

Note that matching is performed on normalized strings, not parsed inline content. So the following does not match, even though the labels define equivalent inline content:  
<Example :index="$page.frontmatter.start++"/>

[Link labels](https://github.github.com/gfm/#link-label) cannot contain brackets, unless they are backslash-escaped:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that in this example `]` is not backslash-escaped:  
<Example :index="$page.frontmatter.start++"/>

A [link label](https://github.github.com/gfm/#link-label) must contain at least one [non-whitespace character](https://github.github.com/gfm/#non-whitespace-character):  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

A [collapsed reference link](https://github.github.com/gfm/#collapsed-reference-link) consists of a [link label](https://github.github.com/gfm/#link-label) that [matches](https://github.github.com/gfm/#matches) a [link reference definition](https://github.github.com/gfm/#link-reference-definition) elsewhere in the document, followed by the string `[]`. The contents of the first link label are parsed as inlines, which are used as the link’s text. The link’s URI and title are provided by the matching reference link definition. Thus, `[foo][]` is equivalent to `[foo][foo]`.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The link labels are case-insensitive:  
<Example :index="$page.frontmatter.start++"/>

As with full reference links, [whitespace](https://github.github.com/gfm/#whitespace) is not allowed between the two sets of brackets:  
<Example :index="$page.frontmatter.start++"/>

A [shortcut reference link](https://github.github.com/gfm/#shortcut-reference-link) consists of a [link label](https://github.github.com/gfm/#link-label) that [matches](https://github.github.com/gfm/#matches) a [link reference definition](https://github.github.com/gfm/#link-reference-definition) elsewhere in the document and is not followed by `[]` or a link label. The contents of the first link label are parsed as inlines, which are used as the link’s text. The link’s URI and title are provided by the matching link reference definition. Thus, `[foo]` is equivalent to `[foo][]`.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The link labels are case-insensitive:  
<Example :index="$page.frontmatter.start++"/>

A space after the link text should be preserved:  
<Example :index="$page.frontmatter.start++"/>

If you just want bracketed text, you can backslash-escape the opening bracket to avoid links:  
<Example :index="$page.frontmatter.start++"/>

Note that this is a link, because a link label ends with the first following closing bracket:  
<Example :index="$page.frontmatter.start++"/>

Full and compact references take precedence over shortcut references:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Inline links also take precedence:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

In the following case `[bar][baz]` is parsed as a reference, `[foo]` as normal text:  
<Example :index="$page.frontmatter.start++"/>

Here, though, `[foo][bar]` is parsed as a reference, since `[bar]` is defined:  
<Example :index="$page.frontmatter.start++"/>

Here `[foo]` is not parsed as a shortcut reference, because it is followed by a link label (even though `[bar]`is not defined):  
<Example :index="$page.frontmatter.start++"/>
