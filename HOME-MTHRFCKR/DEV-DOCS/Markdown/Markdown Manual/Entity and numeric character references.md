{{($page.frontmatter.start = 321) ? null : null}}
### Entity and numeric character references

Valid HTML entity references and numeric character references can be used in place of the corresponding Unicode character, with the following exceptions:

- Entity and character references are not recognized in code blocks and code spans.

- Entity and character references cannot stand in place of special characters that define structural elements in CommonMark.  For example, although `&#42;` can be used in place of a literal `*` character, `&#42;` cannot replace `*` in emphasis delimiters, bullet list markers, or thematic breaks.

Conforming CommonMark parsers need not store information about whether a particular character was represented in the source using a Unicode character or an entity reference.

[Entity references](https://github.github.com/gfm/#entity-references) consist of `&` + any of the valid HTML5 entity names + `;`. The document [https://html.spec.whatwg.org/multipage/entities.json](https://html.spec.whatwg.org/multipage/entities.json) is used as an authoritative source for the valid entity references and their corresponding code points.  
<Example :index="$page.frontmatter.start++"/>

[Decimal numeric character](https://github.github.com/gfm/#decimal-numeric-character) consist of `&#` + a string of 1–7 arabic digits + `;`. A numeric character reference is parsed as the corresponding Unicode character. Invalid Unicode code points will be replaced by the REPLACEMENT CHARACTER (`U+FFFD`). For security reasons, the code point `U+0000` will also be replaced by `U+FFFD`.  
<Example :index="$page.frontmatter.start++"/>

[Hexadecimal numeric character](https://github.github.com/gfm/#hexadecimal-numeric-character) consist of `&#` + either `X` or `x` + a string of 1-6 hexadecimal digits + `;`. They too are parsed as the corresponding Unicode character (this time specified with a hexadecimal numeral instead of decimal).  
<Example :index="$page.frontmatter.start++"/>

Here are some nonentities:  
<Example :index="$page.frontmatter.start++"/>

Although HTML5 does accept some entity references without a trailing semicolon (such as `&copy`), these are not recognized here, because it makes the grammar too ambiguous:  
<Example :index="$page.frontmatter.start++"/>

Strings that are not on the list of HTML5 named entities are not recognized as entity references either:  
<Example :index="$page.frontmatter.start++"/>

Entity and numeric character references are recognized in any context besides code spans or code blocks, including URLs, [link titles](https://github.github.com/gfm/#link-title), and [fenced code block](https://github.github.com/gfm/#fenced-code-block) [info strings](https://github.github.com/gfm/#info-string):  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Entity and numeric character references are treated as literal text in code spans and code blocks:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>=

Entity and numeric character references cannot be used in place of symbols indicating structure in CommonMark documents.

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>
