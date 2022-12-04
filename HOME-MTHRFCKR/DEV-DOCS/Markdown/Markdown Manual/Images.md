{{($page.frontmatter.start = 580) ? null : null}}
### Images

Syntax for images is like the syntax for links, with one difference. Instead of [link text](https://github.github.com/gfm/#link-text), we have an [image description](https://github.github.com/gfm/#image-description). The rules for this are the same as for [link text](https://github.github.com/gfm/#link-text), except that (a) an image description starts with `![` rather than `[`, and (b) an image description may contain links. An image description has inline elements as its contents. When an image is rendered to HTML, this is standardly used as the image’s `alt` attribute.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Though this spec is concerned with parsing, not rendering, it is recommended that in rendering to HTML, only the plain string content of the [image description](https://github.github.com/gfm/#image-description) be used. Note that in the above example, the alt attribute’s value is `foo bar`, not `foo [bar](/url)` or `foo <a href="/url">bar</a>`. Only the plain string content is rendered, without formatting.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Reference-style:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Collapsed:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The labels are case-insensitive:  
<Example :index="$page.frontmatter.start++"/>

As with reference links, [whitespace](https://github.github.com/gfm/#whitespace) is not allowed between the two sets of brackets:  
<Example :index="$page.frontmatter.start++"/>

Shortcut:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that link labels cannot contain unescaped brackets:  
<Example :index="$page.frontmatter.start++"/>

The link labels are case-insensitive:  
<Example :index="$page.frontmatter.start++"/>

If you just want a literal `!` followed by bracketed text, you can backslash-escape the opening `[`:  
<Example :index="$page.frontmatter.start++"/>

If you want a link after a literal `!`, backslash-escape the `!`:  
<Example :index="$page.frontmatter.start++"/>
    