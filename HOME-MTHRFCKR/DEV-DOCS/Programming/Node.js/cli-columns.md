[![NPM version](https://camo.githubusercontent.com/b439fefa670a28e51cad4d8cb4771ceabf25859a5faaae5b18604f8635453bd5/687474703a2f2f696d672e736869656c64732e696f2f6e706d2f762f636c692d636f6c756d6e732e7376673f7374796c653d666c61742d737175617265)](https://npmjs.org/package/cli-columns) [![Downloads](https://camo.githubusercontent.com/62d7a1b13ebba26320f770103a0b21b14625e81ea7e845594bba3b99f12cea9b/687474703a2f2f696d672e736869656c64732e696f2f6e706d2f646d2f636c692d636f6c756d6e732e7376673f7374796c653d666c61742d737175617265)](https://npmjs.org/package/cli-columns)

Columnated lists for the CLI. Unicode and ANSI safe.

## Install

```
$ npm install --save cli-columns
```

## Usage

const columns \= require('cli-columns');
const chalk \= require('chalk');

const values \= \[
    'blue' + chalk.bgBlue('berry'),
    '笔菠萝' + chalk.yellow('苹果笔'),
    chalk.red('apple'), 'pomegranate',
    'durian', chalk.green('star fruit'),
    'パイナップル', 'apricot', 'banana',
    'pineapple', chalk.bgRed.yellow('orange')
\];

console.log(columns(values));

[![screenshot](https://user-images.githubusercontent.com/155164/28672800-bd415c86-72ae-11e7-855c-6f6aa108921b.png)](https://user-images.githubusercontent.com/155164/28672800-bd415c86-72ae-11e7-855c-6f6aa108921b.png)

## API

### columns(values \[, options\]): String

-   `values` `{Array<String>}` Array of strings to display.
-   `options` `{Object}`
    -   `character` `{String}` (default: `' '`) Padding character.
    -   `newline` `{String}` (default: `'\n'`) Newline character.
    -   `padding` `{Number}` (default: `2`) Space between columns.
    -   `sort` `{Boolean}` (default: `true`) Whether to sort results.
    -   `width` `{Number}` (default: `process.stdout.columns`) Max width of list.

Sorts and formats a list of values into columns suitable to display in a given width.

## Contribute

Standards for this project, including tests, code coverage, and semantics are enforced with a build tool. Pull requests must include passing tests with 100% code coverage and no linting errors.

### Test

___

MIT © [Shannon Moeller](http://shannonmoeller.com/)