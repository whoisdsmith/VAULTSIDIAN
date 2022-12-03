[![Build](https://github.com/remarkjs/remark/workflows/main/badge.svg)](https://github.com/remarkjs/remark/actions) [![Coverage](https://camo.githubusercontent.com/d4d5ca5b211025c6a1f897f4441ef56d64ae1e2f6c50019ee39ab8364c756b28/68747470733a2f2f696d672e736869656c64732e696f2f636f6465636f762f632f6769746875622f72656d61726b6a732f72656d61726b2e737667)](https://codecov.io/github/remarkjs/remark) [![Downloads](https://camo.githubusercontent.com/a5e6350a1a8cb031a0b5eae237d87a404747898ab8073e78791d402ccf18caf4/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f646d2f72656d61726b2e737667)](https://www.npmjs.com/package/remark) [![Size](https://camo.githubusercontent.com/b2b21a9c9714de58fe5aa8e8b966b41a408df4e9b2ff90443e436b76c0e2eada/68747470733a2f2f696d672e736869656c64732e696f2f62756e646c6570686f6269612f6d696e7a69702f72656d61726b2e737667)](https://bundlephobia.com/result?p=remark) [![Sponsors](https://camo.githubusercontent.com/3d801487a7570a627780b2e75af3b7f07239ebb2b91e850e8e5a3eeddb91ff58/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f756e69666965642f73706f6e736f72732f62616467652e737667)](https://opencollective.com/unified) [![Backers](https://camo.githubusercontent.com/f5ea613d33171557007b46e32a55a43f9fbf0ad19059fc396c4be556ebf093b7/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f756e69666965642f6261636b6572732f62616467652e737667)](https://opencollective.com/unified) [![Chat](https://camo.githubusercontent.com/f28d582b8e09c11e9852250fcb90ba3b464842dc2bbb8ae38bb28e900a0267e8/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f636861742d64697363757373696f6e732d737563636573732e737667)](https://github.com/remarkjs/remark/discussions)

**remark** is a tool that transforms markdown with plugins. These plugins can inspect and change your markup. You can use remark on the server, the client, CLIs, deno, etc.

## Feature highlights

-   **[popular](https://www.npmtrends.com/remark-parse-vs-marked-vs-micromark-vs-markdown-it)** (world’s most popular markdown parser)
-   **[compliant](https://github.com/remarkjs/remark#syntax)** (100% to CommonMark, 100% to GFM with a plugin)
-   **[plugins](https://github.com/remarkjs/remark#plugins)** (150+ plugins you can pick and choose from)
-   **[ASTs](https://github.com/remarkjs/remark#syntax-tree)** (inspecting and changing content made easy)

## Intro

remark is a very popular ecosystem of plugins that work with markdown as structured data, specifically ASTs (abstract syntax trees). ASTs make it easy for programs to deal with markdown. We call those programs plugins. Plugins inspect and change trees. You can use the many existing plugins or you can make your own.

-   to learn markdown, see this [cheatsheet and tutorial](https://commonmark.org/help/)
-   for more about us, see [`unifiedjs.com`](https://unifiedjs.com/)
-   for updates, see [Twitter](https://twitter.com/unifiedjs)
-   for questions, see [support](https://github.com/remarkjs/.github/blob/main/support.md)
-   to help, see [contribute](https://github.com/remarkjs/remark#contribute) or [sponsor](https://github.com/remarkjs/remark#sponsor) below

## Contents

-   [What is this?](https://github.com/remarkjs/remark#what-is-this)
-   [When should I use this?](https://github.com/remarkjs/remark#when-should-i-use-this)
-   [Plugins](https://github.com/remarkjs/remark#plugins)
-   [Examples](https://github.com/remarkjs/remark#examples)
    -   [Example: turning markdown into HTML](https://github.com/remarkjs/remark#example-turning-markdown-into-html)
    -   [Example: support for GFM and frontmatter](https://github.com/remarkjs/remark#example-support-for-gfm-and-frontmatter)
    -   [Example: checking markdown](https://github.com/remarkjs/remark#example-checking-markdown)
    -   [Example: checking and formatting markdown on the CLI](https://github.com/remarkjs/remark#example-checking-and-formatting-markdown-on-the-cli)
-   [Syntax](https://github.com/remarkjs/remark#syntax)
-   [Syntax tree](https://github.com/remarkjs/remark#syntax-tree)
-   [Types](https://github.com/remarkjs/remark#types)
-   [Compatibility](https://github.com/remarkjs/remark#compatibility)
-   [Security](https://github.com/remarkjs/remark#security)
-   [Contribute](https://github.com/remarkjs/remark#contribute)
-   [Sponsor](https://github.com/remarkjs/remark#sponsor)
-   [License](https://github.com/remarkjs/remark#license)

## What is this?

You can use plugins to turn markdown into HTML. **In**:

**Out**:

<h1\>Hello, <em\>Mercury</em\>!</h1\>

You can use plugins to change markdown. **In**:

**Plugin**:

import {visit} from 'unist-util-visit'

/\*\* @type {import('unified').Plugin<\[\], import('mdast').Root>} \*/
function myRemarkPluginToIncreaseHeadings() {
  return (tree) \=> {
    visit(tree, (node) \=> {
      if (node.type \=== 'heading') {
        node.depth++
      }
    })
  }
}

**Out**:

You can use remark for many different things. **[unified](https://github.com/unifiedjs/unified)** is the core project that transforms content with ASTs. **remark** adds support for markdown to unified. **[mdast](https://github.com/syntax-tree/mdast)** is the markdown AST that remark uses.

This GitHub repository is a monorepo that contains the following packages:

-   [`remark-parse`](https://github.com/remarkjs/remark/blob/main/packages/remark-parse) — plugin to take markdown as input and turn it into a syntax tree (mdast)
-   [`remark-stringify`](https://github.com/remarkjs/remark/blob/main/packages/remark-stringify) — plugin to take a syntax tree (mdast) and turn it into markdown as output
-   [`remark`](https://github.com/remarkjs/remark/blob/main/packages/remark) — unified, `remark-parse`, and `remark-stringify`, useful when input and output are markdown
-   [`remark-cli`](https://github.com/remarkjs/remark/blob/main/packages/remark-cli) — CLI around `remark` to inspect and format markdown in scripts

## When should I use this?

If you _just_ want to turn markdown into HTML (with maybe a few extensions), we recommend [`micromark`](https://github.com/micromark/micromark) instead. remark can also do that but it focusses on ASTs and providing an interface for plugins to transform them.

Depending on the input you have and output you want, you can use different parts of remark. If the input is markdown, you can use `remark-parse` with `unified`. If the output is markdown, you can use `remark-stringify` with `unified` If both the input and output are markdown, you can use `remark` on its own. When you want to inspect and format markdown files in a project, you can use `remark-cli`.

## Plugins

remark plugins deal with markdown. Some popular examples are:

-   [`remark-gfm`](https://github.com/remarkjs/remark-gfm) — add support for GFM (GitHub flavored markdown)
-   [`remark-lint`](https://github.com/remarkjs/remark-lint) — inspect markdown and warn about inconsistencies
-   [`remark-toc`](https://github.com/remarkjs/remark-toc) — generate a table of contents
-   [`remark-html`](https://github.com/remarkjs/remark-html) — turn the syntax tree into serialized HTML

These plugins are exemplary because what they do and how they do it is quite different, respectively to extend markdown syntax, inspect trees, change trees, and define other output formats.

You can choose from the 150+ plugins that already exist. Here are three good ways to find plugins:

-   [`awesome-remark`](https://github.com/remarkjs/awesome-remark) — selection of the most awesome projects
-   [List of plugins](https://github.com/remarkjs/remark/blob/main/doc/plugins.md#list-of-plugins) — list of all plugins
-   [`remark-plugin` topic](https://github.com/topics/remark-plugin) — any tagged repo on GitHub

Some plugins are maintained by us here in the `@remarkjs` organization while others are maintained by folks elsewhere. Anyone can make remark plugins, so as always when choosing whether to include dependencies in your project, make sure to carefully assess the quality of remark plugins too.

## Examples

### Example: turning markdown into HTML

remark is an ecosystem around markdown. A different ecosystem is for HTML: [rehype](https://github.com/rehypejs/rehype). The following example turns markdown into HTML by combining both ecosystems with [`remark-rehype`](https://github.com/remarkjs/remark-rehype):

import {unified} from 'unified'
import remarkParse from 'remark-parse'
import remarkRehype from 'remark-rehype'
import rehypeSanitize from 'rehype-sanitize'
import rehypeStringify from 'rehype-stringify'

main()

async function main() {
  const file \= await unified()
    .use(remarkParse)
    .use(remarkRehype)
    .use(rehypeSanitize)
    .use(rehypeStringify)
    .process('# Hello, Neptune!')

  console.log(String(file))
}

Yields:

### Example: support for GFM and frontmatter

remark supports CommonMark by default. Non-standard markdown extensions can be enabled with plugins. The following example adds support for GFM (autolink literals, footnotes, strikethrough, tables, tasklists) and frontmatter (YAML):

import {unified} from 'unified'
import remarkParse from 'remark-parse'
import remarkFrontmatter from 'remark-frontmatter'
import remarkGfm from 'remark-gfm'
import remarkRehype from 'remark-rehype'
import rehypeStringify from 'rehype-stringify'

main()

async function main() {
  const file \= await unified()
    .use(remarkParse)
    .use(remarkFrontmatter)
    .use(remarkGfm)
    .use(remarkRehype)
    .use(rehypeStringify)
    .process('---\\nlayout: home\\n---\\n\\n# Hi ~~Mars~~Venus!')

  console.log(String(file))
}

Yields:

<h1\>Hi <del\>Mars</del\>Venus!</h1\>

### Example: checking markdown

The following example checks that markdown code style is consistent and follows recommended best practices:

import {reporter} from 'vfile-reporter'
import {remark} from 'remark'
import remarkPresetLintConsistent from 'remark-preset-lint-consistent'
import remarkPresetLintRecommended from 'remark-preset-lint-recommended'

main()

async function main() {
  const file \= await remark()
    .use(remarkPresetLintConsistent)
    .use(remarkPresetLintRecommended)
    .process('1) Hello, \_Jupiter\_ and \*Neptune\*!')

  console.error(reporter(file))
}

Yields:

```
        1:1  warning  Missing newline character at end of file  final-newline              remark-lint
   1:1-1:35  warning  Marker style should be `.`                ordered-list-marker-style  remark-lint
        1:4  warning  Incorrect list-item indent: add 1 space   list-item-indent           remark-lint
  1:25-1:34  warning  Emphasis should use `_` as a marker       emphasis-marker            remark-lint

⚠ 4 warnings
```

### Example: checking and formatting markdown on the CLI

The following example checks and formats markdown with `remark-cli`, which is the CLI (command line interface) of remark that you can use in your terminal. This example assumes you’re in a Node.js package.

First, install the CLI and plugins:

npm install remark-cli remark-toc remark-preset-lint-consistent remark-preset-lint-recommended --save-dev

Now, add an npm script in your `package.json`:

  /\* … \*/
  "scripts": {
    /\* … \*/
    "format": "remark . --output",
    /\* … \*/
  },
  /\* … \*/

> 💡 **Tip**: add ESLint and such in the `format` script too.

Observe that the above change adds a `format` script, which can be run with `npm run format`. It runs remark on all markdown files (`.`) and rewrites them (`--output`). Run `./node_modules/.bin/remark --help` for more info on the CLI.

Then, add a `remarkConfig` to your `package.json` to configure remark:

  /\* … \*/
  "remarkConfig": {
    "settings": {
      "bullet": "\*", // Use \`\*\` for list item bullets (default)
      // See <https://github.com/remarkjs/remark/tree/main/packages/remark-stringify> for more options.
    },
    "plugins": \[
      "remark-preset-lint-consistent", // Check that markdown is consistent.
      "remark-preset-lint-recommended", // Few recommended rules.
      \[
        // Generate a table of contents in \`## Contents\`
        "remark-toc",
        {
          "heading": "contents"
        }
      \]
    \]
  },
  /\* … \*/

> 👉 **Note**: you must remove the comments in the above examples when copy/pasting them, as comments are not supported in `package.json` files.

Finally, you can run the npm script to check and format markdown files in your project:

## Syntax

remark follows CommonMark, which standardizes the differences between markdown implementations, by default. Some syntax extensions are supported through plugins.

We use [`micromark`](https://github.com/micromark/micromark) for our parsing. See its documentation for more information on markdown, CommonMark, and extensions.

## Syntax tree

The syntax tree format used in remark is [mdast](https://github.com/syntax-tree/mdast). It represents markdown constructs as JSON objects. **In**:

**Out**:

{
  type: 'heading',
  depth: 2,
  children: \[
    {type: 'text', value: 'Hello '},
    {type: 'emphasis', children: \[{type: 'text', value: 'Pluto'}\]}
    {type: 'text', value: '!'}
  \]
}

## Types

The remark organization and the unified collective as a whole is fully typed with [TypeScript](https://www.typescriptlang.org/). Types for mdast are available in [`@types/mdast`](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/mdast).

## Compatibility

Projects maintained by the unified collective are compatible with all maintained versions of Node.js. As of now, that is Node.js 12.20+, 14.14+, and 16.0+. Our projects sometimes work with older versions, but this is not guaranteed.

## Security

As markdown can be turned into HTML and improper use of HTML can open you up to [cross-site scripting (XSS)](https://en.wikipedia.org/wiki/Cross-site_scripting) attacks, use of remark can be unsafe. When going to HTML, you will likely combine remark with **[rehype](https://github.com/rehypejs/rehype)**, in which case you should use [`rehype-sanitize`](https://github.com/rehypejs/rehype-sanitize).

Use of remark plugins could also open you up to other attacks. Carefully assess each plugin and the risks involved in using them.

For info on how to submit a report, see our [security policy](https://github.com/remarkjs/.github/blob/main/security.md).

## Contribute

See [`contributing.md`](https://github.com/remarkjs/.github/blob/main/contributing.md) in [`remarkjs/.github`](https://github.com/remarkjs/.github) for ways to get started. See [`support.md`](https://github.com/remarkjs/.github/blob/main/support.md) for ways to get help. Join us in [Discussions](https://github.com/remarkjs/remark/discussions) to chat with the community and contributors.

This project has a [code of conduct](https://github.com/remarkjs/.github/blob/main/code-of-conduct.md). By interacting with this repository, organization, or community you agree to abide by its terms.

## Sponsor

Support this effort and give back by sponsoring on [OpenCollective](https://opencollective.com/unified)!

[Vercel](https://vercel.com/)

[![](https://avatars1.githubusercontent.com/u/14985020?s=256&v=4)](https://vercel.com/)

[Motif](https://motif.land/)

[![](https://avatars1.githubusercontent.com/u/74457950?s=256&v=4)](https://motif.land/)

[HashiCorp](https://www.hashicorp.com/)

[![](https://avatars1.githubusercontent.com/u/761456?s=256&v=4)](https://www.hashicorp.com/)

[Gatsby](https://www.gatsbyjs.org/)

[![](https://avatars1.githubusercontent.com/u/12551863?s=256&v=4)](https://www.gatsbyjs.org/)

[Netlify](https://www.netlify.com/)

[![](https://camo.githubusercontent.com/a04f5c94c1ca51dce8845aa83b4237d487a4291441178c1b8aa34cfeb8d408bb/68747470733a2f2f696d616765732e6f70656e636f6c6c6563746976652e636f6d2f6e65746c6966792f343038376465322f6c6f676f2f3235362e706e67)](https://www.netlify.com/)

[Coinbase](https://www.coinbase.com/)

[![](https://avatars1.githubusercontent.com/u/1885080?s=256&v=4)](https://www.coinbase.com/)

[ThemeIsle](https://themeisle.com/)

[![](https://avatars1.githubusercontent.com/u/58979018?s=128&v=4)](https://themeisle.com/)

[Expo](https://expo.io/)

[![](https://avatars1.githubusercontent.com/u/12504344?s=128&v=4)](https://expo.io/)

[Boost Hub](https://boosthub.io/)

[![](https://camo.githubusercontent.com/b78d7c010b71e6ea973e8664423a86da80bf091a6ea8bf5958bab335bcfe63db/68747470733a2f2f696d616765732e6f70656e636f6c6c6563746976652e636f6d2f626f6f73746875622f363331383038332f6c6f676f2f3132382e706e67)](https://boosthub.io/)

[Holloway](https://www.holloway.com/)

[![](https://avatars1.githubusercontent.com/u/35904294?s=128&v=4)](https://www.holloway.com/)

  
[**You?**](https://opencollective.com/unified)

## License

[MIT](https://github.com/remarkjs/remark/blob/main/license) © [Titus Wormer](https://wooorm.com/)