Render markdown on the CLI, with _pizzazz_!

[![Glow Logo](https://camo.githubusercontent.com/8c6b1d5dde709001a6c086d7b488dcca0b63bdfa8b9fc68c80efcfd99f0c108d/68747470733a2f2f73747566662e636861726d2e73682f676c6f772f676c6f772d62616e6e65722d6769746875622e676966)](https://camo.githubusercontent.com/8c6b1d5dde709001a6c086d7b488dcca0b63bdfa8b9fc68c80efcfd99f0c108d/68747470733a2f2f73747566662e636861726d2e73682f676c6f772f676c6f772d62616e6e65722d6769746875622e676966) [![Latest Release](https://camo.githubusercontent.com/ae995a959f6f2b411399dbc28d6422a291e38bbaf616014f1d7dd56a05650562/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f72656c656173652f636861726d62726163656c65742f676c6f772e737667)](https://github.com/charmbracelet/glow/releases) [![GoDoc](https://camo.githubusercontent.com/376f038517a929a7fb4143c5b2330fb56346bd235028a14276be41747d94c2d0/68747470733a2f2f676f646f632e6f72672f6769746875622e636f6d2f676f6c616e672f6764646f3f7374617475732e737667)](https://pkg.go.dev/github.com/charmbracelet/glow?tab=doc) [![Build Status](https://github.com/charmbracelet/glow/workflows/build/badge.svg)](https://github.com/charmbracelet/glow/actions) [![Go ReportCard](https://camo.githubusercontent.com/97d52b36fadf03b3cedabd8a489b095c96b4f304285107cddf106543f12acbcb/68747470733a2f2f676f7265706f7274636172642e636f6d2f62616467652f636861726d62726163656c65742f676c6f77)](https://goreportcard.com/report/github.com/charmbracelet/glow)

[![Glow UI Demo](https://camo.githubusercontent.com/bd591b74af8a6991894c8a84ab8d48f05ce7f66975b325d31f6954c836ddab27/68747470733a2f2f73747566662e636861726d2e73682f676c6f772f676c6f772d312e332d747261696c65722d6769746875622e676966)](https://camo.githubusercontent.com/bd591b74af8a6991894c8a84ab8d48f05ce7f66975b325d31f6954c836ddab27/68747470733a2f2f73747566662e636861726d2e73682f676c6f772f676c6f772d312e332d747261696c65722d6769746875622e676966)

## What is it?

Glow is a terminal based markdown reader designed from the ground up to bring out the beauty—and power—of the CLI.

Use it to discover markdown files, read documentation directly on the command line and stash markdown files to your own private collection so you can read them anywhere. Glow will find local markdown files in subdirectories or a local Git repository.

By the way, all data stashed is encrypted end-to-end: only you can decrypt it. More on that below.

## Installation

Use your fave package manager:

# macOS or Linux
brew install glow

# macOS (with MacPorts)
sudo port install glow

# Arch Linux (btw)
yay -S glow

# Void Linux
xbps-install -S glow

# Nix
nix-env -iA nixpkgs.glow

# FreeBSD
pkg install glow

# Solus
eopkg install glow

# Windows (with Scoop)
scoop install glow

# Android (with termux)
pkg install glow

Or download a binary from the [releases](https://github.com/charmbracelet/glow/releases) page. MacOS, Linux, Windows, FreeBSD, and OpenBSD binaries are available, as well as Debian, RPM, and Alpine packages. ARM builds are also available for macOS, Linux, FreeBSD, and OpenBSD.

Or just build it yourself (requires Go 1.13+):

git clone https://github.com/charmbracelet/glow.git
cd glow
go build

## The TUI

Simply run `glow` without arguments to start the textual user interface and browse local and stashed markdown. Glow will find local markdown files in the current directory and below or, if you’re in a Git repository, Glow will search the repo.

Markdown files can be read with Glow's high-performance pager. Most of the keystrokes you know from `less` are the same, but you can press `?` to list the hotkeys.

### Stashing

Glow works with the Charm Cloud to allow you to store any markdown files in your own private collection. You can stash a local document from the Glow TUI by pressing `s`.

Stashing is private, its contents will not be exposed publicly, and it's encrypted end-to-end. More on encryption below.

## The CLI

In addition to a TUI, Glow has a CLI for working with Markdown. To format a document use a markdown source as the primary argument:

# Read from file
glow README.md

# Read from stdin
glow -

# Fetch README from GitHub / GitLab
glow github.com/charmbracelet/glow

# Fetch markdown from HTTP
glow https://host.tld/file.md

### Stashing

You can also stash documents from the CLI:

Then, when you run `glow` without arguments will you can browse through your stashed documents. This is a great way to keep track of things that you need to reference often.

### Word Wrapping

The `-w` flag lets you set a maximum width at which the output will be wrapped:

### Paging

CLI output can be displayed in your preferred pager with the `-p` flag. This defaults to the ANSI-aware `less -r` if `$PAGER` is not explicitly set.

### Styles

You can choose a style with the `-s` flag. When no flag is provided `glow` tries to detect your terminal's current background color and automatically picks either the `dark` or the `light` style for you.

Alternatively you can also supply a custom JSON stylesheet:

For additional usage details see:

Check out the [Glamour Style Section](https://github.com/charmbracelet/glamour/blob/master/styles/gallery/README.md) to find more styles. Or [make your own](https://github.com/charmbracelet/glamour/tree/master/styles)!

## The Config File

If you find yourself supplying the same flags to `glow` all the time, it's probably a good idea to create a config file. Run `glow config`, which will open it in your favorite $EDITOR. Alternatively you can manually put a file named `glow.yml` in the default config path of you platform. If you're not sure where that is, please refer to `glow --help`.

Here's an example config:

# style name or JSON path (default "auto")
style: "light"
# show local files only; no network (TUI-mode only)
local: true
# mouse support (TUI-mode only)
mouse: true
# use pager to display markdown
pager: true
# word-wrap at width
width: 80

## 🔒 Encryption: How It Works

Encryption works by issuing symmetric keys (basically a generated password) and encrypting it with the local SSH public key generated by the open-source [charm](https://github.com/charmbracelet/charm) library. That encrypted key is then sent up to our server. We can’t read it since we don’t have your private key. When you want to decrypt something or view your stash, that key is downloaded from our server and decrypted locally using the SSH private key. When you link accounts, the symmetric key is encrypted for each new public key. This happens on your machine and not our server, so we never see any unencrypted data.

## License

[MIT](https://github.com/charmbracelet/glow/raw/master/LICENSE)

___

Part of [Charm](https://charm.sh/).

[![The Charm logo](https://camo.githubusercontent.com/fc3e8def2516f0ccb1334101489d1681866873c03599fbab9dd52ab5e0837a2c/68747470733a2f2f73747566662e636861726d2e73682f636861726d2d62616467652d756e726f756e6465642e6a7067)](https://charm.sh/)

Charm热爱开源 • Charm loves open source