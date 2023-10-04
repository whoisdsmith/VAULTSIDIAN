---
title: Obsidian Broken Links Plug-in
datetimeCreate: 2023-10-04 12:46:15
datetimeUpdate: 2023-10-04 12:52:25
---
## USER
Create a plug-in for obsidian that will check for broken links in a vault

## ASSISTANT
Creating a plug-in for Obsidian to check for broken links requires writing code in JavaScript, as Obsidian is built on the Electron framework which uses web technologies. Here is a basic outline of how you can create such a plug-in:

1. Set up the plug-in structure:
   - Create a new folder in your Obsidian vault's `.obsidian/plugins/` directory with a name like `broken-links-checker`.
   - Inside the folder, create a `main.js` file that will contain the plug-in's code, and a `manifest.json` file to store the plug-in's metadata.

2. Create the `manifest.json` file with the following content:
```json
{
  "id": "broken-links-checker",
  "name": "Broken Links Checker",
  "description": "A plug-in for Obsidian to check for broken links in a vault",
  "version": "0.1.0",
  "author": "Your Name",
  "minAppVersion": "0.12.0",
  "main": "main.js"
}
```

3. Write the code for the plug-in in the `main.js` file:
```javascript
const { Plugin } = require('obsidian');

class BrokenLinksChecker extends Plugin {
  async onload() {
    this.addCommand({
      id: 'check-broken-links',
      name: 'Check for broken links',
      callback: () => this.checkForBrokenLinks(),
    });
  }

  async checkForBrokenLinks() {
    const brokenLinks = new Map();
    const files = this.app.vault.getMarkdownFiles();

    for (const file of files) {
      const content = await this.app.vault.read(file);
      const links = this.extractLinks(content);

      for (const link of links) {
        if (!(await this.isLinkValid(link))) {
          if (!brokenLinks.has(file.path)) {
            brokenLinks.set(file.path, []);
          }
          brokenLinks.get(file.path).push(link);
        }
      }
    }

    this.showBrokenLinks(brokenLinks);
  }

  extractLinks(content) {
    const linkRegex = /\[\[([^|\]]+)(?:\|[^|\]]+)?\]\]/g;
    const links = [];
    let match;

    while ((match = linkRegex.exec(content))) {
      links.push(match[1]);
    }

    return links;
  }

  async isLinkValid(link) {
    const file = this.app.metadataCache.getFirstLinkpathDest(link, '');
    return !!file;
  }

  showBrokenLinks(brokenLinks) {
    let message = '';

    if (brokenLinks.size === 0) {
      message = 'No broken links found.';
    } else {
      message = 'Broken links found:\n\n';

      for (const [file, links] of brokenLinks.entries()) {
        message += `- ${file}:\n  - ${links.join('\n  - ')}\n`;
      }
    }

    new Notice(message);
  }
}

module.exports = BrokenLinksChecker;
```

4. Install the plug-in:
   - Restart Obsidian.
   - Go to Settings > Community Plugins.
   - Click on "Load local plugin" and select the `broken-links-checker` folder.
   - Enable the "Broken Links Checker" plug-in.

Now you should be able to use the "Check for broken links" command in Obsidian, which will display a notice with the list of broken links found in your vault.

## USER
Adding to this I would like the plug-in create a new markdown file that lists any broken links

## ASSISTANT
To modify the plug-in to create a new markdown file that lists the broken links, you can update the `showBrokenLinks` method in the `main.js` file as follows:

```javascript
// Replace this method in the existing code
async showBrokenLinks(brokenLinks) {
  let content = '';

  if (brokenLinks.size === 0) {
    content = 'No broken links found.\n';
  } else {
    content = '# Broken Links Report\n\n';

    for (const [file, links] of brokenLinks.entries()) {
      content += `- [${file}](${encodeURI(file)}):\n  - ${links.map(link => `[${link}](${encodeURI(link)})`).join('\n  - ')}\n`;
    }
  }

  // Create or update the broken links markdown file
  const brokenLinksFile = await this.getOrCreateBrokenLinksFile();
  await this.app.vault.modify(brokenLinksFile, content);

  // Show a notice that the broken links file has been updated
  new Notice('Broken Links Report has been updated.');
}

// Add this new method to the existing code
async getOrCreateBrokenLinksFile() {
  const fileName = 'Broken Links Report.md';
  let brokenLinksFile = this.app.vault.getAbstractFileByPath(fileName);

  if (!brokenLinksFile) {
    brokenLinksFile = await this.app.vault.create(fileName);
  }

  return brokenLinksFile;
}
```

These changes will make the plug-in create a new markdown file named "Broken Links Report.md" in your vault, or update it if it already exists. The file will contain a list of broken links, with each link pointing to the file containing the broken link.

After making these changes, restart Obsidian and ensure the "Broken Links Checker" plug-in is enabled. Now, when you run the "Check for broken links" command, the plug-in will create or update the "Broken Links Report.md" file with the list of broken links found in your vault.