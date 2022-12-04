{{($page.frontmatter.start = 189) ? null : null}}
### Paragraphs

A sequence of non-blank lines that cannot be interpreted as other kinds of blocks forms a [paragraph](https://github.github.com/gfm/#paragraph). The contents of the paragraph are the result of parsing the paragraph’s raw content as inlines. The paragraph’s raw content is formed by concatenating the lines and removing initial and final [whitespace](https://github.github.com/gfm/#whitespace).  
A simple example with two paragraphs:  
<Example :index="$page.frontmatter.start++"/>

Paragraphs can contain multiple lines, but no blank lines:  
<Example :index="$page.frontmatter.start++"/>

Multiple blank lines between paragraph have no effect:  
<Example :index="$page.frontmatter.start++"/>

Leading spaces are skipped:  
<Example :index="$page.frontmatter.start++"/>

Lines after the first may be indented any amount, since indented code blocks cannot interrupt paragraphs.  
<Example :index="$page.frontmatter.start++"/>

However, the first line may be indented at most three spaces, or an indented code block will be triggered:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Final spaces are stripped before inline parsing, so a paragraph that ends with two or more spaces will not end with a [hard line break](https://github.github.com/gfm/#hard-line-break):  
<Example :index="$page.frontmatter.start++"/>
