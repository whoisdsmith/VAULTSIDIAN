{{($page.frontmatter.start = 89) ? null : null}}
### Fenced code blocks

A [code fence](https://github.github.com/gfm/#code-fence) is a sequence of at least three consecutive backtick characters (`` ` ``) or tildes (`~`). (Tildes and backticks cannot be mixed.) A [fenced code block](https://github.github.com/gfm/#fenced-code-block) begins with a code fence, indented no more than three spaces.  

The line with the opening code fence may optionally contain some text following the code fence; this is trimmed of leading and trailing whitespace and called the [info string](https://github.github.com/gfm/#info-string). The [info string](https://github.github.com/gfm/#info-string) may not contain any backtick characters. (The reason for this restriction is that otherwise some inline code would be incorrectly interpreted as the beginning of a fenced code block.) 
 
The content of the code block consists of all subsequent lines, until a closing [code fence](https://github.github.com/gfm/#code-fence) of the same type as the code block began with (backticks or tildes), and with at least as many backticks or tildes as the opening code fence. If the leading code fence is indented N spaces, then up to N spaces of indentation are removed from each line of the content (if present). (If a content line is not indented, it is preserved unchanged. If it is indented less than N spaces, all of the indentation is removed.)  

The closing code fence may be indented up to three spaces, and may be followed only by spaces, which are ignored. If the end of the containing block (or document) is reached and no closing code fence has been found, the code block contains all of the lines after the opening code fence until the end of the containing block (or document). (An alternative spec would require backtracking in the event that a closing code fence is not found. But this makes parsing much less efficient, and there seems to be no real down side to the behavior described here.)  

A fenced code block may interrupt a paragraph, and does not require a blank line either before or after.  

The content of a code fence is treated as literal text, not parsed as inlines. The first word of the [info string](https://github.github.com/gfm/#info-string) is typically used to specify the language of the code sample, and rendered in the `class` attribute of the `code`tag. However, this spec does not mandate any particular treatment of the [info string](https://github.github.com/gfm/#info-string).  

Here is a simple example with backticks:  
<Example :index="$page.frontmatter.start++"/>

With tildes:  
<Example :index="$page.frontmatter.start++"/>

Fewer than three backticks is not enough:  
<Example :index="$page.frontmatter.start++"/>

The closing code fence must use the same character as the opening fence:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The closing code fence must be at least as long as the opening fence:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Unclosed code blocks are closed by the end of the document (or the enclosing [block quote](https://github.github.com/gfm/#block-quotes) or [list item](https://github.github.com/gfm/#list-items)):  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

A code block can have all empty lines as its content:  
<Example :index="$page.frontmatter.start++"/>

A code block can be empty:  
<Example :index="$page.frontmatter.start++"/>

Fences can be indented. If the opening fence is indented, content lines will have equivalent opening indentation removed, if present:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Four spaces indentation produces an indented code block:  
<Example :index="$page.frontmatter.start++"/>

Closing fences may be indented by 0-3 spaces, and their indentation need not match that of the opening fence:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

This is not a closing fence, because it is indented 4 spaces:  
<Example :index="$page.frontmatter.start++"/>

Code fences (opening and closing) cannot contain internal spaces:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Fenced code blocks can interrupt paragraphs, and can be followed directly by paragraphs, without a blank line between:  
<Example :index="$page.frontmatter.start++"/>

Other blocks can also occur before and after fenced code blocks without an intervening blank line:  
<Example :index="$page.frontmatter.start++"/>

An [info string](https://github.github.com/gfm/#info-string) can be provided after the opening code fence.
Although this spec doesn't mandate any particular treatment of the info string, the first word is typically used to specify the language of the code block. In HTML output, the language is normally indicated by adding a class to the `code` element consisting of `language-` followed by the language name.    
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

[Info strings](https://github.github.com/gfm/#info-string) for backtick code blocks cannot contain backticks:      
<Example :index="$page.frontmatter.start++"/>

[Info strings](https://github.github.com/gfm/#info-string) for tilde code blocks can contain backticks and tildes:     

<Example :index="$page.frontmatter.start++"/>

Closing code fences cannot have [info strings](https://github.github.com/gfm/#info-string):  
<Example :index="$page.frontmatter.start++"/>
