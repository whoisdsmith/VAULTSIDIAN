---
created: 2022-01-14T09:35:52 (UTC -05:00)
tags: []
source: https://devhints.io/applescript
author: 
---

# AppleScript cheatsheet

> ## Excerpt
> The one-page guide to AppleScript: usage, examples, links, snippets, and more.

---
# AppleScript _cheatsheet_

### Running

```applescript
osascript -e "..."
```

```applescript
display notification "X" with title "Y"
```

### Comments

```applescript
-- This is a single line comment
```

```applescript
# This is another single line comment
```

```applescript
(*
This is
a multi
line comment
*)
```

### Say

```applescript
-- default voice
say "Hi I am a Mac"
```

```applescript
-- specified voice
say "Hi I am a Mac" using "Zarvox"
```

### Beep

```applescript
-- beep once
beep
```

```applescript
-- beep 10 times
beep 10
```

### Delay

```applescript
-- delay for 5 seconds
delay 5
```
