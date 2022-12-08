---
created: 2022-08-07T22:02:29 (UTC -04:00)
tags: []
source: chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html
author: 
---

# Publish and GitHub URL plugin

---
This plugin adds a command which lets you copy the URL of a note for your Obsidian Publish site.

Optionally, as of v0.2.0, you can also enable a file menu entry. Thank you to [@Mara-Li](https://github.com/Mara-Li) for the contribution.

It doesn't copy the URL (or show the file menu entry) if the `publish` flag is set to `false`.

As of v0.3.0, you can also open the current note on the published site directly in your browser. This feature is enabled by default.

As of v0.4.0, you can open the current note's Git commit history on GitHub. It is turned off by default. You need to set the repository URL and the branch name for it to work.

### [](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#configuration)Configuration

In the settings, you need to set your Publish `Index` note and also the base path of your Obsidian Publish site.
