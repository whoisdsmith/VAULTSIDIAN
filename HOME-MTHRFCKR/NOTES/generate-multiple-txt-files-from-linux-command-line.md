# Generate multiple .txt files from Linux command line - Super User

> ## Excerpt

> I'm using Ubuntu and I need to generate multiple .txt files from a large .txt file that contains a word in each new line.

Steps:
Take one word from the large .txt list, e.g. foo
generate .txt and...

---
I'm using Ubuntu and I need to generate multiple .txt files from a large .txt file that contains a word in each new line.

Steps:

1. Take one word from the large .txt list, e.g. **foo**
2. generate .txt and name it \[word\].txt, e.g. **foo.txt**
3. \[word\].txt should contain only the \[word\], e.g. **foo.txt** >contains **foo** text inside

I found that you can generate a .txt from the command line like this:

```
echo 'Hello, world.' >foo.txt 
```

How to do that in batch with the content from the large .txt file?

asked Sep 14 '19 at 18:15

[

![](https://www.gravatar.com/avatar/d279d9f0a1e6847b048e9c742e281cb1?s=64&d=identicon&r=PG)

](<https://superuser.com/users/866914/tom>)

1

Something like this should work, but it doesn't check to make sure that the created filenames are legal. Also, if you have dupes, they will be overwritten:

```
#!/bin/bash

filename=/path/to/your_data_file
while read -r line
do
    echo $line > "$line.txt"
done < "$filename"
echo
```

answered Sep 14 '19 at 18:52

[

![](https://i.stack.imgur.com/C2mem.jpg?s=64&g=1)

](<https://superuser.com/users/1063077/ajgringo619>)

[ajgringo619](https://superuser.com/users/1063077/ajgringo619)ajgringo619

2961 gold badge2 silver badges8 bronze badges

2

This answer is to correct common flaws that are present in other answers. Basic code should be like:

```
#!/bin/bash
filename="/path/to/your_data_file"

while IFS= read -r line
do
    printf '%s\n' "$line" > "$line.txt"
done < "$filename"
```

Improvements:

- [all variables quoted](https://unix.stackexchange.com/a/131767/108618)
- [`printf` instead of `echo`](https://unix.stackexchange.com/q/65803/108618)
- [empty `IFS`](https://unix.stackexchange.com/a/209184/108618)

Some of them may not be strictly necessary if `your_data_file` really contains "a word in each new line" as stated in the question body. But [your comment](https://superuser.com/q/1482643/432690#comment2236131_1482656) mentions handling "multiple words in one line that contains spaces", this requires non-robust solutions to be improved. It's better to get used to good practices in shell scripting and to write robust code from the start.

answered Sep 16 '19 at 6:39

[

![](https://www.gravatar.com/avatar/4c5b24abfdbe0d1ba60f3c012b5f85fe?s=64&d=identicon&r=PG)

](<https://superuser.com/users/432690/kamil-maciorowski>)

[Kamil Maciorowski](https://superuser.com/users/432690/kamil-maciorowski)Kamil Maciorowski

56.2k22 gold badges100 silver badges154 bronze badges

This might be a lot quicker for a large file...

# !/bin/bash

filename=/path/to/your\_data\_file

sort -u "$filename" |
( IFS=
  while read -r line
  do
      echo $line > "$line.txt"
  done
)

answered Sep 15 '19 at 10:53

[

![](https://i.stack.imgur.com/OPf7Z.jpg?s=64&g=1)

](<https://superuser.com/users/346288/hannu>)

[Hannu](https://superuser.com/users/346288/hannu)Hannu

7,4623 gold badges18 silver badges33 bronze badges

2

## Your Answer

- Links
- Images
- Styling/Headers
- Lists
- Blockquotes
- Code
- HTML
- Tables
- [Advanced help](https://superuser.com/editing-help)

In most cases, a plain URL will be recognized as such and automatically linked:

Visit <https://area51.stackexchange.com/> regularly!
Use angle brackets to force linking: Have you seen <https://superuser.com>?

To create fancier links, use Markdown:

Here's \[a link\](https://www.example.com/)! And a reference-style link to \[a panda\]\[1\].
References don't have to be \[numbers\]\[question\].

 \[1\]: https://notfound.stackexchange.com/
 \[question\]: https://english.stackexchange.com/questions/11481

You can add tooltips to links:

Click \[here\](https://diy.stackexchange.com "this text appears when you mouse over")!
This works with \[reference links\]\[blog\] as well.

 \[blog\]: https://stackoverflow.blog/ "click here for updates"

Images are exactly like links, but they have an exclamation point in front of them:

!\[a busy cat\](https://cdn.sstatic.net/Sites/stackoverflow/Img/error-lolcat-problemz.jpg)
!\[two muppets\]\[1\]

 \[1\]: https://i.imgur.com/I5DFV.jpg "tooltip"

The word in square brackets is the alt text, which gets displayed if the browser can't show the image. Be sure to include meaningful alt text for screen-reading software.

Be sure to use text styling sparingly; only where it helps readability.

\*This is italicized\*, and so
is \_this\_.

\*\*This is bold\*\*, just like \_\_this\_\_.

You can \*\*\*combine\*\*\* them
if you \_\_\_really have to\_\_\_.

To break your text into sections, you can use headers:

A Large Header
==============

Smaller Subheader
-----------------

Use hash marks if you need several levels of headers:

\# Header 1 #

## Header 2 ##

### Header 3 ###

Both bulleted and numbered lists are possible:

\- Use a minus sign for a bullet
- Or plus sign
\* Or an asterisk

1. Numbered lists are easy
2. Markdown keeps track of
   the numbers for you
7. So this will be item 3.

1. Lists in a list item:
 \- Indented four spaces.
 \* indented eight spaces.
 \- Four spaces again.
2. You can have multiple
 paragraphs in a list items.

 Just be sure to indent.

\> Create a blockquote by
> prepending “>” to each line.
>
> Other formatting also works here, e.g.
>
> 1. Lists or
> 2. Headings:
>
> ## Quoted Heading ##

You can even put blockquotes in blockquotes:

\> A standard blockquote is indented
> > A nested blockquote is indented more
> > > > You can nest to any depth.

To create code blocks or other preformatted text, indent by four spaces or surround with groups of backticks:

 This will be displayed in a monospaced font. The first four spaces
 will be stripped off, but all other whitespace will be preserved.

\`\`\`
Markdown and HTML are turned off in code blocks:
<i>This is not italic</i>, and \[this is not a link\](https://example.com)
\`\`\`

To create not a block, but an inline code span, use backticks:

The \`$\` character is just a shortcut for \`window.jQuery\`.

If you want to have a preformatted block within a list, indent by eight spaces:

1\. This is normal text.
2. So is this, but now follows a code block:

 Skip a line and indent eight spaces.
 That's four spaces for the list
 and four to trigger the code block.

If you need to do something that Markdown can't handle, use HTML. Note that [we only support a very strict subset of HTML!](https://meta.stackexchange.com/questions/1777/what-html-tags-are-allowed)

Strikethrough humor is <strike>funny</strike>.

Markdown is smart enough not to mangle your span-level HTML:

<b>Markdown works \*fine\* in here.</b>

Block-level HTML elements have a few restrictions:

1. They must be separated from surrounding text by blank lines.
2. The begin and end tags of the outermost block element must not be indented.
3. Markdown can't be used within HTML blocks.

<pre>
    You can <em>not</em> use Markdown in here.
</pre>

You can create tables using the [GitHub-flavored markdown format](https://github.github.com/gfm/#tables-extension-).

| A header | Another header |
| -------- | -------------- |
| First    | row            |
| Second   | row            |

- A header row is required and must be followed by a separator row with the same number of cells
- Cells are separated by a pipe (`|`) symbol

Set the **alignment** of a table column by placing a `:` on the left, right, or both sides of a separator in the separator line.

| left | center | right |
|:---- |:------:| -----:|
| One  | Two    | Three |

## Not the answer you're looking for? Browse other questions tagged [linux](https://superuser.com/questions/tagged/linux "show questions tagged 'linux'") [command-line](https://superuser.com/questions/tagged/command-line "show questions tagged 'command-line'") [bash](https://superuser.com/questions/tagged/bash "show questions tagged 'bash'") [batch](https://superuser.com/questions/tagged/batch "show questions tagged 'batch'") [generator](https://superuser.com/questions/tagged/generator "show questions tagged 'generator'") or [ask your own question](https://superuser.com/questions/ask)
