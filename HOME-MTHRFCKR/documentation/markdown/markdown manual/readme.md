# GitHub Flavored Markdown Spec

Version 0.29-gfm (2019-04-06)  
This formal specification is based on the [CommonMark Spec](http://spec.commonmark.org/) by [John MacFarlane](http://github.com/jgm) and licensed under [![Creative Commons BY-SA](https://i.creativecommons.org/l/by-sa/4.0/80x15.png)](http://creativecommons.org/licenses/by-sa/4.0/)  

* [1. Introduction](/Introduction/)  

  * [1.1 What is GitHub Flavored Markdown?](/Introduction.html#_1-what-is-github-flavored-markdown)

  * [1.2 What is Markdown?](/Introduction.html#_2-what-is-markdown)

  * [1.3 Why is a spec needed?](/Introduction.html#_3-why-is-a-spec-needed)

  * [1.4 About this document](/Introduction.html#_4-about-this-document)

* [2. Preliminaries](/Preliminaries/)  

  * [2.1 Characters and lines](/Preliminaries/)

  * [2.2 Tabs](/Preliminaries.html#_2-tabs)

  * [2.3 Insecure characters](/Preliminaries.html#_3-insecure-characters)

* [3. Blocks and inlines](/Blocks%20and%20inlines.html)  

  * [3.1 Precedence](/Blocks%20and%20inlines.html)

  * [3.2 Container blocks and leaf blocks](/Blocks%20and%20inlines.html#container-blocks-and-leaf-blocks)

* [4. Leaf blocks](/Leaf%20blocks/)  

  * [4.1 Thematic breaks](/Leaf%20blocks/Thematic%20breaks.html)

  * [4.2 ATX headings](/Leaf%20blocks/ATX%20headings.html)

  * [4.3 Setext headings](/Leaf%20blocks/Setext%20headings.html)

  * [4.4 Indented code blocks](/Leaf%20blocks/Indented%20code%20blocks.html)

  * [4.5 Fenced code blocks](/Leaf%20blocks/Fenced%20code%20blocks.html)

  * [4.6 HTML blocks](/Leaf%20blocks/HTML%20blocks.html)

  * [4.7 Link reference definitions](/Leaf%20blocks/Link%20reference%20definitions.html)

  * [4.8 Paragraphs](/Leaf%20blocks/Paragraphs.html)

  * [4.9 Blank lines](/Leaf%20blocks/Blank%20lines.html)

  * [4.10 Tables (extension)](/Leaf%20blocks/Tables%20extension.html)

* [5. Container blocks](/Container%20blocks/)  

  * [5.1 Block quotes](/Container%20blocks/Block%20quotes.html)

  * [5.2 List items](/Container%20blocks/List%20items.html)

  * [5.3 Task list items (extension)](/Container%20blocks/Task%20list%20items.html)

  * [5.4 Lists](/Container%20blocks/Lists/)

* [6. Inlines](/Inlines/)  

  * [6.1 Backslash escapes](/Inlines/Backslash%20escapes.html)

  * [6.2 Entity and numeric character references](/Inlines/Entity%20and%20numeric%20character%20references.html)

  * [6.3 Code spans](/Inlines/Code%20spans.html)

  * [6.4 Emphasis and strong emphasis](/Inlines/Emphasis%20and%20strong%20emphasis.html)

  * [6.5 Strikethrough (extension)](/Inlines/Strikethrough/)

  * [6.6 Links](/Inlines/Links/)

  * [6.7 Images](/Inlines/Images/)

  * [6.8 Autolinks](/Inlines/Autolinks/)

  * [6.9 Autolinks (extension)](/Inlines/Autolinks%20extension/)

  * [6.10 Raw HTML](/Inlines/Raw%20HTML/)

  * [6.11 Disallowed Raw HTML (extension)](/Inlines/Disallowed%20Raw%20HTML/)

  * [6.12 Hard line breaks](/Inlines/Hard%20line%20breaks/)

  * [6.13 Soft line breaks](/Inlines/Soft%20line%20breaks/)

  * [6.14 Textual content](/Inlines/Textual%20content/)

* [Appendix: A parsing strategy](/Appendix/)  

  * [Overview](/Appendix/Overview/)

  * [Phase 1: block structure](/Appendix/block%20structure/)

  * [Phase 2: inline structure](/Appendix/inline%20structure/)
