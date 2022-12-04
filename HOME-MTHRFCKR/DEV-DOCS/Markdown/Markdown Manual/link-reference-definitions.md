{{($page.frontmatter.start = 161) ? null : null}}
### Link reference definitions

A [link reference definition](https://github.github.com/gfm/#link-reference-definition) consists of a [link label](https://github.github.com/gfm/#link-label), indented up to three spaces, followed by a colon (`:`), optional [whitespace](https://github.github.com/gfm/#whitespace) (including up to one [line ending](https://github.github.com/gfm/#line-ending)), a [link destination](https://github.github.com/gfm/#link-destination), optional [whitespace](https://github.github.com/gfm/#whitespace) (including up to one [line ending](https://github.github.com/gfm/#line-ending)), and an optional [link title](https://github.github.com/gfm/#link-title), which if it is present must be separated from the [link destination](https://github.github.com/gfm/#link-destination)by [whitespace](https://github.github.com/gfm/#whitespace). No further [non-whitespace characters](https://github.github.com/gfm/#non-whitespace-character) may occur on the line.  

A [link reference definition](https://github.github.com/gfm/#link-reference-definition) does not correspond to a structural element of a document. Instead, it defines a label which can be used in [reference links](https://github.github.com/gfm/#reference-link) and reference-style [images](https://github.github.com/gfm/#images) elsewhere in the document. [Link reference definitions](https://github.github.com/gfm/#link-reference-definition) can come either before or after the links that use them.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The title may extend over multiple lines:  
<Example :index="$page.frontmatter.start++"/>

However, it may not contain a [blank line](https://github.github.com/gfm/#blank-line):  
<Example :index="$page.frontmatter.start++"/>

The title may be omitted:  
<Example :index="$page.frontmatter.start++"/>

The link destination may not be omitted:  
<Example :index="$page.frontmatter.start++"/>

However, an empty link destination may be specified using angle brackets:    

<Example :index="$page.frontmatter.start++"/>

The title must be separated from the link destination by whitespace:

<Example :index="$page.frontmatter.start++"/>

Both title and destination can contain backslash escapes and literal backslashes:  
<Example :index="$page.frontmatter.start++"/>

A link can come before its corresponding definition:  
<Example :index="$page.frontmatter.start++"/>

If there are several matching definitions, the first one takes precedence:  
<Example :index="$page.frontmatter.start++"/>

As noted in the section on [Links](https://github.github.com/gfm/#links), matching of labels is case-insensitive (see [matches](https://github.github.com/gfm/#matches)).  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Here is a link reference definition with no corresponding link. It contributes nothing to the document.  
<Example :index="$page.frontmatter.start++"/>

Here is another one:  
<Example :index="$page.frontmatter.start++"/>

This is not a link reference definition, because there are [non-whitespace characters](https://github.github.com/gfm/#non-whitespace-character) after the title:  
<Example :index="$page.frontmatter.start++"/>

This is a link reference definition, but it has no title:  
<Example :index="$page.frontmatter.start++"/>

This is not a link reference definition, because it is indented four spaces:  
<Example :index="$page.frontmatter.start++"/>

This is not a link reference definition, because it occurs inside a code block:  
<Example :index="$page.frontmatter.start++"/>

A [link reference definition](https://github.github.com/gfm/#link-reference-definition) cannot interrupt a paragraph.  
<Example :index="$page.frontmatter.start++"/>

However, it can directly follow other block elements, such as headings and thematic breaks, and it need not be followed by a blank line.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Several [link reference definitions](https://github.github.com/gfm/#link-reference-definition) can occur one after another, without intervening blank lines.  
<Example :index="$page.frontmatter.start++"/>

[Link reference definitions](https://github.github.com/gfm/#link-reference-definition) can occur inside block containers, like lists and block quotations. They affect the entire document, not just the container in which they are defined:  
<Example :index="$page.frontmatter.start++"/>

Whether something is a [link reference definition] is independent of whether the link reference it defines is used in the document.  Thus, for example, the following document contains just a link reference definition, and no visible content:

<Example :index="$page.frontmatter.start++"/>
