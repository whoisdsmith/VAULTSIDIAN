## Blocks and inlines

We can think of a document as a sequence of [blocks](https://github.github.com/gfm/#blocks)—structural elements like paragraphs, block quotations, lists, headings, rules, and code blocks. Some blocks (like block quotes and list items) contain other blocks; others (like headings and paragraphs) contain [inline](https://github.github.com/gfm/#inline) content—text, links, emphasized text, images, code spans, and so on.  

### Precedence

Indicators of block structure always take precedence over indicators of inline structure. So, for example, the following is a list with two items, not a list with one item containing a code span:  
<Example :index="12"/>

This means that parsing can proceed in two steps: first, the block structure of the document can be discerned; second, text lines inside paragraphs, headings, and other block constructs can be parsed for inline structure. The second step requires information about link reference definitions that will be available only at the end of the first step. Note that the first step requires processing lines in sequence, but the second can be parallelized, since the inline parsing of one block element does not affect the inline parsing of any other.  

### Container blocks and leaf blocks

We can divide blocks into two types: [container blocks](https://github.github.com/gfm/#container-block)s, which can contain other blocks, and [leaf blocks](https://github.github.com/gfm/#leaf-block)s, which cannot.