# Org Mode cheatsheet

> ## Excerpt
> One-page guide to Org Mode: usage, examples, and more. Org mode is for keeping hierarchal notes (and more) in Emacs.

---
# Org Mode _cheatsheet_

This page is a work in progress. You can help by [suggesting edits](https://github.com/rstacruz/cheatsheets/blob/master/org-mode.md)!

[Org mode](https://orgmode.org/) is for keeping hierarchal notes (and more) in Emacs.

## [#](https://devhints.io/org-mode#syntax)Syntax

### Headings

```org
* Welcome to Org mode

  Lines starting with * are headings.
  These lines without are notes.

** Sub-heading

   Two stars mark a 2nd-level subheading (h2).
```

### Lists

```org
* Lists

To buy:
1. Milk
2. Eggs
   - Organic
3. Cheese
   + Parmesan
   + Mozarella
```

### Inline styles

```org
*bold*
/italic/
_underline_
=verbatim=
~code~
+strike-through+
```

### To do

```org
* TODO buy airplane
```

Cycle by using `S-LEFT` / `S-RIGHT`. List all TODO’s via `C-c C-v`.

## [#](https://devhints.io/org-mode#shortcuts)Shortcuts

### Basic shortcuts

Description

Shortcut

(Un) fold

`TAB` / `S-TAB`

Move up

`M-UP` / `M-DOWN`

New headline

`M-RET`

Cycle workflow

`S-LEFT` / `S-RIGHT`

Cycle priority

`S-UP` / `S-DOWN`

### Timer

Description

Shortcut

Start timer

`C-c` `C-x` `0`

Stop timer

`C-c` `C-x` `_`

Pause timer

`C-c` `C-x` `,`

Start countdown

`C-c` `C-x` `;`

You can use this for Pomodoro!

### Agenda

Description

Shortcut

Agenda menu

`C-c` `a`

Add document

`C-c` `[`

Remove document

`C-c` `]`

Add date

`C-c` `.`

Add time & date

`C-u` `C-c` `.`

Start by adding the current file to the agenda (`C-c [`), then use the agenda menu to navigate.

### Export

Description

Shortcut

Export menu

`C-c` `C-e`

Lets you export the document as Markdown, HTML, and others.
