{{($page.frontmatter.start = 338) ? null : null}}
### Code spans

A [backtick string](https://github.github.com/gfm/#backtick-string) is a string of one or more backtick characters (`` ` ``) that is neither preceded nor followed by a backtick.  
A code span(@) begins with a backtick string and ends with a backtick string of equal length.  The contents of the code span are the characters between the two backtick strings, normalized in the following ways:

- First, line endings are converted to spaces.
- If the resulting string both begins *and* ends with a space character, but does not consist entirely of space characters, a single space character is removed from the front and back.  This allows you to include code that begins or ends with backtick characters, which must be separated by whitespace from the opening or closing backtick strings.
This is a simple code span:  

<Example :index="$page.frontmatter.start++"/>

Here two backticks are used, because the code contains a backtick.    
This example also illustrates stripping of a single leading and trailing space:    
<Example :index="$page.frontmatter.start++"/>

This example shows the motivation for stripping leading and trailing spaces:  
<Example :index="$page.frontmatter.start++"/>

Note that only *one* space is stripped:
<Example :index="$page.frontmatter.start++"/>

Only [spaces], and not [unicode whitespace] in general, are stripped in this way:
<Example :index="$page.frontmatter.start++"/>

No stripping occurs if the code span contains only spaces:
<Example :index="$page.frontmatter.start++"/>

[Line endings](https://github.github.com/gfm/#line-ending) are treated like spaces:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Interior spaces are not collapsed:    
<Example :index="$page.frontmatter.start++"/>

Note that browsers will typically collapse consecutive spaces when rendering `<code>` elements, so it is recommended that the following CSS be used:

    code{white-space: pre-wrap;}

Note that backslash escapes do not work in code spans. All backslashes are treated literally:  
<Example :index="$page.frontmatter.start++"/>

Backslash escapes are never needed, because one can always choose a string of _n_ backtick characters as delimiters, where the code does not contain any strings of exactly _n_ backtick characters. 

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>
 
Code span backticks have higher precedence than any other inline constructs except HTML tags and autolinks. Thus, for example, this is not parsed as emphasized text, since the second `*` is part of a code span:  
<Example :index="$page.frontmatter.start++"/>

And this is not parsed as a link:  
<Example :index="$page.frontmatter.start++"/>

Code spans, HTML tags, and autolinks have the same precedence. Thus, this is code:  
<Example :index="$page.frontmatter.start++"/>

But this is an HTML tag:  
<Example :index="$page.frontmatter.start++"/>

And this is code:  
<Example :index="$page.frontmatter.start++"/>

But this is an autolink:  
<Example :index="$page.frontmatter.start++"/>

When a backtick string is not closed by a matching backtick string, we just have literal backticks:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The following case also illustrates the need for opening and closing backtick strings to be equal in length:  
<Example :index="$page.frontmatter.start++"/>
