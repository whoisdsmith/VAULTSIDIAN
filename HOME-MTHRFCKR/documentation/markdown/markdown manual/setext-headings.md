# Setext-headings

## Setext Headings

{{($page.frontmatter.start = 50) ? null : null}}

A [setext heading](https://github.github.com/gfm/#setext-heading) consists of one or more lines of text, each containing at least one [non-whitespace character](https://github.github.com/gfm/#non-whitespace-character), with no more than 3 spaces indentation, followed by a [setext heading underline](https://github.github.com/gfm/#setext-heading-underline). The lines of text must be such that, were they not followed by the setext heading underline, they would be interpreted as a paragraph: they cannot be interpretable as a [code fence](https://github.github.com/gfm/#code-fence), [ATX heading](https://github.github.com/gfm/#atx-headings), [block quote](https://github.github.com/gfm/#block-quotes), [thematic break](https://github.github.com/gfm/#thematic-breaks), [list item](https://github.github.com/gfm/#list-items), or [HTML block](https://github.github.com/gfm/#html-blocks).  

A [setext heading underline](https://github.github.com/gfm/#setext-heading-underline) is a sequence of `=` characters or a sequence of `-` characters, with no more than 3 spaces indentation and any number of trailing spaces. If a line containing a single `-` can be interpreted as an empty [list items](https://github.github.com/gfm/#list-items), it should be interpreted this way and not as a [setext heading underline](https://github.github.com/gfm/#setext-heading-underline).  

The heading is a level 1 heading if `=` characters are used in the [setext heading underline](https://github.github.com/gfm/#setext-heading-underline), and a level 2 heading if `-` characters are used. The contents of the heading are the result of parsing the preceding lines of text as CommonMark inline content.  

In general, a setext heading need not be preceded or followed by a blank line. However, it cannot interrupt a paragraph, so when a setext heading comes after a paragraph, a blank line is needed between them.  

Simple examples:  
<Example :index="$page.frontmatter.start++"/>

The content of the header may span more than one line:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The underlining can be any length:  
<Example :index="$page.frontmatter.start++"/>

The heading content can be indented up to three spaces, and need not line up with the underlining:  
<Example :index="$page.frontmatter.start++"/>

Four spaces indent is too much:  
<Example :index="$page.frontmatter.start++"/>

The setext heading underline can be indented up to three spaces, and may have trailing spaces:  
<Example :index="$page.frontmatter.start++"/>

Four spaces is too much:  
<Example :index="$page.frontmatter.start++"/>

The setext heading underline cannot contain internal spaces:  
<Example :index="$page.frontmatter.start++"/>

Trailing spaces in the content line do not cause a line break:  
<Example :index="$page.frontmatter.start++"/>

Nor does a backslash at the end:  
<Example :index="$page.frontmatter.start++"/>

Since indicators of block structure take precedence over indicators of inline structure, the following are setext headings:  
<Example :index="$page.frontmatter.start++"/>

The setext heading underline cannot be a [lazy continuation line](https://github.github.com/gfm/#lazy-continuation-line) in a list item or block quote:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

A blank line is needed between a paragraph and a following setext heading, since otherwise the paragraph becomes part of the heading’s content:  
<Example :index="$page.frontmatter.start++"/>

But in general a blank line is not required before or after setext headings:  
<Example :index="$page.frontmatter.start++"/>

Setext headings cannot be empty:  
<Example :index="$page.frontmatter.start++"/>

Setext heading text lines must not be interpretable as block constructs other than paragraphs. So, the line of dashes in these examples gets interpreted as a thematic break:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

If you want a heading with `> foo` as its literal text, you can use backslash escapes:  
<Example :index="$page.frontmatter.start++"/>

**Compatibility note:** Most existing Markdown implementations do not allow the text of setext headings to span multiple lines. But there is no consensus about how to interpret  

    Foo
    bar
    ---
    baz

One can find four different interpretations:  

1. paragraph “Foo”, heading “bar”, paragraph “baz”
2. paragraph “Foo bar”, thematic break, paragraph “baz”
3. paragraph “Foo bar — baz”
4. heading “Foo bar”, paragraph “baz”

We find interpretation 4 most natural, and interpretation 4 increases the expressive power of CommonMark, by allowing multiline headings. Authors who want interpretation 1 can put a blank line after the first paragraph:  
<Example :index="$page.frontmatter.start++"/>

Authors who want interpretation 2 can put blank lines around the thematic break,  
<Example :index="$page.frontmatter.start++"/>

or use a thematic break that cannot count as a [setext heading underline](https://github.github.com/gfm/#setext-heading-underline), such as  
<Example :index="$page.frontmatter.start++"/>

Authors who want interpretation 3 can use backslash escapes:  
<Example :index="$page.frontmatter.start++"/>
