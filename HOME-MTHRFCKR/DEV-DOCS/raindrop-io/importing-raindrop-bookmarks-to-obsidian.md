
# Importing Raindrop.io bookmarks into Obsidian

1 min (301 words)

There have been previous articles and videos suggesting using Raindrop.io as a means to manage bookmarks (what they call "Raindrops") for the purposes of managing web content, and then later importing it into Obsidian. I found the process of importing these things to be rather tedious, first starting with a script to read the exported text files, debating about migrating that to using the exported CSV files (which I dismissed due to the irritations of dealing with CSVs), and then finally discovered that Raindrop has an API for pulling content which can be integrated into [Templater](https://github.com/SilentVoid13/Templater). Hopefully this is useful to others, and maybe someone might want to create a plugin out of it.

Here's what you'll need: - [Raindrop.js Script](https://gist.github.com/Mezner/896b49db4f29eed1fa739c146f8b0c09#file-raindrop-js) - [Sample Templater Template, which uses the script](https://gist.github.com/Mezner/896b49db4f29eed1fa739c146f8b0c09#file-raindroptemplatertemplate) - Getting Started with Templater Scripts Guide: [how-to-use-templater-js-scripts - shabegom's Obsidian Tutorials](https://shbgm.ca/obsidian/docs/how-to-use-templater-js-scripts)

To use it, you'll need to: 1. Follow the general guide to setup Templater with Scripts 2. Create an application and test token, updating the Raindrop.js Script with the value that's specific to you. 3. Create a template that uses it or use the sample template above. 4. Create a new note using Templater, and you should have Templater UI that shows you items from your Raindrop account!

My sample template creates Obsidian callouts that have well-ordered block link names for later use in embedding in other notes should I choose to do so. This can be far simpler if you'd like or more complex. For example, the raindrop you get back has [other pieces of information](https://developer.raindrop.io/v1/raindrops) associated with it that you can use in your templates, like the excerpt, type, or associated media to visualize your raindrop.

-   [Templater](https://github.com/SilentVoid13/Templater)
-   [Raindrop.js Script](https://gist.github.com/Mezner/896b49db4f29eed1fa739c146f8b0c09#file-raindrop-js)
-   [Sample Templater Template, which uses the script](https://gist.github.com/Mezner/896b49db4f29eed1fa739c146f8b0c09#file-raindroptemplatertemplate)
-   [how-to-use-templater-js-scripts - shabegom's Obsidian Tutorials](https://shbgm.ca/obsidian/docs/how-to-use-templater-js-scripts)
-   [other pieces of information](https://developer.raindrop.io/v1/raindrops)
