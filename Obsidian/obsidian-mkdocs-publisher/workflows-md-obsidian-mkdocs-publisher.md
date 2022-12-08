---
created: 2022-08-07T22:13:10 (UTC -04:00)
tags: []
source: https://obsidian-publisher.netlify.app/python/workflows/
author: 
---

# Workflows.md - Obsidian Mkdocs Publisher

---
## On push[¶](https://obsidian-publisher.netlify.app/python/workflows/#on-push "Permanent link")

The main workflow is in `ci.yml` . **It needs a push event where the commit name starts with `[PUBLISHER]`**. After that, it will scan the repository and try to find modified file (since the last commit). After find these file, it will convert it using obs2mk, and build the mkdocs site.

## Manual run[¶](https://obsidian-publisher.netlify.app/python/workflows/#manual-run "Permanent link")

You can also run manually the convertor using `Publisher Manual` (in the `manual_run.yml`).

Tutorial to manually trigger the workflow using Github.com

1.  First, go to _Actions_
2.  You will see the list of the actions on your repository. Click on **publisher manual**.
3.  Click on **run workflow**
4.  The run ask you for the file(s) you want to convert. You can convert multiple files using a [glob pattern](https://en.wikipedia.org/wiki/Glob_(programming)), like a folder or commune name. Each markdown file found will be converted by `obs2mk`.  
    ![../assets/img/demo.gif](https://obsidian-publisher.netlify.app/assets/img/demo.gif "../assets/img/demo.gif")

Note that you can also trigger the workflow using [Github CLI](https://cli.github.com/) using `gh workflow run manual_run.yml file=your_file`

If you want to have the last message with your mkdocs page, you need to edit the `.github/env.txt` with the link to your page.
