## Introduction 

### 1. What is GitHub Flavored Markdown?

GitHub Flavored Markdown, often shortened as GFM, is the dialect of Markdown that is currently supported for user content on GitHub.com and GitHub Enterprise.  

This formal specification, based on the CommonMark Spec, defines the syntax and semantics of this dialect. 

GFM is a strict superset of CommonMark. All the features which are supported in GitHub user content and that are not specified on the original CommonMark Spec are hence known as **extensions**, and highlighted as such.  

While GFM supports a wide range of inputs, it’s worth noting that GitHub.com and GitHub Enterprise perform additional post-processing and sanitization after GFM is converted to HTML to ensure security and consistency of the website.  

### 2. What is Markdown?

Markdown is a plain text format for writing structured documents, based on conventions for indicating formatting in email and usenet posts. It was developed by John Gruber (with help from Aaron Swartz) and released in 2004 in the form of a [syntax description](http://daringfireball.net/projects/markdown/syntax) and a Perl script (`Markdown.pl`) for converting Markdown to HTML. In the next decade, dozens of implementations were developed in many languages. Some extended the original Markdown syntax with conventions for footnotes, tables, and other document elements. Some allowed Markdown documents to be rendered in formats other than HTML. Websites like Reddit, StackOverflow, and GitHub had millions of people using Markdown. And Markdown started to be used beyond the web, to author books, articles, slide shows, letters, and lecture notes.  

What distinguishes Markdown from many other lightweight markup syntaxes, which are often easier to write, is its readability. As Gruber writes:  

> The overriding design goal for Markdown’s formatting syntax is to make it as readable as possible. The idea is that a Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions. ([http://daringfireball.net/projects/markdown/](http://daringfireball.net/projects/markdown/))

The point can be illustrated by comparing a sample of [AsciiDoc](http://www.methods.co.nz/asciidoc/) with an equivalent sample of Markdown. Here is a sample of AsciiDoc from the AsciiDoc manual:  

    1. List item one.
    +
    List item one continued with a second paragraph followed by an
    Indented block.
    +
    .................
    $ ls *.sh
    $ mv *.sh ~/tmp
    .................
    +
    List item continued with a third paragraph.
    
    2. List item two continued with an open block.
    +
    --
    This paragraph is part of the preceding list item.
    
    a. This list is nested and does not require explicit item
    continuation.
    +
    This paragraph is part of the preceding list item.
    
    b. List item b.
    
    This paragraph belongs to item two of the outer list.
    --

And here is the equivalent in Markdown:  

    1.  List item one.
    
        List item one continued with a second paragraph followed by an
        Indented block.
    
            $ ls *.sh
            $ mv *.sh ~/tmp
    
        List item continued with a third paragraph.
    
    2.  List item two continued with an open block.
    
        This paragraph is part of the preceding list item.
    
        1. This list is nested and does not require explicit item continuation.
    
           This paragraph is part of the preceding list item.
    
        2. List item b.
    
        This paragraph belongs to item two of the outer list.

The AsciiDoc version is, arguably, easier to write. You don’t need to worry about indentation. But the Markdown version is much easier to read. The nesting of list items is apparent to the eye in the source, not just in the processed document.  

### 3. Why is a spec needed?

John Gruber’s [canonical description of Markdown’s syntax](http://daringfireball.net/projects/markdown/syntax) does not specify the syntax unambiguously. Here are some examples of questions it does not answer:  

1.  How much indentation is needed for a sublist? 

The spec says that continuation paragraphs need to be indented four spaces, but is not fully explicit about sublists. It is natural to think that they, too, must be indented four spaces, but `Markdown.pl` does not require that. This is hardly a “corner case,” and divergences between implementations on this issue often lead to surprises for users in real documents. (See [this comment by John Gruber](http://article.gmane.org/gmane.text.markdown.general/1997).)

2.  Is a blank line needed before a block quote or heading? 

Most implementations do not require the blank line. However, this can lead to unexpected results in hard-wrapped text, and also to ambiguities in parsing (note that some implementations put the heading inside the blockquote, while others do not). (John Gruber has also spoken [in favor of requiring the blank lines](http://article.gmane.org/gmane.text.markdown.general/2146).)

3.  Is a blank line needed before an indented code block? (`Markdown.pl` requires it, but this is not mentioned in the documentation, and some implementations do not require it.)  
    
        paragraph
            code?
    
4.  What is the exact rule for determining when list items get wrapped in `<p>` tags? Can a list be partially “loose” and partially “tight”? What should we do with a list like this?  
    
        1. one
        
        2. two
        3. three
    
    Or this?  
    
        1.  one
            - a
        
            - b
        2.  two
    
    (There are some relevant comments by John Gruber [here](http://article.gmane.org/gmane.text.markdown.general/2554).)  
    
5.  Can list markers be indented? Can ordered list markers be right-aligned?  
    
         8. item 1
         9. item 2
        10. item 2a
    
6.  Is this one list with a thematic break in its second item, or two lists separated by a thematic break?  
    
        * a
        * * * * *
        * b
    
7.  When list markers change from numbers to bullets, do we have two lists or one? (The Markdown syntax description suggests two, but the perl scripts and many other implementations produce one.)  
    
        1. fee
        2. fie
        -  foe
        -  fum
    
8.  What are the precedence rules for the markers of inline structure? For example, is the following a valid link, or does the code span take precedence ?  
    
        [a backtick (`)](/url) and [another backtick (`)](/url).
    
9.  What are the precedence rules for markers of emphasis and strong emphasis? For example, how should the following be parsed?  
    
        *foo *bar* baz*
    
10.  What are the precedence rules between block-level and inline-level structure? For example, how should the following be parsed?  
    
        - `a long code span can contain a hyphen like this
          - and it can screw things up`
    
11.  Can list items include section headings? (`Markdown.pl` does not allow this, but does allow blockquotes to include headings.)  
    
        - # Heading
    
12.  Can list items be empty?  
    
        * a
        *
        * b
    
13.  Can link references be defined inside block quotes or list items?  
    
        > Blockquote [foo].
        >
        > [foo]: /url
    
14.  If there are multiple definitions for the same reference, which takes precedence?  
    
        [foo]: /url1
        [foo]: /url2
        
        [foo][]
    
In the absence of a spec, early implementers consulted `Markdown.pl` to resolve these ambiguities. But `Markdown.pl` was quite buggy, and gave manifestly bad results in many cases, so it was not a satisfactory replacement for a spec.  

Because there is no unambiguous spec, implementations have diverged considerably. As a result, users are often surprised to find that a document that renders one way on one system (say, a Github wiki) renders differently on another (say, converting to docbook using pandoc). To make matters worse, because nothing in Markdown counts as a “syntax error,” the divergence often isn’t discovered right away.  

### 4. About this document

This document attempts to specify Markdown syntax unambiguously. It contains many examples with side-by-side Markdown and HTML. These are intended to double as conformance tests. An accompanying script `spec_tests.py` can be used to run the tests against any Markdown program:  

    python test/spec_tests.py --spec spec.txt --program PROGRAM

Since this document describes how Markdown is to be parsed into an abstract syntax tree, it would have made sense to use an abstract representation of the syntax tree instead of HTML. But HTML is capable of representing the structural distinctions we need to make, and the choice of HTML for the tests makes it possible to run the tests against an implementation without writing an abstract syntax tree renderer.  

This document is generated from a text file, `spec.txt`, written in Markdown with a small extension for the side-by-side tests. The script `tools/makespec.py` can be used to convert `spec.txt` into HTML or CommonMark (which can then be converted into other formats).  

In the examples, the `→` character is used to represent tabs.  