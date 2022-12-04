{{($page.frontmatter.start = 621) ? null : null}}
### Autolinks (extension)

GFM enables the `autolink` extension, where autolinks will be recognised in a greater number of conditions.  
[Autolink](https://github.github.com/gfm/#autolink)s can also be constructed without requiring the use of `<` and to `>` to delimit them, although they will be recognized under a smaller set of circumstances. All such recognized autolinks can only come at the beginning of a line, after whitespace, or any of the delimiting characters `*`, `_`, `~`, and `(`.  
An [extended www autolink](https://github.github.com/gfm/#extended-www-autolink) will be recognized when the text `www.` is found followed by a [valid domain](https://github.github.com/gfm/#valid-domain). A [valid domain](https://github.github.com/gfm/#valid-domain) consists of alphanumeric characters, underscores (`_`), hyphens (`-`) and periods (`.`). There must be at least one period, and no underscores may be present in the last two segments of the domain.  
The scheme `http` will be inserted automatically:  
<Example :index="$page.frontmatter.start++"/>

After a [valid domain](https://github.github.com/gfm/#valid-domain), zero or more non-space non-`<` characters may follow:  
<Example :index="$page.frontmatter.start++"/>

We then apply [extended autolink path validation](https://github.github.com/gfm/#extended-autolink-path-validation) as follows:  
Trailing punctuation (specifically, `?`, `!`, `.`, `,`, `:`, `*`, `_`, and `~`) will not be considered part of the autolink, though they may be included in the interior of the link:  
<Example :index="$page.frontmatter.start++"/>

When an autolink ends in `)`, we scan the entire autolink for the total number of parentheses. If there is a greater number of closing parentheses than opening ones, we don’t consider the last character part of the autolink, in order to facilitate including an autolink inside a parenthesis:  
<Example :index="$page.frontmatter.start++"/>

This check is only done when the link ends in a closing parentheses `)`, so if the only parentheses are in the interior of the autolink, no special rules are applied:  
<Example :index="$page.frontmatter.start++"/>

If an autolink ends in a semicolon (`;`), we check to see if it appears to resemble an [entity reference](https://github.github.com/gfm/#entity-references); if the preceding text is `&` followed by one or more alphanumeric characters. If so, it is excluded from the autolink:  
<Example :index="$page.frontmatter.start++"/>

`<` immediately ends an autolink.  
<Example :index="$page.frontmatter.start++"/>

An [extended url autolink](https://github.github.com/gfm/#extended-url-autolink) will be recognised when one of the schemes `http://`, `https://`, or `ftp://`, followed by a [valid domain](https://github.github.com/gfm/#valid-domain), then zero or more non-space non-`<` characters according to [extended autolink path validation](https://github.github.com/gfm/#extended-autolink-path-validation):  
<Example :index="$page.frontmatter.start++"/>

An [extended email autolink](https://github.github.com/gfm/#extended-email-autolink) will be recognised when an email address is recognised within any text node. Email addresses are recognised according to the following rules:  

*   One ore more characters which are alphanumeric, or `.`, `-`, `_`, or `+`.
*   An `@` symbol.
*   One or more characters which are alphanumeric, or `.`, `-`, or `_`. At least one of the characters here must be a period (`.`). The last character must not be one of `-` or `_`. If the last character is a period (`.`), it will be excluded from the autolink.

The scheme `mailto:` will automatically be added to the generated link:  
<Example :index="$page.frontmatter.start++"/>

`+` can occur before the `@`, but not after.  
<Example :index="$page.frontmatter.start++"/>

`.`, `-`, and `_` can occur on both sides of the `@`, but only `.` may occur at the end of the email address, in which case it will not be considered part of the address:  
<Example :index="$page.frontmatter.start++"/>
