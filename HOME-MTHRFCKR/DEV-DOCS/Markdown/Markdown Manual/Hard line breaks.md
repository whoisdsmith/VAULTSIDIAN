{{($page.frontmatter.start = 654) ? null : null}}
## Hard line breaks

A line break (not in a code span or HTML tag) that is preceded by two or more spaces and does not occur at the end of a block is parsed as a [hard line break](https://github.github.com/gfm/#hard-line-break) (rendered in HTML as a `<br />` tag):  
<Example :index="$page.frontmatter.start++"/>

For a more visible alternative, a backslash before the [line ending](https://github.github.com/gfm/#line-ending) may be used instead of two spaces:  
<Example :index="$page.frontmatter.start++"/>

More than two spaces can be used:  
<Example :index="$page.frontmatter.start++"/>

Leading spaces at the beginning of the next line are ignored:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Line breaks can occur inside emphasis, links, and other constructs that allow inline content:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Line breaks do not occur inside code spans  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

or HTML tags:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Hard line breaks are for separating inline content within a block. Neither syntax for hard line breaks works at the end of a paragraph or other block element:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>
