{{($page.frontmatter.start = 231) ? null : null}}
### List items

A [list marker](https://github.github.com/gfm/#list-marker) is a [bullet list marker](https://github.github.com/gfm/#bullet-list-marker) or an [ordered list marker](https://github.github.com/gfm/#ordered-list-marker).  
A [bullet list marker](https://github.github.com/gfm/#bullet-list-marker) is a `-`, `+`, or `*` character.  
An [ordered list marker](https://github.github.com/gfm/#ordered-list-marker) is a sequence of 1–9 arabic digits (`0-9`), followed by either a `.` character or a `)`character. (The reason for the length limit is that with 10 digits we start seeing integer overflows in some browsers.)  
The following rules define [list items](https://github.github.com/gfm/#list-items):  

1.  **Basic case.**  If a sequence of lines *Ls* constitute a sequence of blocks *Bs* starting with a [non-whitespace character], and *M* is a list marker of width *W* followed by 1 ≤ *N* ≤ 4 spaces, then the result of prepending *M* and the following spaces to the first line of *Ls*, and indenting subsequent lines of *Ls* by *W + N* spaces, is a list item with *Bs* as its contents.  The type of the list item (bullet or ordered) is determined by the type of its list marker.    
    Exceptions:  
    1.  When the first list item in a [list](https://github.github.com/gfm/#list) interrupts a paragraph—that is, when it starts on a line that would otherwise count as [paragraph continuation text](https://github.github.com/gfm/#paragraph-continuation-text)—then (a) the lines _Ls_ must not begin with a blank line, and (b) if the list item is ordered, the start number must be 1.
    2.  If any line is a [thematic break](https://github.github.com/gfm/#thematic-breaks) then that line is not a list item.

For example, let _Ls_ be the lines  
<Example :index="$page.frontmatter.start++"/>

And let _M_ be the marker `1.`, and _N_ = 2. Then rule #1 says that the following is an ordered list item with start number 1, and the same contents as _Ls_:  
<Example :index="$page.frontmatter.start++"/>

The most important thing to notice is that the position of the text after the list marker determines how much indentation is needed in subsequent blocks in the list item. If the list marker takes up two spaces, and there are three spaces between the list marker and the next [non-whitespace character](https://github.github.com/gfm/#non-whitespace-character), then blocks must be indented five spaces in order to fall under the list item.  

Here are some examples showing how far content must be indented to be put under the list item:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

It is tempting to think of this in terms of columns: the continuation blocks must be indented at least to the column of the first [non-whitespace character](https://github.github.com/gfm/#non-whitespace-character) after the list marker. However, that is not quite right. The spaces after the list marker determine how much relative indentation is needed. Which column this indentation reaches will depend on how the list item is embedded in other constructions, as shown by this example:  
<Example :index="$page.frontmatter.start++"/>

Here `two` occurs in the same column as the list marker `1.`, but is actually contained in the list item, because there is sufficient indentation after the last containing blockquote marker.  
The converse is also possible. In the following example, the word `two` occurs far to the right of the initial text of the list item, `one`, but it is not considered part of the list item, because it is not indented far enough past the blockquote marker:  
<Example :index="$page.frontmatter.start++"/>

Note that at least one space is needed between the list marker and any following content, so these are not list items:  
<Example :index="$page.frontmatter.start++"/>

A list item may contain blocks that are separated by more than one blank line.  
<Example :index="$page.frontmatter.start++"/>

A list item may contain any kind of block:  
<Example :index="$page.frontmatter.start++"/>

A list item that contains an indented code block will preserve empty lines within the code block verbatim.  
<Example :index="$page.frontmatter.start++"/>

Note that ordered list start numbers must be nine digits or less:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

A start number may begin with 0s:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

A start number may not be negative:  
<Example :index="$page.frontmatter.start++"/>

2.  **Item starting with indented code.** If a sequence of lines _Ls_ constitute a sequence of blocks _Bs_starting with an indented code block, and *M* is a list marker of width *W* followed by one space, then the result of prepending _M_ and the following space to the first line of _Ls_, and indenting subsequent lines of _Ls_ by _W + 1_ spaces, is a list item with _Bs_ as its contents. If a line is empty, then it need not be indented. The type of the list item (bullet or ordered) is determined by the type of its list marker. If the list item is ordered, then it is also assigned a start number, based on the ordered list marker.

An indented code block will have to be indented four spaces beyond the edge of the region where text will be included in the list item. In the following case that is 6 spaces:  
<Example :index="$page.frontmatter.start++"/>

And in this case it is 11 spaces:  
<Example :index="$page.frontmatter.start++"/>

If the _first_ block in the list item is an indented code block, then by rule #2, the contents must be indented _one_space after the list marker:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that an additional space indent is interpreted as space inside the code block:  
<Example :index="$page.frontmatter.start++"/>

Note that rules #1 and #2 only apply to two cases: (a) cases in which the lines to be included in a list item begin with a [non-whitespace character](https://github.github.com/gfm/#non-whitespace-character), and (b) cases in which they begin with an indented code block. In a case like the following, where the first block begins with a three-space indent, the rules do not allow us to form a list item by indenting the whole thing and prepending a list marker:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

This is not a significant restriction, because when a block begins with 1-3 spaces indent, the indentation can always be removed without a change in interpretation, allowing rule #1 to be applied. So, in the above case:  
<Example :index="$page.frontmatter.start++"/>

3.  **Item starting with a blank line.** If a sequence of lines _Ls_ starting with a single [blank line](https://github.github.com/gfm/#blank-line) constitute a (possibly empty) sequence of blocks _Bs_, not separated from each other by more than one blank line, and _M_ is a list marker of width _W_, then the result of prepending _M_ to the first line of _Ls_, and indenting subsequent lines of _Ls_ by _W + 1_ spaces, is a list item with _Bs_ as its contents. If a line is empty, then it need not be indented. The type of the list item (bullet or ordered) is determined by the type of its list marker. If the list item is ordered, then it is also assigned a start number, based on the ordered list marker.

Here are some list items that start with a blank line but are not empty:  
<Example :index="$page.frontmatter.start++"/>

When the list item starts with a blank line, the number of spaces following the list marker doesn’t change the required indentation:  
<Example :index="$page.frontmatter.start++"/>

A list item can begin with at most one blank line. In the following example, `foo` is not part of the list item:  
<Example :index="$page.frontmatter.start++"/>

Here is an empty bullet list item:  
<Example :index="$page.frontmatter.start++"/>

It does not matter whether there are spaces following the [list marker](https://github.github.com/gfm/#list-marker):  
<Example :index="$page.frontmatter.start++"/>

Here is an empty ordered list item:  
<Example :index="$page.frontmatter.start++"/>

A list may start or end with an empty list item:  
<Example :index="$page.frontmatter.start++"/>

However, an empty list item cannot interrupt a paragraph:  
<Example :index="$page.frontmatter.start++"/>

4.  **Indentation.** If a sequence of lines _Ls_ constitutes a list item according to rule #1, #2, or #3, then the result of indenting each line of _Ls_ by 1-3 spaces (the same for each line) also constitutes a list item with the same contents and attributes. If a line is empty, then it need not be indented.

Indented one space:  
<Example :index="$page.frontmatter.start++"/>

Indented two spaces:  
<Example :index="$page.frontmatter.start++"/>

Indented three spaces:  
<Example :index="$page.frontmatter.start++"/>

Four spaces indent gives a code block:  
<Example :index="$page.frontmatter.start++"/>

5.  **Laziness.** If a string of lines _Ls_ constitute a [list item](https://github.github.com/gfm/#list-items) with contents _Bs_, then the result of deleting some or all of the indentation from one or more lines in which the next [non-whitespace character](https://github.github.com/gfm/#non-whitespace-character) after the indentation is [paragraph continuation text](https://github.github.com/gfm/#paragraph-continuation-text) is a list item with the same contents and attributes. The unindented lines are called [lazy continuation line](https://github.github.com/gfm/#lazy-continuation-line)s.

Here is an example with [lazy continuation lines](https://github.github.com/gfm/#lazy-continuation-line):  
<Example :index="$page.frontmatter.start++"/>

Indentation can be partially deleted:  
<Example :index="$page.frontmatter.start++"/>

These examples show how laziness can work in nested structures:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

6.  **That’s all.** Nothing that is not counted as a list item by rules #1–5 counts as a [list item](https://github.github.com/gfm/#list-items).

The rules for sublists follow from the general rules [above](https://github.github.com/gfm/#list-items). A sublist must be indented the same number of spaces a paragraph would need to be in order to be included in the list item.  
So, in this case we need two spaces indent:  
<Example :index="$page.frontmatter.start++"/>

One is not enough:  
<Example :index="$page.frontmatter.start++"/>

Here we need four, because the list marker is wider:  
<Example :index="$page.frontmatter.start++"/>

Three is not enough:  
<Example :index="$page.frontmatter.start++"/>

A list may be the first block in a list item:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

A list item can contain a heading:  
<Example :index="$page.frontmatter.start++"/>

5.2.1 Motivation

John Gruber’s Markdown spec says the following about list items:  

1.  “List markers typically start at the left margin, but may be indented by up to three spaces. List markers must be followed by one or more spaces or a tab.”
2.  “To make lists look nice, you can wrap items with hanging indents…. But if you don’t want to, you don’t have to.”
3.  “List items may consist of multiple paragraphs. Each subsequent paragraph in a list item must be indented by either 4 spaces or one tab.”
4.  “It looks nice if you indent every line of the subsequent paragraphs, but here again, Markdown will allow you to be lazy.”
5.  “To put a blockquote within a list item, the blockquote’s `>` delimiters need to be indented.”
6.  “To put a code block within a list item, the code block needs to be indented twice — 8 spaces or two tabs.”

These rules specify that a paragraph under a list item must be indented four spaces (presumably, from the left margin, rather than the start of the list marker, but this is not said), and that code under a list item must be indented eight spaces instead of the usual four. They also say that a block quote must be indented, but not by how much; however, the example given has four spaces indentation. Although nothing is said about other kinds of block-level content, it is certainly reasonable to infer that _all_ block elements under a list item, including other lists, must be indented four spaces. This principle has been called the _four-space rule_.
  
The four-space rule is clear and principled, and if the reference implementation `Markdown.pl` had followed it, it probably would have become the standard. However, `Markdown.pl` allowed paragraphs and sublists to start with only two spaces indentation, at least on the outer level. Worse, its behavior was inconsistent: a sublist of an outer-level list needed two spaces indentation, but a sublist of this sublist needed three spaces. It is not surprising, then, that different implementations of Markdown have developed very different rules for determining what comes under a list item. (Pandoc and python-Markdown, for example, stuck with Gruber’s syntax description and the four-space rule, while discount, redcarpet, marked, PHP Markdown, and others followed `Markdown.pl`’s behavior more closely.)  

Unfortunately, given the divergences between implementations, there is no way to give a spec for list items that will be guaranteed not to break any existing documents. However, the spec given here should correctly handle lists formatted with either the four-space rule or the more forgiving `Markdown.pl` behavior, provided they are laid out in a way that is natural for a human to read.  

The strategy here is to let the width and indentation of the list marker determine the indentation necessary for blocks to fall under the list item, rather than having a fixed and arbitrary number. The writer can think of the body of the list item as a unit which gets indented to the right enough to fit the list marker (and any indentation on the list marker). (The laziness rule, #5, then allows continuation lines to be unindented if needed.)
  
This rule is superior, we claim, to any rule requiring a fixed level of indentation from the margin. The four-space rule is clear but unnatural. It is quite unintuitive that  

    - foo
    
      bar
    
      - baz

should be parsed as two lists with an intervening paragraph,  

    <ul>
    <li>foo</li>
    </ul>
    <p>bar</p>
    <ul>
    <li>baz</li>
    </ul>

as the four-space rule demands, rather than a single list,  

    <ul>
    <li>
    <p>foo</p>
    <p>bar</p>
    <ul>
    <li>baz</li>
    </ul>
    </li>
    </ul>

The choice of four spaces is arbitrary. It can be learned, but it is not likely to be guessed, and it trips up beginners regularly.  
Would it help to adopt a two-space rule? The problem is that such a rule, together with the rule allowing 1–3 spaces indentation of the initial list marker, allows text that is indented _less than_ the original list marker to be included in the list item. For example, `Markdown.pl` parses  

       - one
    
      two

as a single list item, with `two` a continuation paragraph:  

    <ul>
    <li>
    <p>one</p>
    <p>two</p>
    </li>
    </ul>

and similarly  

    >   - one
    >
    >  two

as  

    <blockquote>
    <ul>
    <li>
    <p>one</p>
    <p>two</p>
    </li>
    </ul>
    </blockquote>

This is extremely unintuitive.  
Rather than requiring a fixed indent from the margin, we could require a fixed indent (say, two spaces, or even one space) from the list marker (which may itself be indented). This proposal would remove the last anomaly discussed. Unlike the spec presented above, it would count the following as a list item with a subparagraph, even though the paragraph `bar` is not indented as far as the first paragraph `foo`:  

     10. foo
    
       bar

Arguably this text does read like a list item with `bar` as a subparagraph, which may count in favor of the proposal. However, on this proposal indented code would have to be indented six spaces after the list marker. And this would break a lot of existing Markdown, which has the pattern:  

    1.  foo
    
            indented code

where the code is indented eight spaces. The spec above, by contrast, will parse this text as expected, since the code block’s indentation is measured from the beginning of `foo`.  
The one case that needs special treatment is a list item that _starts_ with indented code. How much indentation is required in that case, since we don’t have a “first paragraph” to measure from? Rule #2 simply stipulates that in such cases, we require one space indentation from the list marker (and then the normal four spaces for the indented code). This will match the four-space rule in cases where the list marker plus its initial indentation takes four spaces (a common case), but diverge in other cases.  
