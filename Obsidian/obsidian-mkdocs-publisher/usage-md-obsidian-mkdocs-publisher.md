---
created: 2022-08-07T22:12:06 (UTC -04:00)
tags: []
source: https://obsidian-publisher.netlify.app/python/usage/
author: 
---

# Usage.md - Obsidian Mkdocs Publisher

---
The script can be use :

-   Directly in Obsidian, using [Obsidian Shell Commands](https://github.com/Taitava/obsidian-shellcommands) (see [Obsidian shell configuration](https://obsidian-publisher.netlify.appdocumentation/obs2mk/obsidian%20shell/) )
-   In a [terminal](https://obsidian-publisher.netlify.app/python/usage/#commands).

The supported system are :

-   macOS, Linux and Windows
-   [IOS](https://mara-li.github.io/obsidian_mkdocs_publisher_docs/documentation/obs2mk/ios/) (with [Pyto](https://pyto.app/) and/or [a-shell](https://holzschu.github.io/a-Shell_iOS/) with [Working Copy](https://workingcopyapp.com/))

## Script’s Configuration[¶](https://obsidian-publisher.netlify.app/python/usage/#scripts-configuration "Permanent link")

At the first run, you will be asked to configure some key and specific path.

1.  Vault : Use the file dialog to choose your vault folder.
2.  Publish repository folder : As vault path, use the file dialog.
3.  share : You can change the `share` key. By default, it’s `share`
4.  Index key: Support for citation of [pagination index pages](https://obsidian-publisher.netlify.app/Template/customization/#folder-note "pagination index pages"). By default, it uses `(i)`
5.  Default blog folder: By default, the notes will be in `docs/notes` but you can change that, or use `/` for root.

## Commands[¶](https://obsidian-publisher.netlify.app/python/usage/#commands "Permanent link")

Global options :

-   `--git` : No commit and push to git ;
-   `--mobile` : Use mobile shortcuts instead of `--git`
-   `--meta` : Update frontmatter of source files
-   `--keep` : Don’t delete files in blog folder
-   `--shell` : Remove Rich printing

Commands and specific options :

-   **config** : (_it will ignore `--use configuration_name`_)
    -   `--new configuration_name` : Create a specific configuration for some files
-   **all** : Share all vault
    -   `--force` : Force updating (ignore the difference between the source and blog file)
    -   `--vault` : Share all vault file, ignoring the share state.
-   **`file [file]`** : Share only one file

```
usage: __main__.py [-h] [--mobile | --git] [--meta] [--keep] [--use configuration_name] {config,all,file} ...

positional arguments:
  {config,all,file}
    config              Configure the script : Add or edit your vault and blog absolute path, change some keys.
    all                 Publish multiple files
    file                Publish only one file

options:
  -h, --help            show this help message and exit
  --mobile, --shortcuts
                        Use mobile shortcuts, without push
  --git, --g, --G       No commit and no push to git
  --meta, --m, --M      Update the frontmatter of the source file, adding the note blog's link
  --keep, --k, --K      Keep deleted file from vault and removed shared file
  --use configuration_name, --config configuration_name
                        Use a different config from default

```

The commands order is :  
`obs2mk (global_options) [all|config|file FILEPATH] (specific_options)`

Where :

-   Global and specific options are optional
-   `all`, `config` and `file`[1](https://obsidian-publisher.netlify.app/python/usage/#fn:1) are required  
    You can use the command without argument with `obs2mk` to share every `share: true` file in your vault.

It will :

-   Update the `share` state in original file
-   Convert one file, regardless of what is the `share` state.

You can share multiple documents at once with scanning your Vault, looking for the `share: true`. It will convert automatically these files.  
Only file with modification since the last sharing will be updated.

You can :

-   Share entirely your vault (that’s ignore the `share` state) with : `obs2mk all --vault`
-   Ignore the difference between the source file and the blog’s file with : `obs2mk all --force`  
    Also, you can combine the two options.

## Multiple configurations[¶](https://obsidian-publisher.netlify.app/python/usage/#multiple-configurations "Permanent link")

You can use and create multiple configuration files. This allows to have multiple site based on one vault, or different vault accross one site…

1.  To create a new configuration file : `obs2mk config --new configuration_name`
2.  To use a configuration use : `--use configuration_name`  
    For example : `obs2mk --use configuration_name`

See [configuration template](https://obsidian-publisher.netlify.app/python/configuration%20template/) for more information about the configuration file.

___

## Navigation[¶](https://obsidian-publisher.netlify.app/python/usage/#navigation "Permanent link")

-   [Obsidian Plugin](https://github.com/obsidianPublisher/obsidian-github-publisher)
-   [Python package](https://github.com/obsidianPublisher/obsidian-mkdocs-publisher-python)
-   [Template](https://github.com/obsidianPublisher/obsidian-mkdocs-publisher-template)
