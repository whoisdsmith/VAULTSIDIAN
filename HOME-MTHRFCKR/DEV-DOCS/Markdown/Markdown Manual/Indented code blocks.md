{{($page.frontmatter.start = 77) ? null : null}}
### Indented code blocks

An [indented code block](https://github.github.com/gfm/#indented-code-block) is composed of one or more [indented chunks](https://github.github.com/gfm/#indented-chunk) separated by blank lines. An [indented chunk](https://github.github.com/gfm/#indented-chunk) is a sequence of non-blank lines, each indented four or more spaces. The contents of the code block are the literal contents of the lines, including trailing [line endings](https://github.github.com/gfm/#line-ending), minus four spaces of indentation. An indented code block has no [info string](https://github.github.com/gfm/#info-string).  
An indented code block cannot interrupt a paragraph, so there must be a blank line between a paragraph and a following indented code block. (A blank line is not needed, however, between a code block and a following paragraph.)  
<Example :index="$page.frontmatter.start++"/>

If there is any ambiguity between an interpretation of indentation as a code block and as indicating that material belongs to a [list item](https://github.github.com/gfm/#list-items), the list item interpretation takes precedence:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The contents of a code block are literal text, and do not get parsed as Markdown:  
<Example :index="$page.frontmatter.start++"/>

Here we have three chunks separated by blank lines:  
<Example :index="$page.frontmatter.start++"/>

Any initial spaces beyond four will be included in the content, even in interior blank lines:  
<Example :index="$page.frontmatter.start++"/>

An indented code block cannot interrupt a paragraph. (This allows hanging indents and the like.)  
<Example :index="$page.frontmatter.start++"/>

However, any non-blank line with fewer than four leading spaces ends the code block immediately. So a paragraph may occur immediately after indented code:  
<Example :index="$page.frontmatter.start++"/>

And indented code can occur immediately before and after other kinds of blocks:  
<Example :index="$page.frontmatter.start++"/>

The first line can be indented more than four spaces:  
<Example :index="$page.frontmatter.start++"/>

Blank lines preceding or following an indented code block are not included in it:  
<Example :index="$page.frontmatter.start++"/>

Trailing spaces are included in the code block’s content:  
<Example :index="$page.frontmatter.start++"/>
