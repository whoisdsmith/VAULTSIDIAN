# Regex

# [Detect and replace text paragraph in a markdown document](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document)

I am breaking my head trying to write/ use one of the existing markdown parsers to *find and replace* every text paragraph in a markdown document and leave everything else untouched.

Example Input:

```javascript
# A First Level Header

## Second Level Header

Now is the time for all good men to come to the aid of their country. This is just a regular paragraph.

The quick brown fox jumped over the lazy dog's back.

### Header 3

> This is a blockquote.
> 
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote
```

Desired effect is to identify paragraphs and replace them, e.g.

```javascript
# A First Level Header

## Second Level Header

[replaced]

[replaced]

### Header 3

> This is a blockquote.
> 
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote
```

Existing libraries such as [`marked`](https://www.npmjs.com/package/marked) or [`markdown-it`](https://www.npmjs.com/package/markdown-it) appear to be incapable of parsing and re-creating markdown document without side-effects.

What is the best approach to find and replace a text paragraph in a markdown document?

- [javascript](https://stackoverflow.com/questions/tagged/javascript "show questions tagged 'javascript'")
- [regex](https://stackoverflow.com/questions/tagged/regex "show questions tagged 'regex'")
- [markdown](https://stackoverflow.com/questions/tagged/markdown "show questions tagged 'markdown'")

- You should *at least* provide example of input & desired output

    – [Thomas Ayoub](https://stackoverflow.com/users/2307070/thomas-ayoub "28,558 reputation")

    [Jan 21, 2016 at 13:55](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document#comment57584770_34914559)

- I may rise a conclusion a bit fast but would a markdown paragraph be anything that start with a letter?

    – [Thomas Ayoub](https://stackoverflow.com/users/2307070/thomas-ayoub "28,558 reputation")

    [Jan 21, 2016 at 14:22](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document#comment57585955_34914559)

- 1

    @Thomas I can think of quite a few examples when a paragraph does not start with a character, e.g. [gist.github.com/gajus/d154559b6a7011d19ae4](https://gist.github.com/gajus/d154559b6a7011d19ae4)

    – [Gajus](https://stackoverflow.com/users/368691/gajus "65,168 reputation")

    [Jan 21, 2016 at 14:31](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document#comment57586370_34914559)

- It gets a bit more tricky when lists come into play, e.g. `1. a` and `a. a` indicates a start of a list.

    – [Gajus](https://stackoverflow.com/users/368691/gajus "65,168 reputation")

    [Jan 21, 2016 at 14:32](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document#comment57586437_34914559)

- 1

    For the record, there is a discussion (inconclusive at the time of writing) about how `markdown-it` can be used to achieve this goal. [github.com/markdown-it/markdown-it/issues/195](https://github.com/markdown-it/markdown-it/issues/195)

    – [Gajus](https://stackoverflow.com/users/368691/gajus "65,168 reputation")

    [Jan 21, 2016 at 14:47](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document#comment57587071_34914559)

## 2 Answers

That's a well known type of problems - source map info required to find source ranges by elements of result. At this moment i don't know markdown parsers with full and correct support of source maps.

But markdown-it and reference commonmark parsers can provide info about source lines (without columns). If you need to do something with root blocks only, then such limited lines info will be enougth. For example, [markdown-it demo](http://markdown-it.github.io/) use lines mapping to srcoll panes in sync.

---

Paragraphs in Markdown are essentially any block of text which is not any other block level construct (as defined by the [Syntax Rules](http://daringfireball.net/projects/markdown/syntax)). So a paragraph is a block of text which is not a header, list, blockquote, codeblock, or horizontal rules (as those are the only other block level constructions defined in Markdown--ignoring some unofficial extensions).

As you are only interested in finding root level paragraphs (not nested ones), a simple approach may be to simply split your document on double line breaks and run a regex against the beginning of each block checking for tokens which identify the non-paragraph types. If it starts with four or more spaces (or one tab); not a paragraph. If it starts with a 0-3 spaces and a hash; not a paragraph. If is starts with 0-3 spaces, a `>` and a space; not a paragraph. If it starts with 0-3 spaces, one of `*, -, +`, and a space, not a paragraph. And so on…

One trouble spot is headers. Headers can only ever be one line, to a hash header may not have a blank line between it and the paragraph following it. However, that is fairly easy to work around as headers can only ever be one line. It you find a header (block that starts with a hash), split off the first line and anything else is a separate block which may or may not be a paragraph.

Of course, a trickier problem is setext headers as the second line identifies them has headers. However a regex that looks for the first newline followed by 3 or more `-` or `=` should do the trick.

If you look at some of the existing Markdown implementations, most of the regex you would need already exists. Of course, you would be developing your own Markdown parser of sorts and various edge cases might sneak through. However, given your very specific needs, I'm not sure you will find an existing parser which will give you what you want.

---

- Yes, but if you have `* foo* bar.` then that is a list item. Notice the space after the first `*`. I covered that scenario by stating that a space must follow the token. And yes, it really is that simple. That is the method the reference implementation uses.

    – [Waylan](https://stackoverflow.com/users/866026/waylan "33,126 reputation")

    [Jan 21, 2016 at 15:24](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document#comment57588634_34927282)

- See an example here: [johnmacfarlane.net/babelmark2/?normalize=1&text=](http://johnmacfarlane.net/babelmark2/?normalize=1&text=)*foo*+bar.%0A%0A*+foo*+bar.

    – [Waylan](https://stackoverflow.com/users/866026/waylan "33,126 reputation")

    [Jan 21, 2016 at 15:25](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document#comment57588699_34927282)

- Close. A paragraph can have up to three spaces at the beginning and still be a paragraph, but your regex doesn't match that. Also, you should add some lists to your sample document. Consider a multi-line list item. The second line does not need to be indented, but is not a paragraph. however, your regex still matches it.

    – [Waylan](https://stackoverflow.com/users/866026/waylan "33,126 reputation")

    [Jan 21, 2016 at 15:32](https://stackoverflow.com/questions/34914559/detect-and-replace-text-paragraph-in-a-markdown-document#comment57588986_34927282)

---

# Regex for Markdown Syntax

Sep 28, 2021

## Preface

First of all, to those who are interested, I have made this extremely fun Clickbait Title generator. And to make it, I used Google’s T5 transformer. Yes! The same model with a conditional head which Google uses in its translator. I did not use ther conditional head and fed the data simply by tokenizing the sentences, extracting the proper nouns, adjectives, nouns and named entities as the input and the corresponding sentence as the output. This was a simple, fun job and I just did it to show to my customers how I can make their lives easier using Google Colab. You can view the Colab Gist here:

```
https://chubakbidpaa.com/cbgen
```

Now, onwards to the main topic!

## Markdown, What is It?

Markdown was created by Aaron Swartz and John Gruber in 2002. Their aim was to create a common language that would replace the demented BBCode and other garbage that floated non-WYSIWYG editors. I still remember the PAIN that was the BBCode as a child. So when I joined Reddit, and later Stack Overflow, I really appreciated how slick Markdown was.

The format quickly took over the web in the 2010s and today most if not all platforms support it, in a way at least. Everyone has their own interpretation of Markdown. I’m currently writing down this blogpost in its purest form which is recognized by Jekyll.

## Why Did I Wrote These?

I was thinking about useful CLI tools I can make in Golang, and it struck me that Markdown to Word does not exist. Even if it does, it’s not very good I bet! So I decided to fire up Go and write one myself. And to recognize the syntax, of course I turned to Regex (what else?). Please star [the repo](https://github.com/Chubek/md2docx). So far I’ve only written the Regex patterns but the rest is coming, since these days I’m pretty much free from my usual burden of “making money to survive” and I’ve never felt better!

## So Chubak, Stop Lingering and Tell Us the Patterns

Ok, let’s start!

**Note 1**: You can test all the stuff [here](https://regex101.com/).

**Note 2**: I’ve based everything on the flavour of MD found [here](https://www.markdownguide.org/basic-syntax/) — except for the tables which is on another page.

### One: Headings

In MD, headings are pretty simple. You just do this:

```
# Header1
## Header2
### Header3
.
.
###### Header 6
```

So the corresponding regexes (regexi?) for them will be:

```
headerOne        = `(#{1}\s)(.*)`
headeTwo         = `(#{2}\s)(.*)`
headerThree      = `(#{3}\s)(.*)`
headerFour       = `(#{4}\s)(.*)`
headerFive       = `(#{5}\s)(.*)`
headerSix        = `(#{6}\s)(.*)`
```

The `{n}` tells regex to match the character `#` in exctly that amount. The `\s` after that says there MUST be a whitespace character. Then, you can match absolutely EVERYTHING!

### Two: Bold and Italic Text

There are soooo many ways to write bold, italic and bold/italic text in MD that it won’t be really easy to catch them all using Regex solely by itself. However, what we can do is to catch the “possible” combinations and then count the occurances to assert if it’s bold, italic, or bold/italic. So for example, `**BOLD TEXT**` is the same as `__BOLD TEXT__`, which is the same as `_*BOLD TEXT*_` which is the same as… You get the gist! So let’s match all the possiblities with:

```
boldItalicText   = `(\*|\_)+(\S+)(\*|\_)+`
```

The `(\*|\_)+` says “match either * or _ in multiple occurances” and after that we have `\S+` which is what comes next. Problem with this is, it matches more than 3 occurances. Even if we say match three like we did before, then `\S+` will get the asterisks and underlines AS IT SHOULD. As I said, we clearly need some logic to deal with possible combinations.

### Three: Links

In MD, here’s how we use links:

```
[Link Text](https://url.com "Optionl Alt")
```

We need to match the optional alt “optinally” — but we don’t need it in Word so we can get rid of it through code. So the regex is:

```
linkText         = `(\[.*\])(\((http)(?:s)?(\:\/\/).*\))`
```

So what `(\[.*\])` does that it matches titles like `[Hello!]`. Then we have `(http)(?:s)?` that will match both `http` and `https`. Then we catch the rest.

### Four: Images

Images are similar to links:

```
![Alternative text](path/to/img.png "Text")
```

So what we do here is this:

```
imageFile        = `(\!)(\[(?:.*)?\])(\(.*(\.(jpg|png|gif|tiff|bmp))(?:(\s\"|\')(\w|\W|\d)+(\"|\'))?\)`
```

At first we match the `!`. Then we do the same thing we did with links with `(\[(?:.*)?\])` — however, this time, we make the text optional. We then match everything BUT we then look for `(\.(jpg|png|gif|tiff|bmp)` which matches `.png`, `.jpg`, `.tiff`, `.gif` and `.bmp`. After that we match the text with `(?:(\s\"|\')(\w|\W|\d)+(\"|\'))?` but we use `(?:)?` to make it optional.

### Five: Unordered List

So, unordered lists in MD are pretty straightforwrd:

```
* Item 1
* Item 2
* Item 3
```

So to match them, we could write:

```
listText         = `(^(\W{1})(\s)(.*)(?:$)?)+`
```

So first we have `^(\W{1})`. This says “look for punctuations, exactly one, at the beginning of the line”. We then have `(\s)` which says there MUST be a whitespace. We then match everything. At the end we use the ol’ reliable optional lookahead `(?:$)?` to say it MAYBE the end of the line, to match the last list line. We don’t NEED to make it optional, but just to to be safe! At the very end we wrap everything in a supergroup and add a `+` to say look for additionals.

### Six: Numbered Text

It’s pretty similar to the latter:

```
numberedListText = `(^(\d+\.)(\s)(.*)(?:$)?)+`
```

Except, instead of `\W` we use `\d+` which matcher one or more numbers. We could have combined it with the last one, but I need the parser to differntiate between them.

### Seven: Block Quotes

So a blockquote in MD is like:

```
> I said a very important thing!
```

So to match this:

```
blockQuote       = `((^(\>{1})(\s)(.*)(?:$)?)+`
```

Basically, we say, with `^(\>{1})`, to look for exactly ONE `>` at the beginning of the line. Then match everything, and finish the line. I don’t know why I made it optional… HELP! I’m addicted to `(?:)?`!

### Eight: Inline Code

So inline code needs a LOT of additional parsing. But to match it:

```
inlineCode       = "(\\`{1})(.*)(\\`{1})"
```

Which basically matches a `\``. Writing this, I realized the parsing could be difficult because We have cases where we need need to escape the backtick.

### Nine: Code Block

So in code block, which is wrapped inside three backticks, we can’t use `$`. We’ll have to match the newline character, `\n`.

```
codeBlock        = "(\\`{3}\\n+)(.*)(\\n+\\`{3})"
```

So we match three backticks, one or more newline characters, and then wrap everything inbetween. The reason we can’t use `$` is that we also need the SPACE inbwtween. Try it on regex101.com and you’ll see why.

### Ten: Horizontal Line

So in MD, a horizontal line is inserted with `---`, `***`, or `===`. It’s pretty simple, and straightforward:

```
horizontalLine   = `(\=|\-|\*){3}`
```

### Eleven: Email Text

The purpose of this pattern is not to validate the email, otherwise it would have required [THOUSANDS of characters](https://emailregex.com/)! This is way beyond the scopre of this pattern. We don’t care if the emails are valid, we just want it to match any email-like string:

```
emailText        = `(\<{1})(\S+@\S+)(\>{1})`
```

So we match `<` and `>` at the beginning and the end. Then we match `(\S+@\S+)` ANY non-whitespace character coupled with an at sign.

### And finally… TABLES

So this si the hardest part and I know I’ll be spending hours to parse this. In MD tables are written like this:

```
|New|World|Order|
|---|-----|-----|
|It's|A Very Wonderful|Thing|
|And I|Freaking Love|It!|
```

The thing about this md2docx project is, I could care less if regex is “correct” or not because for some reason that’s unbenownest to me, I’m not using a regex engine to convert the regex to HTML and then convert that to docx. This is not something I’m doing for a job, it’s something I’m doing for fun and **FUN IS ALWAYS IN THE CHALLENGE!**

So let’s see what I’ve come up with:

```
tableText        = `(((\|)([a-zA-Z\d+\s#!@'"():;\\\/.\[\]\^<={$}>?(?!-))]+))+(\|))(?:\n)?((\|)(-+))+(\|)(\n)((\|)(\W+|\w+|\S+))+(\|$)`
```

---

# [How to select parts of text from markdown with regexp?](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp)

[Ask Question](https://stackoverflow.com/questions/ask)

Asked 5 years, 8 months ago

Modified [5 years, 8 months ago](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp?lastactivity "2017-03-08 22:02:45Z")

Viewed 461 times

This question shows research effort; it is useful and clear

1

This question does not show any research effort; it is unclear or not useful

Save this question.

[](https://stackoverflow.com/posts/42681418/timeline)

Show activity on this post.

I have next text:

```less
#Header
my header text

##SubHeader
my sub header text

###Sub3Header
my sub 3 text

#Header2
my header2 text
```

I need to select text from "#Header" to "#Header2".

I tried to wrote regexp: [http://regexr.com/3ffva](http://regexr.com/3ffva) but it's do not match what i needed.

- [regex](https://stackoverflow.com/questions/tagged/regex "show questions tagged 'regex'")

[Share](https://stackoverflow.com/q/42681418/17231101 "Short permalink to this question")

Share a link to this question (Includes your user id)

Copy link[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/ "The current license for this post: CC BY-SA 3.0")

Edit

Follow

Follow this question to receive notifications

asked Mar 8, 2017 at 20:34

[

![Dmitry Bubnenkov's user avatar](https://www.gravatar.com/avatar/e80f2b22b8c98730708ad3842c11604b?s=64&d=identicon&r=PG)

](<https://stackoverflow.com/users/1432751/dmitry-bubnenkov>)

[Dmitry Bubnenkov](https://stackoverflow.com/users/1432751/dmitry-bubnenkov)Dmitry Bubnenkov

8,8211616 gold badges7474 silver badges129129 bronze badges

1

- Does Headers contains `#` in middle of Heading text/name ?

    – [MohaMad](https://stackoverflow.com/users/7529266/mohamad "2,385 reputation")

    [Mar 8, 2017 at 21:24](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp#comment72488474_42681418)

[Add a comment](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp# "Use comments to ask for more information or suggest improvements. Avoid answering questions in comments.")  | [](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp# "Expand to show all comments on this post")

## 3 Answers 3

Sorted by: [Reset to default](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp?answertab=scoredesc#tab-top)

Highest score (default) Trending (recent votes count more) Date modified (newest first) Date created (oldest first)

This answer is useful

0

This answer is not useful

Save this answer.

[](https://stackoverflow.com/posts/42682747/timeline)

Show activity on this post.

Depending on your regex flavor you can use:

`(^#{1}.+)(.*\n)*`

As shown here: [http://regexr.com/3fg08](http://regexr.com/3fg08)

Alternately, you can use Vim's very magic mode:

`\v(^#{1}.+)(.*\n)*(^#{1}\w+)`

[Share](https://stackoverflow.com/a/42682747/17231101 "Short permalink to this answer")

Share a link to this answer (Includes your user id)

Copy link[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/ "The current license for this post: CC BY-SA 3.0")

Edit

Follow

Follow this answer to receive notifications

answered Mar 8, 2017 at 22:02

[

![builder-7000's user avatar](https://www.gravatar.com/avatar/b6d433ceb0bd5eb9ae492b50354849e0?s=64&d=identicon&r=PG&f=1)

](<https://stackoverflow.com/users/5411198/builder-7000>)

[builder-7000](https://stackoverflow.com/users/5411198/builder-7000)builder-7000

6,92533 gold badges1818 silver badges4242 bronze badges

[Add a comment](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp# "Use comments to ask for more information or suggest improvements. Avoid comments like “+1” or “thanks”.")  | [](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp# "Expand to show all comments on this post")

This answer is useful

1

This answer is not useful

Save this answer.

[](https://stackoverflow.com/posts/42681825/timeline)

Show activity on this post.

With looking ahead for closing capture and also matching, before next heading:

1- without multi-line flag

```scss
(^|\n)#([^#]+?)\n([^]+?)(?=\n#[^#]|$)
```

[Demo without multi-line flag](https://regex101.com/r/8e7nPL/3)

Description:

- Group 1 captures first of string or new line that follows # and no other #, that means new Heading starts there.

- Group 2 captures Heading title

- Group 3 captures any thing till the next heading or end of string

- Group 4 is non-capturing and looks ahead for new heading, or end of text.

---

2- with multi-line flag

```scss
^#([^#]+?)\n([^]+?)(?=^#[^#])
```

[Demo with Multi-line flag](https://regex101.com/r/8e7nPL/2)

Description:

- first, add `#--` at the end of text, for matching last Heading by this regex!

- Starts matching from first char of line by `^` and matches `#` with no # in heading text. Group 1 captured: *Heading* before `\n`

- Group 2 captures texts till next Heading start, that defined by just one # at starting line.

[Share](https://stackoverflow.com/a/42681825/17231101 "Short permalink to this answer")

Share a link to this answer (Includes your user id)

Copy link[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/ "The current license for this post: CC BY-SA 3.0")

Edit

Follow

Follow this answer to receive notifications

[edited Mar 8, 2017 at 21:22](https://stackoverflow.com/posts/42681825/revisions "show all edits to this post")

answered Mar 8, 2017 at 20:59

[

![MohaMad's user avatar](https://i.stack.imgur.com/IGW24.jpg?s=64&g=1)

](<https://stackoverflow.com/users/7529266/mohamad>)

[MohaMad](https://stackoverflow.com/users/7529266/mohamad)MohaMad

2,38522 gold badges1313 silver badges2525 bronze badges

1

- ECMAScript regex. For python check comment above.

    – [tsr](https://stackoverflow.com/users/2261423/tsr "364 reputation")

    [Jul 13, 2021 at 7:43](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp#comment120812238_42681825)

[Add a comment](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp# "Use comments to ask for more information or suggest improvements. Avoid comments like “+1” or “thanks”.")  | [](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp# "Expand to show all comments on this post")

This answer is useful

2

This answer is not useful

Save this answer.

[](https://stackoverflow.com/posts/42681472/timeline)

Show activity on this post.

[`^#[^#\n]+([\W\w]*?)^#[^#\n]+`](https://regex101.com/r/pm4weq/1)

Basic idea: find first level-1 heading, find any text *until*… second level-1 heading.

- `^#[^#\n]+` first level-1 heading
  - `^` start of line (because of multi-line flag)
  - `[^#\n]+` Any character that isn't `#` or a newline character. Repeat 1 or more times.
- `([\W\w]*?)` any text until next matching part
- `^#[^#\n]+` second level-1 heading (see above)

Flags: multiline.

[Share](https://stackoverflow.com/a/42681472/17231101 "Short permalink to this answer")

Share a link to this answer (Includes your user id)

Copy link[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/ "The current license for this post: CC BY-SA 3.0")

Edit

Follow

Follow this answer to receive notifications

answered Mar 8, 2017 at 20:38

[

![Whothehellisthat's user avatar](https://www.gravatar.com/avatar/f6d261261425b72bba389146c4cf2d2e?s=64&d=identicon&r=PG)

](<https://stackoverflow.com/users/1086525/whothehellisthat>)

[Whothehellisthat](https://stackoverflow.com/users/1086525/whothehellisthat)Whothehellisthat

2,00611 gold badge1414 silver badges1313 bronze badges

1

- Works with python regex. Just need to take index from match start to group end.

    – [tsr](https://stackoverflow.com/users/2261423/tsr "364 reputation")

    [Jul 13, 2021 at 7:42](https://stackoverflow.com/questions/42681418/how-to-select-parts-of-text-from-markdown-with-regexp#comment120812217_42681472)

----
