---
created: 2022-01-19T22:10:36Z
folder: Commands
modified: 2022-01-19T22:10:52Z
notes: htm to md
tags: pandoc, htm to md
title: Batch htm to md
---

# Batch Htm to Md

find . -name \*.htm -type f -exec pandoc -o {}.md {} \;
