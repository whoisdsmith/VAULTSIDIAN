{{($page.frontmatter.start = 308) ? null : null}}
### Backslash escapes

Any ASCII punctuation character may be backslash-escaped:  
<Example :index="$page.frontmatter.start++"/>

Backslashes before other characters are treated as literal backslashes:  
<Example :index="$page.frontmatter.start++"/>

Escaped characters are treated as regular characters and do not have their usual Markdown meanings:  
<Example :index="$page.frontmatter.start++"/>

If a backslash is itself escaped, the following character is not:  
<Example :index="$page.frontmatter.start++"/>

A backslash at the end of the line is a [hard line break](https://github.github.com/gfm/#hard-line-break):  
<Example :index="$page.frontmatter.start++"/>

Backslash escapes do not work in code blocks, code spans, autolinks, or raw HTML:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

But they work in all other contexts, including URLs and link titles, link references, and [info strings](https://github.github.com/gfm/#info-string) in [fenced code blocks](https://github.github.com/gfm/#fenced-code-blocks):  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>
