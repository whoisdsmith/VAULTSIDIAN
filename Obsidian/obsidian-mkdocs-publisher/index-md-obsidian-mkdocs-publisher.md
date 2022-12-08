---
created: 2022-08-07T22:13:02 (UTC -04:00)
tags: []
source: https://obsidian-publisher.netlify.app/python/
author: 
---

# Index.md - Obsidian Mkdocs Publisher

---
The script’s goal is to move an authorized file (or multiple authorized file) from your Obsidian’s vault to your blog’s repository. It will :

-   Move linked image in `docs/assets/img`
-   Convert the **code block** [Admonition](https://github.com/valentine195/obsidian-admonition) to [material Admonition](https://squidfunk.github.io/mkdocs-material/reference/admonitions/)[1](https://obsidian-publisher.netlify.app/python/#fn:1)
-   Convert the [Callout Syntax](https://help.obsidian.md/How+to/Use+callouts) to [material Admonition](https://squidfunk.github.io/mkdocs-material/reference/admonitions/)[2](https://obsidian-publisher.netlify.app/python/#fn:2)
-   Remove Obsidian’s comments as ``
-   Copy the file in `docs` or a specific folder structure.
-   Add custom CSS based on [markdown attribute or tags](https://obsidian-publisher.netlify.app/Template/customization/#custom-attribute "markdown attribute or tags") ([CM6 Live Preview](https://github.com/nothingislost/obsidian-cm6-attributes) ; [Markdown Attribute](https://github.com/valentine195/obsidian-markdown-attributes) and [Contextual Typography](https://github.com/mgmeyers/obsidian-contextual-typography)).

Furthermore, it will also carry :

-   Of the support of [Folder Note — Pagination Indexes](https://obsidian-publisher.netlify.app/Template/customization/#folder-note "Folder Note — Pagination Indexes")
-   Copy a link to the blog converted file (only if one file is converted)
