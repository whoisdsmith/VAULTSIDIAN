{{($page.frontmatter.start = 491) ? null : null}}
### Strikethrough (extension)

GFM enables the `strikethrough` extension, where an additional emphasis type is available.  
Strikethrough text is any text wrapped in two tildes (`~`).  
<Example :index="$page.frontmatter.start++"/>

As with regular emphasis delimiters, a new paragraph will cause strikethrough parsing to cease:  
<Example :index="$page.frontmatter.start++"/>
