{{($page.frontmatter.start = 279) ? null : null}}
### Task list items (extension)

GFM enables the `tasklist` extension, where an additional processing step is performed on [list items](https://github.github.com/gfm/#list-items).  
A [task list item](https://github.github.com/gfm/#task-list-item) is a [list item](https://github.github.com/gfm/#list-items) where the first block in it is a paragraph which begins with a [task list item marker](https://github.github.com/gfm/#task-list-item-marker) and at least one whitespace character before any other content.  
A [task list item marker](https://github.github.com/gfm/#task-list-item-marker) consists of an optional number of spaces, a left bracket (`[`), either a whitespace character or the letter `x` in either lowercase or uppercase, and then a right bracket (`]`).  
When rendered, the [task list item marker](https://github.github.com/gfm/#task-list-item-marker) is replaced with a semantic checkbox element; in an HTML output, this would be an `<input type="checkbox">` element.  
If the character between the brackets is a whitespace character, the checkbox is unchecked. Otherwise, the checkbox is checked.  
This spec does not define how the checkbox elements are interacted with: in practice, implementors are free to render the checkboxes as disabled or inmutable elements, or they may dynamically handle dynamic interactions (i.e. checking, unchecking) in the final rendered document.  
<Example :index="$page.frontmatter.start++"/>

Task lists can be arbitrarily nested:  
<Example :index="$page.frontmatter.start++"/>
