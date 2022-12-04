{{($page.frontmatter.start = 206) ? null : null}}
### Block quotes

A [block quote marker](https://github.github.com/gfm/#block-quote-marker) consists of 0-3 spaces of initial indent, plus (a) the character `>` together with a following space, or (b) a single character `>` not followed by a space.  

The following rules define [block quotes](https://github.github.com/gfm/#block-quotes):     
1.  **Basic case.** If a string of lines _Ls_ constitute a sequence of blocks _Bs_, then the result of prepending a [block quote marker](https://github.github.com/gfm/#block-quote-marker) to the beginning of each line in _Ls_ is a [block quote](https://github.github.com/gfm/#block-quotes) containing _Bs_.
2.  **Laziness.** If a string of lines _Ls_ constitute a [block quote](https://github.github.com/gfm/#block-quotes) with contents _Bs_, then the result of deleting the initial [block quote marker](https://github.github.com/gfm/#block-quote-marker) from one or more lines in which the next [non-whitespace character](https://github.github.com/gfm/#non-whitespace-character) after the [block quote marker](https://github.github.com/gfm/#block-quote-marker) is [paragraph continuation text](https://github.github.com/gfm/#paragraph-continuation-text) is a block quote with _Bs_ as its content. [Paragraph continuation text](https://github.github.com/gfm/#paragraph-continuation-text) is text that will be parsed as part of the content of a paragraph, but does not occur at the beginning of the paragraph.
3.  **Consecutiveness.** A document cannot contain two [block quotes](https://github.github.com/gfm/#block-quotes) in a row unless there is a [blank line](https://github.github.com/gfm/#blank-line)between them.

Nothing else counts as a [block quote](https://github.github.com/gfm/#block-quotes).  
Here is a simple example:  
<Example :index="$page.frontmatter.start++"/>

The spaces after the `>` characters can be omitted:  
<Example :index="$page.frontmatter.start++"/>

The `>` characters can be indented 1-3 spaces:  
<Example :index="$page.frontmatter.start++"/>

Four spaces gives us a code block:  
<Example :index="$page.frontmatter.start++"/>

The Laziness clause allows us to omit the `>` before [paragraph continuation text](https://github.github.com/gfm/#paragraph-continuation-text):  
<Example :index="$page.frontmatter.start++"/>

A block quote can contain some lazy and some non-lazy continuation lines:  
<Example :index="$page.frontmatter.start++"/>

Laziness only applies to lines that would have been continuations of paragraphs had they been prepended with [block quote markers](https://github.github.com/gfm/#block-quote-marker). For example, the `>` cannot be omitted in the second line of  

    > foo
    > ---

without changing the meaning:  
<Example :index="$page.frontmatter.start++"/>

Similarly, if we omit the `>` in the second line of  

    > - foo
    > - bar

then the block quote ends after the first line:  
<Example :index="$page.frontmatter.start++"/>

For the same reason, we can’t omit the `>` in front of subsequent lines of an indented or fenced code block:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that in the following case, we have a [lazy continuation line](https://github.github.com/gfm/#lazy-continuation-line):  
<Example :index="$page.frontmatter.start++"/>

To see why, note that in  

    > foo
    >     - bar

the `- bar` is indented too far to start a list, and can’t be an indented code block because indented code blocks cannot interrupt paragraphs, so it is [paragraph continuation text](https://github.github.com/gfm/#paragraph-continuation-text).  
A block quote can be empty:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

A block quote can have initial or final blank lines:  
<Example :index="$page.frontmatter.start++"/>

A blank line always separates block quotes:  
<Example :index="$page.frontmatter.start++"/>

(Most current Markdown implementations, including John Gruber’s original `Markdown.pl`, will parse this example as a single block quote with two paragraphs. But it seems better to allow the author to decide whether two block quotes or one are wanted.)  
Consecutiveness means that if we put these block quotes together, we get a single block quote:  
<Example :index="$page.frontmatter.start++"/>

To get a block quote with two paragraphs, use:  
<Example :index="$page.frontmatter.start++"/>

Block quotes can interrupt paragraphs:  
<Example :index="$page.frontmatter.start++"/>

In general, blank lines are not needed before or after block quotes:  
<Example :index="$page.frontmatter.start++"/>

However, because of laziness, a blank line is needed between a block quote and a following paragraph:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

It is a consequence of the Laziness rule that any number of initial `>`s may be omitted on a continuation line of a nested block quote:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

When including an indented code block in a block quote, remember that the [block quote marker](https://github.github.com/gfm/#block-quote-marker) includes both the `>` and a following space. So _five spaces_ are needed after the `>`:  
<Example :index="$page.frontmatter.start++"/>
