[![](https://camo.githubusercontent.com/ab774779b77774ec814d04ef18092537a91dc6a17a886fc0b3c9d60e811dc51b/68747470733a2f2f7261776769742e636f6d2f662f6f6d656c657474652f6d61737465722f7265736f75726365732f6c6f676f2e7376673f7631)](https://camo.githubusercontent.com/ab774779b77774ec814d04ef18092537a91dc6a17a886fc0b3c9d60e811dc51b/68747470733a2f2f7261776769742e636f6d2f662f6f6d656c657474652f6d61737465722f7265736f75726365732f6c6f676f2e7376673f7631)

> Omelette is a simple template based autocompletion tool for **Node** and **Deno** projects with super easy API.

[![npm version](https://camo.githubusercontent.com/e65b260d9442d0b385c8b5d9d8d064c6975322a24aa191608ed53b8e742f382b/68747470733a2f2f62616467652e667572792e696f2f6a732f6f6d656c657474652e737667)](https://badge.fury.io/js/omelette) [![Build Status](https://camo.githubusercontent.com/6348321a5fa6151bed5ea1a68cd5598b9e731e89fb4cac094836fae6fbf1def5/68747470733a2f2f7472617669732d63692e6f72672f662f6f6d656c657474652e7376673f6272616e63683d6d6173746572)](https://travis-ci.org/f/omelette)

yarn add omelette
# or
npm install omelette

You also can use Omelette with **Deno**:

import omelette from "https://deno.land/x/omelette/omelette.ts";

You just have to decide your program name and CLI fragments.

omelette\`github ${\['pull', 'push'\]} ${\['origin', 'upstream'\]} ${\['master', 'develop'\]}\`.init()

...and you are almost done! The output will look like this:

[![](https://camo.githubusercontent.com/d7caa832fb5e62a10061825c0d22afa60a8eef4fa3168ba4c9ed5a1f406f488e/68747470733a2f2f7261772e6769746875622e636f6d2f662f6f6d656c657474652f6d61737465722f7265736f75726365732f6f6d656c657474652d6e65772e6769663f7631)](https://camo.githubusercontent.com/d7caa832fb5e62a10061825c0d22afa60a8eef4fa3168ba4c9ed5a1f406f488e/68747470733a2f2f7261772e6769746875622e636f6d2f662f6f6d656c657474652f6d61737465722f7265736f75726365732f6f6d656c657474652d6e65772e6769663f7631)

## Quick Start

**For a step by step guide please follow [this link](https://github.com/f/omelette/issues/33#issuecomment-439864555)**

Implementing omelette is very easy:

import \* as omelette from 'omelette';

const firstArgument \= ({ reply }) \=> {
  reply(\[ 'beautiful', 'cruel', 'far' \])
}

const planet \= ({ reply }) \=> {
  reply(\[ 'world', 'mars', 'pluto' \])
}

omelette\`hello|hi ${firstArgument} ${planet}\`.init()

[![](https://camo.githubusercontent.com/ced11d0225205611eec07623cdcd00d97a5460e898af2c79a00d97a851e015e8/68747470733a2f2f7261772e6769746875622e636f6d2f662f6f6d656c657474652f6d61737465722f7265736f75726365732f6f6d656c657474652d6e65772d68656c6c6f2e6769663f7631)](https://camo.githubusercontent.com/ced11d0225205611eec07623cdcd00d97a5460e898af2c79a00d97a851e015e8/68747470733a2f2f7261772e6769746875622e636f6d2f662f6f6d656c657474652f6d61737465722f7265736f75726365732f6f6d656c657474652d6e65772d68656c6c6f2e6769663f7631)

### Simple Event Based API ☕️

It's based on a simple CLI template.

Let's think we have a executable file with the name **githubber**, _in a global path_.

In our program, the code will be:

import \* as omelette from 'omelette';

// Write your CLI template.
const completion \= omelette(\`githubber|gh <action> <user> <repo>\`);

// Bind events for every template part.
completion.on('action', ({ reply }) \=> {
  reply(\[ 'clone', 'update', 'push' \])
})

completion.on('user', ({ reply }) \=> {
  reply(fs.readdirSync('/Users/'))
})

completion.on('repo', ({ before, reply }) \=> {
  reply(\[
    \`http://github.com/${before}/helloworld\`,
    \`http://github.com/${before}/blabla\`
  \])
})

// Initialize the omelette.
completion.init()

// If you want to have a setup feature, you can use \`omeletteInstance.setupShellInitFile()\` function.
if (~process.argv.indexOf('--setup')) {
  completion.setupShellInitFile()
}

// Similarly, if you want to tear down autocompletion, use \`omeletteInstance.cleanupShellInitFile()\`
if (~process.argv.indexOf('--cleanup')) {
  completion.cleanupShellInitFile()
}

// Rest is yours
console.log("Your program's default workflow.")
console.log(process.argv)

`complete.reply` is the completion replier. You must pass the options into that method.

### ES6 Template Literal API 🚀

You can use **Template Literals** to define your completion with a simpler (super easy) API.

import \* as omelette from 'omelette';

// Just pass a template literal to use super easy API.
omelette\`hello ${\[ 'cruel', 'nice' \]} ${\[ 'world', 'mars' \]}\`.init()

Let's make the example above with ES6 TL:

import \* as omelette from 'omelette'

// Write your CLI template.
omelette\`
 githubber|gh
 ${\[ 'clone', 'update', 'push' \]}
 ${() \=> fs.readdirSync('/Users/')}
 ${({ before }) \=> \[
 \`http://github.com/${before}/helloworld\`,
 \`http://github.com/${before}/blabla\`,
 \]}
\`.init()

Also you can still use lambda functions to make more complex template literals:

#### Advanced Template Literals

import \* as omelette from 'omelette';

omelette\`
 githubber|gh
 ${\['pull', 'push', 'star'\] /\* Direct command list \*/}
 ${require('some/other/commands') /\* Import from another file \*/}
 ${getFromRemote('http://api.example.com/commands') /\* Remote call at the beginning \*/}
 ${({ reply }) \=> fetch('http://api.example.com/lazy-commands').then(reply) /\* Fetch when argument <tab>bed \*/}
 ${() \=> fs.readdirSync("/Users/") /\* Access filesystem via Node \*/}
 ${({ before }) \=> \[ /\* Use parameters like \`before\`, \`line\`, \`fragment\` or \`reply\` \*/
 \`${before}/helloworld\`,
 \`${before}/blabla\`
 \]}
 \`.init()

// No extra configuration required.

console.log("Your program's default workflow.")
console.log(process.argv)

### Async API ⏩

Omelette allows you to use `async` functions. You have to use `onAsync` and to pass `Promise` object to the `reply` function.

complete.onAsync('user', async ({ reply }) \=> {
  reply(new Promise((resolve) \=> {
    fs.readdir('/Users/', (err, users) \=> {
      resolve(users)
    })
  }))
})

#### ⚠️ A note about `async` handlers

If you are using async handlers, you have to use `complete.next` method to continue running your main workflow.

// ...

complete.onAsync('user', async ({ reply }) \=> {
  reply(new Promise((resolve) \=> {
    fs.readdir('/Users/', (err, users) \=> {
      resolve(users)
    })
  }))
})

// Instead of running directly, you need to set an handler to run your main workflow.
complete.next(()\=> {
  console.log("Your program's default workflow.")
  console.log(process.argv)
})

// .init must be called after defining .next
complete.init()
// ...

Using `util.promisify` will make your `async` handlers easier.

import promisify from 'util';

complete.onAsync('user', async ({ reply }) \=> {
  reply(await promisify(fs.readdir)('/Users'))
})

### Tree API 🌲

You can use `simple objects` as autocompletion definitions:

omelette('hello').tree({
  cruel: \['world', 'moon'\],
  beautiful: \['mars', 'pluto'\]
}).init();

## Install

### Automated Install

> ⚠️ Not available for Deno runtime. You can make your users to put `yourprogram --completion | source` or `yourprogram --completion-fish | source` args explicitly to their shell config file.

Installing and making your users install the autocompletion feature is very simple.

You can use simply use `setupShellInitFile` function.

try {
  // Pick shell init file automatically
  complete.setupShellInitFile()

  // Or use a manually defined init file
  complete.setupShellInitFile('~/.my\_bash\_profile')

} catch (err) {
  // setupShellInitFile() throws if the used shell is not supported
}

If you use Bash, it will create a file at `~/.<program-name>/completion.sh` and append a loader code to `~/.bash_profile` file.

If you use Zsh, it appends a loader code to `~/.zshrc` file.

If you use Fish, it appends a loader code to `~/.config/fish/config.fish` file.

_TL;DR: It does the Manual Install part, basically._

### Automated Uninstallation

> ⚠️ Not available for Deno runtime. Your users need to remove the autocompletion setup script from their shell config files.

Similarly to installation, you can use `cleanupShellInitFile` to undo changes done by `setupShellInitFile`.

complete.cleanupShellInitFile()

As with `setupShellInitFile()`, wrap this in a `try/catch` block to handle unsupported shells.

### Manual Installation

#### Instructions for your README files:

_(You should add these instructions to your project's README, don't forget to replace `myprogram` string with your own executable name)_

In **zsh**, you should write these:

echo '. <(myprogram --completion)' \>> ~/.zshrc

In **bash**:

On macOS, you may need to install `bash-completion` using `brew install bash-completion`.

myprogram --completion \>> ~/.config/hello.completion.sh
echo 'source ~/.config/hello.completion.sh' \>> ~/.bash\_profile

In **fish**:

echo 'myprogram --completion-fish | source' \>> ~/.config/fish/config.fish

That's all!

Now you have an autocompletion system for your CLI tool.

## Additions

There are some useful additions to omelette.

### Parameters

Callbacks have two parameters:

-   The fragment name (e.g.`command` of `<command>` template) _(only in global event)_
-   The meta data
    -   `fragment`: The number of fragment.
    -   `before`: The previous word.
    -   `line`: The whole command line buffer allow you to parse and reply as you wish.
    -   `reply`: This is the reply function to use _this-less_ API.

### Global Event

You can also listen to all fragments by "complete" event.

complete.on('complete', (fragment, { reply }) \=> reply(\["hello", "world"\]));

### Numbered Arguments

You can also listen to events in order.

complete.on('$1', ({ reply }) \=> reply(\["hello", "world"\]))

### Autocompletion Tree

You can create a **completion tree** to more complex autocompletions.

omelette('hello').tree({
  how: {
    much: {
      is: {
        this: \['car'\],
        that: \['house'\],
      }
    },
    are: \['you'\],
    many: \['cars', 'houses'\],
  },
  where: {
    are: {
      you: \['from'\],
      the: \['houses', 'cars'\],
    },
    is: {
      // You can also add some logic with defining functions:
      your() {
        return \['house', 'car'\];
      },
    }
  },
}).init()

Now, you will be able to use your completion as tree.

[![](https://camo.githubusercontent.com/1954e9827e8359a17d3b82b07ffc203f3986d7d3ec9f73f4af20dcd85e337ffc/68747470733a2f2f7261772e6769746875622e636f6d2f662f6f6d656c657474652f6d61737465722f7265736f75726365732f6f6d656c657474652d747265652d6e65772e6769663f7631)](https://camo.githubusercontent.com/1954e9827e8359a17d3b82b07ffc203f3986d7d3ec9f73f4af20dcd85e337ffc/68747470733a2f2f7261772e6769746875622e636f6d2f662f6f6d656c657474652f6d61737465722f7265736f75726365732f6f6d656c657474652d747265652d6e65772e6769663f7631)

> Thanks [@jblandry](https://github.com/jblandry) for the idea.

#### Advanced Tree Implementations

You can seperate your autocompletion by importing objects from another file:

omelette('hello').tree(require('./autocompletion-tree.js')).init();

### Short Names

You can set a short name for an executable:

In this example, `githubber` is long and `gh` is short.

omelette('githubber|gh <module> <command> <suboption>');

## Test

Now you can try it in your shell.

git clone https://github.com/f/omelette
cd omelette/example
alias githubber="./githubber" # The app should be global, completion will search it on global level.
./githubber --setup --debug # --setup is not provided by omelette, you should proxy it.
# (reload bash, or source ~/.bash\_profile or ~/.config/fish/config.fish)
omelette-debug-githubber # See Debugging section
githubber<tab\>
ghb<tab\> # short alias
gh<tab\> # short alias

### Debugging

`--debug` option generates a function called `omelette-debug-<programname>`. (`omelette-debug-githubber` in this example).

When you run `omelette-debug-<programname>`, it will create aliases for your application. (`githubber` and `gh` in this example).

A long name:

$ githubber<tab\>
clone update push

Or short name:

$ gh<tab\>
clone update push

Then you can start easily.

$ ./githubber<tab\>
clone update push

$ ./githubber cl<tab\>
$ ./githubber clone<tab\>
Guest fka

$ ./githubber clone fka<tab\>
$ ./githubber clone fka http://github.com/fka/<tab\>
http://github.com/fka/helloworld
http://github.com/fka/blabla

## Using with Deno

Omelette now supports and is useful with **Deno**. You can make your Deno based CLI tools autocomplete powered using Omelette. It's fully featured but `setupShellInitFile` and `cleanupShellInitFile` methods does not exist for now (to prevent requirement of `allow-env`, `allow-read` and `allow-write` permissions).

### Instructions to use Omelette in your Deno projects:

Assume we have a `hello.js`:

import omelette from "https://raw.githubusercontent.com/f/omelette/master/deno/omelette.ts";

const complete \= omelette("hello <action>");

complete.on("action", function ({ reply }) {
  reply(\["world", "mars", "jupiter"\]);
});

complete.init();

// your CLI program

Install your program using `deno install`:

deno install hello.js
hello --completion | source # bash and zsh installation
hello --completion-fish | source # fish shell installation

That's all! Now you have autocompletion feature!

## Users?

-   **Windows Azure** uses Omelette to support autocompletion in [azure-cli](https://github.com/WindowsAzure/azure-sdk-tools-xplat).
-   **Office 365 CLI** uses Omelette to support autocompletion in [office365-cli](https://github.com/pnp/office365-cli).
-   **Visual Studio App Center CLI** uses Omelette to support autocompletion in [appcenter-cli](https://github.com/Microsoft/appcenter-cli).

## Contribute

I need your contributions to make that work better!

## License

This project licensed under MIT.