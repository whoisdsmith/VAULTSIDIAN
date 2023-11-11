# Bare Bones Software | Regarding Environment Variables when Using “zsh”

---

## Regarding Environment Variables when Using “zsh”

If you find that BBEdit is unable to locate commands that you are able to use in Terminal; or if you find that these commands are available but behave unexpectedly, it's likely that your shell environment needs to be adjusted so that your customizations are visible to BBEdit. (This applies to [language servers](http://www.barebones.com/support/bbedit/lsp-notes.html) as well as commands such as `git` and `svn` that BBEdit uses to support built-in features.)

When using `zsh`, a common mistake is to configure `$PATH` and other environment variables in `~/.zshrc`. However, `zsh` only loads `~/.zshrc` when running an interactive shell. Because BBEdit runs `zsh` as a non-interactive shell, `zsh` does not load `~/.zshrc`, and BBEdit never gets your desired environment.

However, if you move `$PATH` (and other environment settings) into `~/.zshenv`, `zsh` will load this (in BBEdit as well as in Terminal).

Note that you can *also* use `~/.zprofile`, since BBEdit runs `zsh` as a login shell to determine the appropriate environment.

A detailed description of the configuration files that `zsh` uses can be found in [sections 5.1 and 5.2 of the zsh documentation](https://zsh.sourceforge.io/Doc/Release/Files.html).

---

[Back to Technical Notes](http://www.barebones.com/support/bbedit/technotes.html)
