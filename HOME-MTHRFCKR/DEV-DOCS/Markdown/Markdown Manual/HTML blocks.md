{{($page.frontmatter.start = 118) ? null : null}}
### HTML blocks

An [HTML block](https://github.github.com/gfm/#html-block) is a group of lines that is treated as raw HTML (and will not be escaped in HTML output).  

There are seven kinds of [HTML block](https://github.github.com/gfm/#html-block), which can be defined by their start and end conditions. The block begins with a line that meets a [start condition](https://github.github.com/gfm/#start-condition) (after up to three spaces optional indentation). It ends with the first subsequent line that meets a matching [end condition](https://github.github.com/gfm/#end-condition), or the last line of the document or other [container block](https://github.github.com/gfm/#container-block)), if no line is encountered that meets the [end condition](https://github.github.com/gfm/#end-condition). If the first line meets both the [start condition](https://github.github.com/gfm/#start-condition) and the [end condition](https://github.github.com/gfm/#end-condition), the block will contain just that line.  

1.  **Start condition:** line begins with the string `<script`, `<pre`, or `<style` (case-insensitive), followed by whitespace, the string `>`, or the end of the line.  
    **End condition:** line contains an end tag `</script>`, `</pre>`, or `</style>` (case-insensitive; it need not match the start tag).  
    
2.  **Start condition:** line begins with the string `<!--`.  
    **End condition:** line contains the string `-->`.  
    
3.  **Start condition:** line begins with the string `<?`.  
    **End condition:** line contains the string `?>`.  
    
4.  **Start condition:** line begins with the string `<!` followed by an uppercase ASCII letter.  
    **End condition:** line contains the character `>`.  
    
5.  **Start condition:** line begins with the string `<![CDATA[`.  
    **End condition:** line contains the string `]]>`.  
    
6.  **Start condition:** line begins the string `<` or `</` followed by one of the strings (case-insensitive) `address`, `article`, `aside`, `base`, `basefont`, `blockquote`, `body`, `caption`, `center`, `col`, `colgroup`, `dd`, `details`, `dialog`, `dir`, `div`, `dl`, `dt`, `fieldset`, `figcaption`, `figure`, `footer`, `form`, `frame`, `frameset`, `h1`, `h2`, `h3`, `h4`, `h5`, `h6`, `head`, `header`, `hr`, `html`, `iframe`, `legend`, `li`, `link`, `main`, `menu`, `menuitem`, `nav`, `noframes`, `ol`, `optgroup`, `option`, `p`, `param`, `section`, `source`, `summary`, `table`, `tbody`, `td`, `tfoot`, `th`, `thead`, `title`, `tr`, `track`, `ul`, followed by [whitespace](https://github.github.com/gfm/#whitespace), the end of the line, the string `>`, or the string `/>`.  
    **End condition:** line is followed by a [blank line](https://github.github.com/gfm/#blank-line).
7.  **Start condition:** line begins with a complete [open tag](https://github.github.com/gfm/#open-tag) or [closing tag](https://github.github.com/gfm/#closing-tag) (with any [tag name](https://github.github.com/gfm/#tag-name) other than `script`, `style`, or `pre`) or a complete closing tag,followed only by [whitespace](https://github.github.com/gfm/#whitespace) or the end of the line.  
    **End condition:** line is followed by a [blank line](https://github.github.com/gfm/#blank-line).

HTML blocks continue until they are closed by their appropriate [end condition](https://github.github.com/gfm/#end-condition), or the last line of the document or other [container block](https://github.github.com/gfm/#container-block). This means any HTML **within an HTML block** that might otherwise be recognised as a start condition will be ignored by the parser and passed through as-is, without changing the parser’s state.  
For instance, `<pre>` within a HTML block started by `<table>` will not affect the parser state; as the HTML block was started in by start condition 6, it will end at any blank line. This can be surprising:  
<Example :index="$page.frontmatter.start++"/>

In this case, the HTML block is terminated by the newline — the `**Hello**` text remains verbatim — and regular parsing resumes, with a paragraph, emphasised `world` and inline and block HTML following.  
All types of [HTML blocks](https://github.github.com/gfm/#html-blocks) except type 7 may interrupt a paragraph. Blocks of type 7 may not interrupt a paragraph. (This restriction is intended to prevent unwanted interpretation of long tags inside a wrapped paragraph as starting HTML blocks.)  
Some simple examples follow. Here are some basic HTML blocks of type 6:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

A block can also start with a closing tag:  
<Example :index="$page.frontmatter.start++"/>

Here we have two HTML blocks with a Markdown paragraph between them:  
<Example :index="$page.frontmatter.start++"/>

The tag on the first line can be partial, as long as it is split where there would be whitespace:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

An open tag need not be closed:  
<Example :index="$page.frontmatter.start++"/>

A partial tag need not even be completed (garbage in, garbage out):  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The initial tag doesn’t even need to be a valid tag, as long as it starts like one:  
<Example :index="$page.frontmatter.start++"/>

In type 6 blocks, the initial tag need not be on a line by itself:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Everything until the next blank line or end of document gets included in the HTML block. So, in the following example, what looks like a Markdown code block is actually part of the HTML block, which continues until a blank line or the end of the document is reached:  
<Example :index="$page.frontmatter.start++"/>

To start an [HTML block](https://github.github.com/gfm/#html-block) with a tag that is _not_ in the list of block-level tags in (6), you must put the tag by itself on the first line (and it must be complete):  
<Example :index="$page.frontmatter.start++"/>

In type 7 blocks, the [tag name](https://github.github.com/gfm/#tag-name) can be anything:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

These rules are designed to allow us to work with tags that can function as either block-level or inline-level tags. The `<del>` tag is a nice example. We can surround content with `<del>` tags in three different ways. In this case, we get a raw HTML block, because the `<del>` tag is on a line by itself:  
<Example :index="$page.frontmatter.start++"/>

In this case, we get a raw HTML block that just includes the `<del>` tag (because it ends with the following blank line). So the contents get interpreted as CommonMark:  
<Example :index="$page.frontmatter.start++"/>

Finally, in this case, the `<del>` tags are interpreted as [raw HTML](https://github.github.com/gfm/#raw-html) _inside_ the CommonMark paragraph. (Because the tag is not on a line by itself, we get inline HTML rather than an [HTML block](https://github.github.com/gfm/#html-block).)  
<Example :index="$page.frontmatter.start++"/>

HTML tags designed to contain literal content (`script`, `style`, `pre`), comments, processing instructions, and declarations are treated somewhat differently. Instead of ending at the first blank line, these blocks end at the first line containing a corresponding end tag. As a result, these blocks can contain blank lines:  
A pre tag (type 1):  
<Example :index="$page.frontmatter.start++"/>

A script tag (type 1):  
<Example :index="$page.frontmatter.start++"/>

A style tag (type 1):  
<Example :index="$page.frontmatter.start++"/>

If there is no matching end tag, the block will end at the end of the document (or the enclosing [block quote](https://github.github.com/gfm/#block-quotes)or [list item](https://github.github.com/gfm/#list-items)):  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The end tag can occur on the same line as the start tag:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that anything on the last line after the end tag will be included in the [HTML block](https://github.github.com/gfm/#html-block):  
<Example :index="$page.frontmatter.start++"/>

A comment (type 2):  
<Example :index="$page.frontmatter.start++"/>

A processing instruction (type 3):  
<Example :index="$page.frontmatter.start++"/>

A declaration (type 4):  
<Example :index="$page.frontmatter.start++"/>

CDATA (type 5):  
<Example :index="$page.frontmatter.start++"/>

The opening tag can be indented 1-3 spaces, but not 4:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

An HTML block of types 1–6 can interrupt a paragraph, and need not be preceded by a blank line.  
<Example :index="$page.frontmatter.start++"/>

However, a following blank line is needed, except at the end of a document, and except for blocks of types 1–5, [above](https://github.github.com/gfm/#html-block) HTML block:  
<Example :index="$page.frontmatter.start++"/>


HTML blocks of type 7 cannot interrupt a paragraph:  
<Example :index="$page.frontmatter.start++"/>

This rule differs from John Gruber’s original Markdown syntax specification, which says:  

> The only restrictions are that block-level HTML elements — e.g. `<div>`, `<table>`, `<pre>`, `<p>`, etc. — must be separated from surrounding content by blank lines, and the start and end tags of the block should not be indented with tabs or spaces.

In some ways Gruber’s rule is more restrictive than the one given here:  

*   It requires that an HTML block be preceded by a blank line.
*   It does not allow the start tag to be indented.
*   It requires a matching end tag, which it also does not allow to be indented.

Most Markdown implementations (including some of Gruber’s own) do not respect all of these restrictions.  
There is one respect, however, in which Gruber’s rule is more liberal than the one given here, since it allows blank lines to occur inside an HTML block. There are two reasons for disallowing them here. First, it removes the need to parse balanced tags, which is expensive and can require backtracking from the end of the document if no matching end tag is found. Second, it provides a very simple and flexible way of including Markdown content inside HTML tags: simply separate the Markdown from the HTML using blank lines:  
Compare:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Some Markdown implementations have adopted a convention of interpreting content inside tags as text if the open tag has the attribute `markdown=1`. The rule given above seems a simpler and more elegant way of achieving the same expressive power, which is also much simpler to parse.  
The main potential drawback is that one can no longer paste HTML blocks into Markdown documents with 100% reliability. However, _in most cases_ this will work fine, because the blank lines in HTML are usually followed by HTML block tags. For example:  
<Example :index="$page.frontmatter.start++"/>

There are problems, however, if the inner tags are indented _and_ separated by spaces, as then they will be interpreted as an indented code block:  
<Example :index="$page.frontmatter.start++"/>

Fortunately, blank lines are usually not necessary and can be deleted. The exception is inside `<pre>` tags, but as described [above](https://github.github.com/gfm/#html-blocks) HTML blocks, raw HTML blocks starting with `<pre>` _can_ contain blank lines.  