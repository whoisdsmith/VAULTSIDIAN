---
created: 2022-08-07T22:09:56 (UTC -04:00)
tags: []
source: https://github.com/mfarragher/obsidiantools
author: 
---

# obsidiantools

---
[![PyPI version](https://camo.githubusercontent.com/a47557286d0d8590a663e67c314b9f4a675106fbea4cb8e9bb47d3ee514032a7/68747470733a2f2f62616467652e667572792e696f2f70792f6f6273696469616e746f6f6c732e737667)](https://badge.fury.io/py/obsidiantools) [![PyPI version](https://camo.githubusercontent.com/d31a8d48dcccddaa94626f20c8c9ce418f842f34ac6c0837a0e978c67950e392/68747470733a2f2f696d672e736869656c64732e696f2f707970692f707976657273696f6e732f6f6273696469616e746f6f6c732e737667)](https://badge.fury.io/py/obsidiantools) [![Licence](https://camo.githubusercontent.com/8ccf186e7288af6d88a1f6a930c0fcc4e7a8a9936b34e07629d815d1eab4d977/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c6963656e73652d425344253230332d2d436c617573652d626c75652e737667)](https://github.com/mfarragher/obsidiantools/blob/main/LICENSE) [![Documentation](https://camo.githubusercontent.com/2d890e4d5b327fe6dd47f4177ac9fccf681cd28af3eaa185af28d7a45b50b360/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646f63732d6f6273696469616e746f6f6c732d2d64656d6f2d6f72616e6765)](https://github.com/mfarragher/obsidiantools-demo) [![codecov](https://camo.githubusercontent.com/7f0424912efab08ee169394e868fe6ea1f9cd186892222784194aeb963822afe/68747470733a2f2f636f6465636f762e696f2f67682f6d6661727261676865722f6f6273696469616e746f6f6c732f6272616e63682f6d61696e2f67726170682f62616467652e737667)](https://codecov.io/gh/mfarragher/obsidiantools)

**obsidiantools** is a Python package for getting structured metadata about your [Obsidian.md notes](https://obsidian.md/) and analysing your vault. Complement your Obsidian workflows by getting metrics and detail about all your notes in one place through the widely-used Python data stack.

It's incredibly easy to explore structured data on your vault through this fluent interface. This is all the code you need to generate a `vault` object that stores the key data:

```python
import obsidiantools.api as otools

vault = otools.Vault(<VAULT_DIRECTORY>).connect().gather()
```

These are the basics of the function calls:

-   `connect()`: connect your notes together in a graph structure and get metadata on links (e.g. wikilinks, backlinks, etc.)
-   `gather()`: gather the plaintext content from your notes in one place. This includes the 'source text' that represent how your notes are written. There are arguments to support what text you want to remove, e.g. remove code.

See some of the **key features** below - all accessible from the `vault` object either through a method or an attribute.

As this package relies upon note (file)names, it is only recommended for use on vaults where wikilinks are not formatted as paths and where note names are unique. This should cover the vast majority of vaults that people create.

## 💡 Key features

This is how **`obsidiantools`** can complement your workflows for note-taking:

-   **Access a `networkx` graph of your vault** (`vault.graph`)
    -   NetworkX is the main Python library for network analysis, enabling sophisticated analyses of your vault.
    -   NetworkX also supports the ability to export your graph to other data formats.
    -   When instantiating a `vault`, the analysis can also be filtered on specific subdirectories.
-   **Get summary stats about your notes, e.g. number of backlinks and wikilinks, in a Pandas dataframe**
    -   Get the dataframe via `vault.get_note_metadata()`
-   **Retrieve detail about your notes' links and metadata as built-in Python types**
    -   The various types of links:
        -   Wikilinks (incl. header links, links with alt text)
        -   Embedded files
        -   Backlinks
        -   Markdown links
    -   You can access all the links in one place, or you can load them for an individual note:
        -   e.g. `vault.backlinks_index` for all backlinks in the vault
        -   e.g. `vault.get_backlinks(<NOTE>)` for the backlinks of an individual note
    -   Front matter via `vault.get_front_matter(<NOTE>)` or `vault.front_matter_index`
    -   Tags via `vault.get_tags(<NOTE>)` or `vault.tags_index`
    -   LaTeX math via `vault.get_math(<NOTE>)` or `vault.math_index`
    -   Check which notes are isolated (`vault.isolated_notes`)
    -   Check which notes do not exist as files yet (`vault.nonexistent_notes`)
    -   As long as `gather()` is called:
        -   Get source text of note (via `vault.get_source_text(<NOTE>)`). This tries to represent how a note's text appears in Obsidian's 'source mode'.
        -   Get readable text of note (via `vault.get_readable_text(<NOTE>)`). This tries to reduce note text to minimal markdown formatting, e.g. preserving paragraphs, headers and punctuation. Only slight processing is needed for various forms of NLP analysis.

Check out the functionality in the demo repo. Launch the '15 minutes' demo in a virtual machine via Binder:

[![Documentation](https://camo.githubusercontent.com/2d890e4d5b327fe6dd47f4177ac9fccf681cd28af3eaa185af28d7a45b50b360/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646f63732d6f6273696469616e746f6f6c732d2d64656d6f2d6f72616e6765)](https://github.com/mfarragher/obsidiantools-demo) [![Binder](https://camo.githubusercontent.com/581c077bdbc6ca6899c86d0acc6145ae85e9d80e6f805a1071793dbe48917982/68747470733a2f2f6d7962696e6465722e6f72672f62616467655f6c6f676f2e737667)](https://mybinder.org/v2/gh/mfarragher/obsidiantools-demo/HEAD?filepath=obsidiantools%20in%2015%20minutes.ipynb)

There are other API features that try to mirror the Obsidian.md app, for your convenience when working with Python, but they are no substitute for the interactivity of the app!

The text from vault notes goes through this process: markdown → split out front matter from text → HTML → ASCII plaintext.

## ⏲️ Installation

`pip install obsidiantools`

As of Aug 2022, NetworkX and Pandas require Python 3.8 or higher, so 3.8 is the lowest Python version recommended.

## 🖇️ Dependencies

-   Main libraries:
    -   `markdown`
    -   `pymdown-extensions`
    -   `html2text`
    -   `pandas`
    -   `numpy`
    -   `networkx`
-   Libraries for front matter and HTML:
    -   `python-frontmatter`
    -   `beautifulsoup4`
    -   `lxml`
    -   `bleach`

All of these libraries are needed so that the package can separate note text from front matter in a generalised approach.

## 🏗️ Tests

A small 'dummy vault' vault of lipsum notes is in `tests/vault-stub` (generated with help of the [lorem-markdownum](https://github.com/jaspervdj/lorem-markdownum) tool). Sense-checking on the API functionality was also done on a personal vault of up to 100 notes.

I am not sure how the parsing will work outside of Latin languages - if you have ideas on how that can be supported feel free to suggest a feature or pull request.

## ⚖️ Licence

Modified BSD (3-clause)
