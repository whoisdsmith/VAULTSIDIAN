---
created: 2022-01-19T21:55:33Z
folder: Commands
modified: 2022-01-19T22:11:56Z
notes: html to md
tags: html to md
title: batch html to md
---

# batch html to md

find . -name \*.html -type f -exec pandoc -o {}.md {} \;
