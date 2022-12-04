{{($page.frontmatter.start = 632) ? null : null}}
### Raw HTML

Text between `<` and `>` that looks like an HTML tag is parsed as a raw HTML tag and will be rendered in HTML without escaping. Tag and attribute names are not limited to current HTML tags, so custom tags (and even, say, DocBook tags) may be used.  
Here is the grammar for tags:  
A [tag name](https://github.github.com/gfm/#tag-name) consists of an ASCII letter followed by zero or more ASCII letters, digits, or hyphens (`-`).  

An [attribute](https://github.github.com/gfm/#attribute) consists of [whitespace](https://github.github.com/gfm/#whitespace), an [attribute name](https://github.github.com/gfm/#attribute-name), and an optional [attribute value specification](https://github.github.com/gfm/#attribute-value-specification).  

An [attribute name](https://github.github.com/gfm/#attribute-name) consists of an ASCII letter, `_`, or `:`, followed by zero or more ASCII letters, digits, `_`, `.`, `:`, or `-`. (Note: This is the XML specification restricted to ASCII. HTML5 is laxer.)  

An [attribute value specification](https://github.github.com/gfm/#attribute-value-specification) consists of optional [whitespace](https://github.github.com/gfm/#whitespace), a `=` character, optional [whitespace](https://github.github.com/gfm/#whitespace), and an [attribute value](https://github.github.com/gfm/#attribute-value). 
 
An [attribute value](https://github.github.com/gfm/#attribute-value) consists of an [unquoted attribute value](https://github.github.com/gfm/#unquoted-attribute-value), a [single-quoted attribute value](https://github.github.com/gfm/#single-quoted-attribute-value), or a [double-quoted attribute value](https://github.github.com/gfm/#double-quoted-attribute-value).  

An [unquoted attribute value](https://github.github.com/gfm/#unquoted-attribute-value) is a nonempty string of characters not including [whitespace](https://github.github.com/gfm/#whitespace), `"`, `'`, `=`, `<`, `>`, or `` ` ``.  

A [single-quoted attribute value](https://github.github.com/gfm/#single-quoted-attribute-value) consists of `'`, zero or more characters not including `'`, and a final `'`.  

A [double-quoted attribute value](https://github.github.com/gfm/#double-quoted-attribute-value) consists of `"`, zero or more characters not including `"`, and a final `"`.  

An [open tag](https://github.github.com/gfm/#open-tag) consists of a `<` character, a [tag name](https://github.github.com/gfm/#tag-name), zero or more [attributes](https://github.github.com/gfm/#attribute), optional [whitespace](https://github.github.com/gfm/#whitespace), an optional `/` character, and a `>` character.  

A [closing tag](https://github.github.com/gfm/#closing-tag) consists of the string `</`, a [tag name](https://github.github.com/gfm/#tag-name), optional [whitespace](https://github.github.com/gfm/#whitespace), and the character `>`.  

An [HTML comment](https://github.github.com/gfm/#html-comment) consists of `<!--` + _text_ + `-->`, where _text_ does not start with `>` or `->`, does not end with `-`, and does not contain `--`. (See the [HTML5 spec](http://www.w3.org/TR/html5/syntax.html#comments).)  

A [processing instruction](https://github.github.com/gfm/#processing-instruction) consists of the string `<?`, a string of characters not including the string `?>`, and the string `?>`.  

A [declaration](https://github.github.com/gfm/#declaration) consists of the string `<!`, a name consisting of one or more uppercase ASCII letters,[whitespace](https://github.github.com/gfm/#whitespace), a string of characters not including the character `>`, and the character `>`.  

A [CDATA section](https://github.github.com/gfm/#cdata-section) consists of the string `<![CDATA[`, a string of characters not including the string `]]>`, and the string `]]>`.  

An [HTML tag](https://github.github.com/gfm/#html-tag) consists of an [open tag](https://github.github.com/gfm/#open-tag), a [closing tag](https://github.github.com/gfm/#closing-tag), an [HTML comment](https://github.github.com/gfm/#html-comment), a [processing instruction](https://github.github.com/gfm/#processing-instruction), a [declaration](https://github.github.com/gfm/#declaration), or a [CDATA section](https://github.github.com/gfm/#cdata-section).  

Here are some simple open tags:  
<Example :index="$page.frontmatter.start++"/>

Empty elements:
<Example :index="$page.frontmatter.start++"/>

[Whitespace](https://github.github.com/gfm/#whitespace) is allowed:  
<Example :index="$page.frontmatter.start++"/>

With attributes:  
<Example :index="$page.frontmatter.start++"/>

Custom tag names can be used:  
<Example :index="$page.frontmatter.start++"/>

Illegal tag names, not parsed as HTML:  
<Example :index="$page.frontmatter.start++"/>

Illegal attribute names:  
<Example :index="$page.frontmatter.start++"/>

Illegal attribute values:  
<Example :index="$page.frontmatter.start++"/>

Illegal [whitespace](https://github.github.com/gfm/#whitespace):  
<Example :index="$page.frontmatter.start++"/>

Missing [whitespace](https://github.github.com/gfm/#whitespace):  
<Example :index="$page.frontmatter.start++"/>

Closing tags:  
<Example :index="$page.frontmatter.start++"/>

Illegal attributes in closing tag:  
<Example :index="$page.frontmatter.start++"/>

Comments:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Not comments:  
<Example :index="$page.frontmatter.start++"/>

Processing instructions:  
<Example :index="$page.frontmatter.start++"/>

Declarations:  
<Example :index="$page.frontmatter.start++"/>

CDATA sections:  
<Example :index="$page.frontmatter.start++"/>

Entity and numeric character references are preserved in HTML attributes:  
<Example :index="$page.frontmatter.start++"/>

Backslash escapes do not work in HTML attributes:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>
