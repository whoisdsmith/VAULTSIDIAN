### Overview

Parsing has two phases:  

1.  In the first phase, lines of input are consumed and the block structure of the document—its division into paragraphs, block quotes, list items, and so on—is constructed. Text is assigned to these blocks but not parsed. Link reference definitions are parsed and a map of links is constructed.
2.  In the second phase, the raw text contents of paragraphs and headings are parsed into sequences of Markdown inline elements (strings, code spans, links, emphasis, and so on), using the map of link references constructed in phase 1.

At each point in processing, the document is represented as a tree of **blocks**. The root of the tree is a `document` block. The `document` may have any number of other blocks as **children**. These children may, in turn, have other blocks as children. The last child of a block is normally considered **open**, meaning that subsequent lines of input can alter its contents. (Blocks that are not open are **closed**.) Here, for example, is a possible document tree, with the open blocks marked by arrows:  

    -> document
      -> block_quote
           paragraph
             "Lorem ipsum dolor\nsit amet."
        -> list (type=bullet tight=true bullet_char=-)
             list_item
               paragraph
                 "Qui *quodsi iracundia*"
          -> list_item
            -> paragraph
                 "aliquando id"
 