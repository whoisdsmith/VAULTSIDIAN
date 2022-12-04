# Using Warp with \[zsh|bash|fish\]

Warp currently supports popular existing shells like Bash, Zsh, and Fish. If your default shell is set to any other shell, you would see a banner notifying you that the shell is not supported, and Warp will fall back to Zsh.

## Zsh is the Default Shell for Warp

Zsh is the default login and interactive shell on macOS (starting with macOS Catalina in 2019), replacing Bash shell which. Warp tries to load your login shell by default, currently we support Bash, Fish, and Zsh; if your login shell is set to something else e.g. Nushell Warp will load Zsh instead.

You can switch your default shell to any other shell supported by Warp (Bash, Zsh, Fish).

[Zsh

(https://zsh.sourceforge.io/Doc/Release/zsh_toc.html) is a Unix shell built as an extension of [Bourne shell]

(https://en.wikipedia.org/wiki/Bourne_shell) with many improvements around customization e.g. support for plugins, themes, syntax highlighting, and auto-correction..

### Setting up Zsh on Warp

By default, macOS ships with Zsh located in `/bin/zsh`. You can confirm this location by typing `which zsh` in your Warp terminal. You can also check the version of Zsh installed on your system by simply typing the following:

`$ zsh --version`

### Customize Your Zsh Shell Environment

You can customize your Zsh shell environment by modifying the `.zshrc` file, which is a configuration file that is automatically created when Zsh is installed in your system. It is typically located your home directory (`~/.zshrc`).

You can think of the `zshrc` file as a startup file that gets executed when a new instance of Zsh is launched (new window, new tab/pane etc.)

You can use the `.zshrc` file to customize behavior like: setting environment variables, adding aliases, changing the [prompt](https://docs.warp.dev/features/prompt), and more. It can also be used to set up key-bindings, and scripts that will automatically execute when a new instance of Zsh is launched.

### Editing the .zshrc File

The `.zshrc` file is located in the home directory, and can be opened with any text editor.

Note that the dot (`.`) before the file’s name indicates that the file is hidden, (it) won’t be visible by default, and may not show up in Finder (press `SHIFT-CMD-.` to show hidden files in Finder). You can edit the file from the terminal by typing `nano ~/.zshrc` or `vi ~/.zshrc`.

![](https://lh5.googleusercontent.com/z6kqYKxNMDMLSbhIO0nps7EXb5zXt3NeOJ7cto2C4NXd6-LIOsXSyL0hBpIjaV9mJ8wG0HgcZygjn7zHmljEI11xeX8FBAWRtOR221QaMghRepqc4Pnwqp4mdh2CBWYrqqE5TPmODdJg7go0E2ocCBtQ71Ok0qYPy6o6xLhbAr0yAb-ukk_SZuf0iQ)

### Reloading the Zshrc File After Making Changes to it

When you make a change to the `zshrc` file, it needs to be reloaded or sourced again for the changes to take effect. You can do this by either restarting Warp, or by typing: `source ~/.zshrc`.

---
