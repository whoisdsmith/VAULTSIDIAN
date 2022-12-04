{{($page.frontmatter.start = 281) ? null : null}}
### Lists

A [list](https://github.github.com/gfm/#list) is a sequence of one or more list items [of the same type](https://github.github.com/gfm/#of-the-same-type). The list items may be separated by any number of blank lines.  
Two list items are [of the same type](https://github.github.com/gfm/#of-the-same-type) if they begin with a [list marker](https://github.github.com/gfm/#list-marker) of the same type. Two list markers are of the same type if (a) they are bullet list markers using the same character (`-`, `+`, or `*`) or (b) they are ordered list numbers with the same delimiter (either `.` or `)`).  
A list is an [ordered list](https://github.github.com/gfm/#ordered-list) if its constituent list items begin with [ordered list markers](https://github.github.com/gfm/#ordered-list-marker), and a [bullet list](https://github.github.com/gfm/#bullet-list) if its constituent list items begin with [bullet list markers](https://github.github.com/gfm/#bullet-list-marker).  
The [start number](https://github.github.com/gfm/#start-number) of an [ordered list](https://github.github.com/gfm/#ordered-list) is determined by the list number of its initial list item. The numbers of subsequent list items are disregarded.  
A list is [loose](https://github.github.com/gfm/#loose) if any of its constituent list items are separated by blank lines, or if any of its constituent list items directly contain two block-level elements with a blank line between them. Otherwise a list is [tight](https://github.github.com/gfm/#tight). (The difference in HTML output is that paragraphs in a loose list are wrapped in `<p>` tags, while paragraphs in a tight list are not.)  
Changing the bullet or ordered list delimiter starts a new list:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

In CommonMark, a list can interrupt a paragraph. That is, no blank line is needed to separate a paragraph from a following list:  
<Example :index="$page.frontmatter.start++"/>

`Markdown.pl` does not allow this, through fear of triggering a list via a numeral in a hard-wrapped line:  

    The number of windows in my house is
    14.  The number of doors is 6.

Oddly, though, `Markdown.pl` _does_ allow a blockquote to interrupt a paragraph, even though the same considerations might apply.  
In CommonMark, we do allow lists to interrupt paragraphs, for two reasons. First, it is natural and not uncommon for people to start lists without blank lines:  

    I need to buy
    - new shoes
    - a coat
    - a plane ticket

Second, we are attracted to a  

> [principle of uniformity](https://github.github.com/gfm/#principle-of-uniformity): if a chunk of text has a certain meaning, it will continue to have the same meaning when put into a container block (such as a list item or blockquote).

(Indeed, the spec for [list items](https://github.github.com/gfm/#list-items) and [block quotes](https://github.github.com/gfm/#block-quotes) presupposes this principle.) This principle implies that if  

      * I need to buy
        - new shoes
        - a coat
        - a plane ticket

is a list item containing a paragraph followed by a nested sublist, as all Markdown implementations agree it is (though the paragraph may be rendered without `<p>` tags, since the list is “tight”), then  

    I need to buy
    - new shoes
    - a coat
    - a plane ticket

by itself should be a paragraph followed by a nested sublist.  
Since it is well established Markdown practice to allow lists to interrupt paragraphs inside list items, the [principle of uniformity](https://github.github.com/gfm/#principle-of-uniformity) requires us to allow this outside list items as well. ([reStructuredText](http://docutils.sourceforge.net/rst.html) takes a different approach, requiring blank lines before lists even inside other list items.)  
In order to solve of unwanted lists in paragraphs with hard-wrapped numerals, we allow only lists starting with `1` to interrupt paragraphs. Thus,  
<Example :index="$page.frontmatter.start++"/>

We may still get an unintended result in cases like  
<Example :index="$page.frontmatter.start++"/>

but this rule should prevent most spurious list captures.  
There can be any number of blank lines between items:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

To separate consecutive lists of the same type, or to separate a list from an indented code block that would otherwise be parsed as a subparagraph of the final list item, you can insert a blank HTML comment:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

List items need not be indented to the same level. The following list items will be treated as items at the same list level, since none is indented enough to belong to the previous list item:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note, however, that list items may not be indented more than three spaces. Here `- e` is treated as a paragraph continuation line, because it is indented more than three spaces:  
<Example :index="$page.frontmatter.start++"/>

And here, `3. c` is treated as in indented code block, because it is indented four spaces and preceded by a blank line.  
<Example :index="$page.frontmatter.start++"/>

This is a loose list, because there is a blank line between two of the list items:  
<Example :index="$page.frontmatter.start++"/>

So is this, with a empty second item:  
<Example :index="$page.frontmatter.start++"/>

These are loose lists, even though there is no space between the items, because one of the items directly contains two block-level elements with a blank line between them:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

This is a tight list, because the blank lines are in a code block:  
<Example :index="$page.frontmatter.start++"/>

This is a tight list, because the blank line is between two paragraphs of a sublist. So the sublist is loose while the outer list is tight:  
<Example :index="$page.frontmatter.start++"/>

This is a tight list, because the blank line is inside the block quote:  
<Example :index="$page.frontmatter.start++"/>

This list is tight, because the consecutive block elements are not separated by blank lines:  
<Example :index="$page.frontmatter.start++"/>

A single-paragraph list is tight:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

This list is loose, because of the blank line between the two block elements in the list item:  
<Example :index="$page.frontmatter.start++"/>

Here the outer list is loose, the inner list tight:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>
