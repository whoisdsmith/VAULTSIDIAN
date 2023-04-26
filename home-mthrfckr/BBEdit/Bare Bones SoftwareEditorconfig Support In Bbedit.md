# Bare Bones Software | EditorConfig Support in BBEdit

---

Beginning with BBEdit 11.1, support for [EditorConfig](http://www.editorconfig.org/) is built in to BBEdit. This document does not attempt to educate about EditorConfig basics; those are thoroughly covered on the EditorConfig web site. However, there are some variances from the core in BBEdit's support, and those are documented here.

### Relationship of EditorConfig to application settings and document state

EditorConfig settings, if present, will *always* override any application settings (including language-specific settings) or document state. This is as it should be, since the goal of EditorConfig is to help ensure consistency of document settings within a project.

### Core property support

BBEdit supports most of the core EditorConfig properties [listed here](https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties). The `end_of_line` property is not supported; nor is `max_line_length`.

### Emacs-derived properties

In addition to the core EditorConfig properties, there are some BBEdit-specific additions. First, BBEdit supports the following keys originating in Emacs:

-   `coding`: similar to `charset`, but allows you to specify any IANA character set name.
    
-   `mode`: allows you to explicitly specify the language. Many of the Emacs-style mode names work, as long as they correspond to supported languages in BBEdit. In addition, any installed language in BBEdit may be expressed as a mode name by lowercasing its name and replacing spaces with dashes. For example, "Ruby in HTML" becomes `ruby-in-html`; or "Strings File" becomes `strings-file`.
    
-   `make-backup-files`: set to `1` or `0`, determines whether BBEdit makes a backup of the file when saving.
    
-   `backup-inhibited`: if present and set to `1`, will explicitly suppress the creation of backup files when saving.
    

### BBEdit-specific properties

Finally, there are some keys which are explicitly BBEdit-specific. All of these keys have names that begin with `x-` in order to prevent collisions with any future core keys. These correspond directly to individual document settings. As noted above, any of these keys will override the global preferences or document state.

-   `x-typographers-quotes`: Use Typographer's Quotes
-   `x-balance-while-typing`: Balance While Typing
-   `x-soft-wrap-text`: Soft Wrap Text
-   `x-soft-wrap-mode`: (string) Must be one of `CharacterWidth`, `WindowWidth`, or `PageGuide`
-   `x-soft-wrap-limit`: (integer) if the wrap mode is `CharacterWidth`, specifies the number of characters
-   `x-font-name`: (string) the display font name
-   `x-font-size`: (integer) the display font point size
-   `x-show-invisibles`: Show Invisibles
-   `x-show-spaces`: Show Spaces

Unless otherwise noted, these application-specific keys are all Boolean flags.

---

[Back to Technical Notes](http://www.barebones.com/support/bbedit/technotes.html)
