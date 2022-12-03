Toggle table of contents sidebar

Mdformat offers an extensible plugin system for both code fence content formatting and Markdown parser extensions (like GFM tables). This document explains how to use plugins. If you want to create a new plugin, refer to the [contributing](https://mdformat.readthedocs.io/en/stable/contributors/contributing.html) docs.

## Code formatter plugins[¶](https://mdformat.readthedocs.io/en/stable/users/plugins.html#code-formatter-plugins "Permalink to this headline")

Mdformat features a plugin system to support formatting of Markdown code blocks where the coding language has been labeled. For instance, if [`mdformat-black`](https://github.com/hukkin/mdformat-black) plugin is installed in the environment, mdformat CLI will automatically format Python code blocks with [Black](https://github.com/psf/black).

For stability, mdformat Python API behavior will not change simply due to a plugin being installed. Code formatters will have to be explicitly enabled in addition to being installed:

import mdformat

unformatted \= "\`\`\`python\\n'''black converts quotes'''\\n\`\`\`\\n"
\# Pass in \`codeformatters\` here! It is an iterable of coding languages
\# that should be formatted
formatted \= mdformat.text(unformatted, codeformatters\={"python"})
assert formatted \== '\`\`\`python\\n"""black converts quotes"""\\n\`\`\`\\n'

### Existing plugins[¶](https://mdformat.readthedocs.io/en/stable/users/plugins.html#existing-plugins "Permalink to this headline")

## Parser extension plugins[¶](https://mdformat.readthedocs.io/en/stable/users/plugins.html#parser-extension-plugins "Permalink to this headline")

Markdown-it-py offers a range of useful extensions to the base CommonMark parser (see the [documented list](https://markdown-it-py.readthedocs.io/en/latest/plugins.html)).

Mdformat features a plugin system to support the loading and rendering of such extensions.

For stability, mdformat Python API behavior will not change simply due to a plugin being installed. Extensions will have to be explicitly enabled in addition to being installed:

import mdformat

unformatted \= "content...\\n"
\# Pass in \`extensions\` here! It is an iterable of extensions that should be loaded
formatted \= mdformat.text(unformatted, extensions\={"tables"})

### Existing plugins[¶](https://mdformat.readthedocs.io/en/stable/users/plugins.html#id1 "Permalink to this headline")