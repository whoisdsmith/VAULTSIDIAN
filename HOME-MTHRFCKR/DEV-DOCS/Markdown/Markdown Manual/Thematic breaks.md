{{($page.frontmatter.start = 13) ? null : null}}
### Thematic breaks

A line consisting of 0-3 spaces of indentation, followed by a sequence of three or more matching `-`, `_`, or `*`characters, each followed optionally by any number of spaces or tabs, forms a [thematic break](https://github.github.com/gfm/#thematic-break).  

<Example :index="$page.frontmatter.start++"/>

Wrong characters:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Not enough characters:  
<Example :index="$page.frontmatter.start++"/>

One to three spaces indent are allowed:  
<Example :index="$page.frontmatter.start++"/>

Four spaces is too many:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

More than three characters may be used:  
<Example :index="$page.frontmatter.start++"/>

Spaces are allowed between the characters:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Spaces are allowed at the end:  
<Example :index="$page.frontmatter.start++"/>

However, no other characters may occur in the line:  
<Example :index="$page.frontmatter.start++"/>

It is required that all of the [non-whitespace characters](https://github.github.com/gfm/#non-whitespace-character) be the same. So, this is not a thematic break:  
<Example :index="$page.frontmatter.start++"/>

Thematic breaks do not need blank lines before or after:  
<Example :index="$page.frontmatter.start++"/>

Thematic breaks can interrupt a paragraph:  
<Example :index="$page.frontmatter.start++"/>

If a line of dashes that meets the above conditions for being a thematic break could also be interpreted as the underline of a [setext heading](https://github.github.com/gfm/#setext-heading), the interpretation as a [setext heading](https://github.github.com/gfm/#setext-heading) takes precedence. Thus, for example, this is a setext heading, not a paragraph followed by a thematic break:      

<Example :index="$page.frontmatter.start++"/>

When both a thematic break and a list item are possible interpretations of a line, the thematic break takes precedence:  
<Example :index="$page.frontmatter.start++"/>

If you want a thematic break in a list item, use a different bullet:  
<Example :index="$page.frontmatter.start++"/>
