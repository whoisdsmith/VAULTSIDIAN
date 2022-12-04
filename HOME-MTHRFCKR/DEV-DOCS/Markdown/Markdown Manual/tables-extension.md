{{($page.frontmatter.start = 198) ? null : null}}
### Tables (extension)

GFM enables the `table` extension, where an additional leaf block type is available.  

A [table](https://github.github.com/gfm/#table) is an arrangement of data with rows and columns, consisting of a single header row, a [delimiter row](https://github.github.com/gfm/#delimiter-row)separating the header from the data, and zero or more data rows.  

Each row consists of cells containing arbitrary text, in which [inlines](https://github.github.com/gfm/#inlines) are parsed, separated by pipes (`|`). A leading and trailing pipe is also recommended for clarity of reading, and if there’s otherwise parsing ambiguity. Spaces between pipes and cell content are trimmed. Block-level elements cannot be inserted in a table.  

The [delimiter row](https://github.github.com/gfm/#delimiter-row) consists of cells whose only content are hyphens (`-`), and optionally, a leading or trailing colon (`:`), or both, to indicate left, right, or center alignment respectively.  
<Example :index="$page.frontmatter.start++"/>

Cells in one column don’t need to match length, though it’s easier to read if they are. Likewise, use of leading and trailing pipes may be inconsistent:  
<Example :index="$page.frontmatter.start++"/>

Include a pipe in a cell’s content by escaping it, including inside other inline spans:  
<Example :index="$page.frontmatter.start++"/>

The table is broken at the first empty line, or beginning of another block-level structure:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

The header row must match the [delimiter row](https://github.github.com/gfm/#delimiter-row) in the number of cells. If not, a table will not be recognized:  
<Example :index="$page.frontmatter.start++"/>

The remainder of the table’s rows may vary in the number of cells. If there are a number of cells fewer than the number of cells in the header row, empty cells are inserted. If there are greater, the excess is ignored:  
<Example :index="$page.frontmatter.start++"/>

If there are no rows in the body, no `<tbody>` is generated in HTML output:  
<Example :index="$page.frontmatter.start++"/>
