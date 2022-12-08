---
created: 2022-08-07T22:11:38 (UTC -04:00)
tags: []
source: https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/
author: 
---

# Obsidian Github Publisher - Obsidian Mkdocs Publisher

---
[FR 🇫🇷](https://github.com/obsidianPublisher/obsidian-github-publisher/blob/master/docs/README_FR.md)

-   [What the plugin do](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#what-the-plugin-do)
-   [Configuration](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#configuration)
-   [Configuration example](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#configuration-example)
-   [GitHub](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#github)
-   [Download configuration](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#download-configuration)
    -   [Folder reception settings.](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#folder-reception-settings)
    -   [Metadata frontmatter](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#metadata-frontmatter)
    -   [Fixed folder](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#fixed-folder)
    -   [Obsidian Path](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#obsidian-path)
    -   [Workflow](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#workflow)
    -   [Auto clean-up](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#auto-clean-up)
    -   [Links’ conversion](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#links-conversion)
    -   [Index & folder note](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#index--folder-note)
    -   [Internal links](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#internal-links)
    -   [Wikilinks to markdown link](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#wikilinks-to-markdown-link)
    -   [Embed](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#embed)
-   [Plugin settings](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#plugin-settings)
-   [Developping](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#developping)
-   [General](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#general)
-   [Translation](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#translation)

GitHub Publisher is a plugin that help you to send file in a configured GitHub Repository, based on a front matter entry state.

You can use it to send any markdown file, allowing compatibility thought a lot of Obsidian Publish alternative.

When a shared file is found, it will be sent in a new branch named by `your_vault_name-month-day-year`. A pull request followed by a merge will be done, and if everything is okay, the branch will be deleted after the merge.  
Thus, you can easily revert commit, and create workflow based on PR, merged PR, specific push…

## What the plugin do[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#what-the-plugin-do "Permanent link")

-   Read the frontmatter to check the value of a configured `share` key.
-   Send the file (and their embedded image or notes if any) to a GitHub repository

But the plugin can do a lot more !

-   Convert wikilinks to markdown links (without changing your file)
-   Activate a GitHub action that have a `workflow_dispatche` event.
-   Convert internal’s links to match the configuration
-   Clean your repo with removing deleted and unshared files
-   Rename folder note with same name strategies with `index.md` (+ respecting the folder settings)
-   Send a link’s note in your clipboard after sharing.
-   Convert simple dataview query in markdown !

___

## Configuration[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#configuration "Permanent link")

To use the plugin, you need to fill the correct information to allow the workflow.

## Configuration example[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#configuration-example "Permanent link")

You will find [here](https://obsidian-publisher.netlify.appobsidian%20github%20publisher/Configuration%20example/) configuration example for some Obsidian Publish alternative, as Obsidian Mkdocs Publisher and [TuanManhCao Digital Garden](https://github.com/TuanManhCao/digital-garden).

Adding configuration

You can send me or do a pullrequest to add new configuration for any Obsidian **free** publish alternative.

-   Repo name: The repository where the files will be sent.
-   GitHub username: Your username.
-   GitHub Token: Get your [GitHub Token here](https://github.com/settings/tokens/new?scopes=repo)[2](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#fn:2). The correct settings should already be applied. If you want to avoid generating this every few months, select the “No expiration” option. Click the “Generate token” button, and copy the token you are presented with on the next page.

## Download configuration[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#download-configuration "Permanent link")

### Folder reception settings.[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#folder-reception-settings "Permanent link")

You have two options :

-   Use a “fixed” folder : Every file will be sent in this folder.
-   Use a folder created based on a `category` key.
-   Use the relative path from obsidian. You can prepend a folder using the default folder.

You need, in all case, to configure the **default folder** : The file will be sent here.

> If you use the option for frontmatter, this folder will be the default folder : the file will be sent here if the key doesn’t exist.

#### Metadata frontmatter[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#metadata-frontmatter "Permanent link")

Using the second option will activate two more options :

-   Front matter key: The key you want to use in your file.
-   Root folder : To prepend a path **before** the category key found (if any key are found!)

Example

-   You use `category` in a file with `category: Roleplay/Characters/DND`
-   You set a root folder with `_docs/pages`
-   And you set a default folder on `_docs/draft`

The final path (in GitHub!) will be : `_docs/pages/Roleplay/Characters/DND`

But, if you don’t set `category`, the path will be `_docs/draft`

#### Fixed folder[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#fixed-folder "Permanent link")

Every file will be sent in the default folder. If you leave the default folder blank, it will be sent in the root of the repository.

Example

-   If you set `source` for the default folder, any file will be sent in `your_repo/source`, whatever is their frontmatter key or their relative path.
-   If you leave it blank, it will be sent in `your_repo` directly.

#### Obsidian Path[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#obsidian-path "Permanent link")

It uses the relative path in your Obsidian vault. The default folder will be prepended before the relative obsidian path. You can leave it blank to use the root repository.

Example

For a file in `20. Compendium/DND/Monster`

-   If you set `source` : the final path will be `source/20. Compendium/DND/Monster`
-   If you leave the default folder blank, the final path will be `20. Compendium/DND/Monster`

The `path removing` allow you to remove part of the path created, to, for example, sync subfolder. If the removed path is not found, the normal behavior apply.

Sync subfolder

You can using this option to designate a subfolder as the “vault” for syncing the repository.  
You could plug in `vault/sub` as the path removed. The sync will flow `vault/sub` as `repo`.  
A file in `vault/sub/folderA` will be sync in `repo/folderA`

### Workflow[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#workflow "Permanent link")

If your workflow needs to activate a GitHub actions, set the name here.

Leave it blank to disable the GitHub actions activation.

#### Auto clean-up[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#auto-clean-up "Permanent link")

You can also set up an “auto-delete” when you use the commands to delete files:

-   Deleted from your vault
-   Which you have stopped sharing

This option will also add a new command to delete file (without sharing new file).

Warning[1](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#fn:1)

You can’t use the delete command if you don’t have set a default folder (and a root folder if you use the YAML configuration)  
Also, you can lost some files using this commands, so be careful! Don’t forget that you can revert commit in case the plugin delete a file you don’t want to delete.

Changing the option

In case you change the folder configuration, the precedent file won’t be deleted and result of a error of this workflow’s part. Be careful!

You can set the path of the folder you want to avoid deleting the file. Separate folders a comma.

Regex are not supported here!

Finally, to prevent deleting `index` created outside of obsidian, you could use some parameters in your front matter :

-   `autoclean: false`
-   `index: true`  
    Or removing the `share` key.

### Links’ conversion[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#links-conversion "Permanent link")

These settings won’t change your file’s content in your vault

#### Index & folder note[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#index-folder-note "Permanent link")

Some publishing solution support folder note, but these note need to be named `index`. In case you use [Folder Note](https://github.com/aidenlx/alx-folder-note) with [the `same name` strategies](https://github.com/aidenlx/alx-folder-note/wiki/folder-note-pref) you will have a problem, no? By chance, I have a solution for you, guys!  
Now, the plugin will convert these file into `index` if you activate the settings. Here some examples of renaming, using the different parameters from the default folder.  
Note : This option doesn’t work for Obsidian Path + Same name strategies **outside** of folder.

frontmatter example with a file named `folder2`

-   Using a category value : `folder1/folder2`
-   With root value named `docs` ⇒ `docs/folder1/folder2/index.md`
-   Without root : `folder1/folder2/index.md`
-   Without category value, with default folder named `drafts` : `draft/folder2.md` (the name won’t be converted!)

Example with Obsidian Path & a file named `folder2`

With a path like : `folder1/folder2` the new path will be :

-   If you use a default folder named `docs` : `docs/folder1/folder2/index.md`
-   Without : `folder1/folder2/index.md`

This option doesn’t work with fixed folder.

#### Internal links[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#internal-links "Permanent link")

This option will convert the internal links (including image links!) of the shared file to match the relative file in your repo. Only **existant** and **shared** file will be converted.

Example

Cited file : `docs/XX/YY/my_file.md`  
File to convert : `docs/XX/ZZ/new_file.md`  
Path created : `../YY/my_file.md`

#### Wikilinks to markdown link[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#wikilinks-to-markdown-link "Permanent link")

In case you use wikilinks as daily but your obsidian publish solution doesn’t support it, you can use this settings to convert the wiki to md link.

### Embed[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#embed "Permanent link")

You can choose to send embeded files :

-   Images : The image will be copied in the repository in an optionnaly settled folder.
-   Notes : Only shared files will be copied in the repository, in their respected folder (following your settings).

## Plugin settings[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#plugin-settings "Permanent link")

You can configure :

-   The share key used by the plugin. By default, it is `share`
-   Folder excluded. The share key can’t work here. Useful if you forget to remove the `share` (or turn it to `false`) and move a file in your archive…
-   Add the command to share the file on the file menu (right-click on a file in the explorer or using the three dot) and editor menu (right-click on an opened edited note)
-   Added the link’s shared note in your clipboard after sharing. You can configure the path created here, with removing some part. As it supports multiple part, you can separate the part using comma. For example, you can remove docs and the extension using : `docs/, .md`

The right-click menu command can also send the file under your cursor if it’s a link!

___

## Developping[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#developping "Permanent link")

## General[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#general "Permanent link")

You can help me to develop the plugin using `npm` !

1.  First clone the project on your computer with `git clone git@github.com:obsidianPublisher/obsidian-github-publisher.git`
2.  `cd obsidian-github-publisher`
3.  `npm install`
4.  Enjoy!

Some notes:

-   I use [Conventional Commit](https://www.conventionalcommits.org/en/v1.0.0/) to generate the commit message, so please respect the format!
-   To forget to documents your function!

## Translation[¶](https://obsidian-publisher.netlify.app/obsidian%20github%20publisher/#translation "Permanent link")

Using [i18n](https://www.i18next.com/), you can translate the plugin.

To add a new language :

-   Clone the `i18n/locales/en-us.ts` and rename it to your langage.
-   Get your locale language from Obsidian using [obsidian translation](https://github.com/obsidianmd/obsidian-translations) or using the commands (in templater for example) : `<% tp.obsidian.moment.locale() %>`
-   Translate the file and save it.
-   In `i18n/index.ts` :
-   Import the new file as `import language from ‘.locales/language’
-   add the new language in the `localeMap` json object: `{ "language": language }`
-   Additionnaly, you can test if your translation is okay.
-   Create a PR to add your translation!

___

If you find this plugin and workflow useful, you can give me some coffee money.  
[![Buy Me a Coffee at ko-fi.com](https://cdn.ko-fi.com/cdn/kofi1.png?v=3)](https://ko-fi.com/X8X54ZYAV)
