# Inline-structure

## Inline Structure

Once all of the input has been parsed, all open blocks are closed.  
We then “walk the tree,” visiting every node, and parse raw string contents of paragraphs and headings as inlines. At this point we have seen all the link reference definitions, so we can resolve reference links as we go.  

    document
      block_quote
        paragraph
          str "Lorem ipsum dolor"
          softbreak
          str "sit amet."
        list (type=bullet tight=true bullet_char=-)
          list_item
            paragraph
              str "Qui "
              emph
                str "quodsi iracundia"
          list_item
            paragraph
              str "aliquando id"

Notice how the [line ending](https://github.github.com/gfm/#line-ending) in the first paragraph has been parsed as a `softbreak`, and the asterisks in the first list item have become an `emph`.  
An algorithm for parsing nested emphasis and linksBy far the trickiest part of inline parsing is handling emphasis, strong emphasis, links, and images. This is done using the following algorithm.  
When we’re parsing inlines and we hit either  

* a run of `*` or `_` characters, or

* a `[` or `![`

we insert a text node with these symbols as its literal content, and we add a pointer to this text node to the [delimiter stack](https://github.github.com/gfm/#delimiter-stack).  
The [delimiter stack](https://github.github.com/gfm/#delimiter-stack) is a doubly linked list. Each element contains a pointer to a text node, plus information about  

* the type of delimiter (`[`, `![`, `*`, `_`)

* the number of delimiters,

* whether the delimiter is “active” (all are active to start), and

* whether the delimiter is a potential opener, a potential closer, or both (which depends on what sort of characters precede and follow the delimiters).

When we hit a `]` character, we call the *look for link or image* procedure (see below).  
When we hit the end of the input, we call the *process emphasis* procedure (see below), with `stack_bottom`\= NULL.  
_look for link or image_Starting at the top of the delimiter stack, we look backwards through the stack for an opening `[` or `![`delimiter.  

* If we don’t find one, we return a literal text node `]`.

* If we do find one, but it’s not *active*, we remove the inactive delimiter from the stack, and return a literal text node `]`.

* If we find one and it’s active, then we parse ahead to see if we have an inline link/image, reference link/image, compact reference link/image, or shortcut reference link/image.  

  * If we don’t, then we remove the opening delimiter from the delimiter stack and return a literal text node `]`.

  * If we do, then  

    * We return a link or image node whose children are the inlines after the text node pointed to by the opening delimiter.

    * We run *process emphasis* on these inlines, with the `[` opener as `stack_bottom`.

    * We remove the opening delimiter.

    * If we have a link (and not an image), we also set all `[` delimiters before the opening delimiter to *inactive*. (This will prevent us from getting links within links.)

_process emphasis_Parameter `stack_bottom` sets a lower bound to how far we descend in the [delimiter stack](https://github.github.com/gfm/#delimiter-stack). If it is NULL, we can go all the way to the bottom. Otherwise, we stop before visiting `stack_bottom`.  
Let `current_position` point to the element on the [delimiter stack](https://github.github.com/gfm/#delimiter-stack) just above `stack_bottom` (or the first element if `stack_bottom` is NULL).  
We keep track of the `openers_bottom` for each delimiter type (`*`, `_`). and each length of the closing delimiter run (modulo 3). Initialize this to `stack_bottom`.  
Then we repeat the following until we run out of potential closers:  

* Move `current_position` forward in the delimiter stack (if needed) until we find the first potential closer with delimiter `*` or `_`. (This will be the potential closer closest to the beginning of the input – the first one in parse order.)

* Now, look back in the stack (staying above `stack_bottom` and the `openers_bottom` for this delimiter type) for the first matching potential opener (“matching” means same delimiter).

* If one is found:  

  * Figure out whether we have emphasis or strong emphasis: if both closer and opener spans have length >= 2, we have strong, otherwise regular.

  * Insert an emph or strong emph node accordingly, after the text node corresponding to the opener.

  * Remove any delimiters between the opener and closer from the delimiter stack.

  * Remove 1 (for regular emph) or 2 (for strong emph) delimiters from the opening and closing text nodes. If they become empty as a result, remove them and remove the corresponding element of the delimiter stack. If the closing node is removed, reset `current_position` to the next element in the stack.

* If none is found:  

  * Set `openers_bottom` to the element before `current_position`. (We know that there are no openers for this kind of closer up to and including this point, so this puts a lower bound on future searches.)

  * If the closer at `current_position` is not a potential opener, remove it from the delimiter stack (since we know it can’t be a closer either).

  * Advance `current_position` to the next element in the stack.

After we’re done, we remove all delimiters above `stack_bottom` from the delimiter stack.
