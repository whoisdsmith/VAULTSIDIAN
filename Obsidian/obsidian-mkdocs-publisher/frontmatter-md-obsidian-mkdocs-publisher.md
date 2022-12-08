---
created: 2022-08-07T22:12:18 (UTC -04:00)
tags: []
source: https://obsidian-publisher.netlify.app/python/frontmatter/
author: 
---

# Frontmatter.md - Obsidian Mkdocs Publisher

---
The script relies on the front matter of the notes you want to publish.

1.  `share: true` allow publishing the file[1](https://obsidian-publisher.netlify.app/python/frontmatter/#fn:1)
2.  `category`[1](https://obsidian-publisher.netlify.app/python/frontmatter/#fn:1) to choose where the file will be after conversion ; allowing categorization for the blog.[2](https://obsidian-publisher.netlify.app/python/frontmatter/#fn:2)
    -   `category: false` will **hide** the file from navigation.
    -   `category: hidden` will do the same.
    -   `category: folder1/folder2/` will move the file in `folder2`, under `folder1`
    -   `category: folder1/folder2/filename` will rename the file `index` and allow support of [section’s index page](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#section-index-pages)
3.  `update: false` prevent to update the file after the first publication
4.  `description` : Add a description to the file (for meta-tag sharing)[3](https://obsidian-publisher.netlify.app/python/frontmatter/#fn:3)
5.  `title` : Change the title in the navigation.
6.  `image` : Add an image for meta-tags sharing.[3](https://obsidian-publisher.netlify.app/python/frontmatter/#fn:3) It needs to be the name of the file, as `image.png`.
