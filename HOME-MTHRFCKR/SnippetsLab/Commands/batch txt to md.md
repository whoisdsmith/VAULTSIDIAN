---
created: 2022-01-19T22:11:59Z
folder: Commands
modified: 2022-01-19T22:12:43Z
notes: txt to md
tags: pandoc, txt to md
title: batch txt to md
---

# batch txt to md

find . -name \*.txt -type f -exec pandoc -o {}.md {} \;
