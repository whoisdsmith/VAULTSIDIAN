{{($page.frontmatter.start = 602) ? null : null}}
### Autolinks

[Autolink](https://github.github.com/gfm/#autolink)s are absolute URIs and email addresses inside `<` and `>`. They are parsed as links, with the URL or email address as the link label.  
A [URI autolink](https://github.github.com/gfm/#uri-autolink) consists of `<`, followed by an [absolute URI](https://github.github.com/gfm/#absolute-uri) followed by `>`. It is parsed as a link to the URI, with the URI as the link’s label.  
An [absolute URI](https://github.github.com/gfm/#absolute-uri), for these purposes, consists of a [scheme](https://github.github.com/gfm/#scheme) followed by a colon (`:`) followed by zero or more characters other than ASCII [whitespace](https://github.github.com/gfm/#whitespace) and control characters, `<`, and `>`. If the URI includes these characters, they must be percent-encoded (e.g. `%20` for a space).  
For purposes of this spec, a [scheme](https://github.github.com/gfm/#scheme) is any sequence of 2–32 characters beginning with an ASCII letter and followed by any combination of ASCII letters, digits, or the symbols plus (”+”), period (”.”), or hyphen (”-”).  
Here are some valid autolinks:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Uppercase is also fine:  
<Example :index="$page.frontmatter.start++"/>

Note that many strings that count as [absolute URIs](https://github.github.com/gfm/#absolute-uri) for purposes of this spec are not valid URIs, because their schemes are not registered or because of other problems with their syntax:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Spaces are not allowed in autolinks:  
<Example :index="$page.frontmatter.start++"/>

Backslash-escapes do not work inside autolinks:  
<Example :index="$page.frontmatter.start++"/>

An [email autolink](https://github.github.com/gfm/#email-autolink) consists of `<`, followed by an [email address](https://github.github.com/gfm/#email-address), followed by `>`. The link’s label is the email address, and the URL is `mailto:` followed by the email address.  
An [email address](https://github.github.com/gfm/#email-address), for these purposes, is anything that matches the [non-normative regex from the HTML5 spec](https://html.spec.whatwg.org/multipage/forms.html#e-mail-state-(type=email)):  

    /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?
    (?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/

Examples of email autolinks:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Backslash-escapes do not work inside email autolinks:  
<Example :index="$page.frontmatter.start++"/>

These are not autolinks:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>
    