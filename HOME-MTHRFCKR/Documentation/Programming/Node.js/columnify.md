[![NPM](https://camo.githubusercontent.com/08860b95d43206f6a72ad8ff16ab7f8983307d82d46e9387c20b7053b2fe316a/68747470733a2f2f6e6f6465692e636f2f6e706d2f636f6c756d6e6966792e706e673f646f776e6c6f6164733d7472756526646f776e6c6f616452616e6b3d747275652673746172733d74727565266368726f6d65)](https://nodei.co/npm-dl/columnify/) [![NPM](https://camo.githubusercontent.com/ca130c0287ac352374c7655c0f1825d541b334569580d9fe861370ef869c3fd3/68747470733a2f2f6e6f6465692e636f2f6e706d2d646c2f636f6c756d6e6966792e706e673f6d6f6e7468733d33266865696768743d33266368726f6d65)](https://nodei.co/npm/columnify/)

[![Build Status](https://camo.githubusercontent.com/f044d7efef1fe57a8fdcf9efde4282a6a59f86bef798d5bfd591a1443a3eed92/68747470733a2f2f696d672e736869656c64732e696f2f7472617669732f74696d6f786c65792f636f6c756d6e6966792e7376673f7374796c653d666c6174)](https://travis-ci.org/timoxley/columnify) [![NPM Version](https://camo.githubusercontent.com/ee99645b4ceed506fc7d18b074534fbfe640257aa07e49cbf38511432a8a685e/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f762f636f6c756d6e6966792e7376673f7374796c653d666c6174)](https://npmjs.org/package/columnify) [![License](https://camo.githubusercontent.com/4b5e88d50ed70ac59f7659473df2732b19617ac652a8f4a441528e37c8d5cfcd/687474703a2f2f696d672e736869656c64732e696f2f6e706d2f6c2f636f6c756d6e6966792e7376673f7374796c653d666c6174)](https://github.com/timoxley/columnify/blob/master/LICENSE) [![Dependency Status](https://camo.githubusercontent.com/07a936637af64909059a4d43a6943c9858e25ad19394b3224331889ee5e0627c/68747470733a2f2f64617669642d646d2e6f72672f74696d6f786c65792f636f6c756d6e6966792e737667)](https://david-dm.org/timoxley/columnify) [![devDependency Status](https://camo.githubusercontent.com/71ac22394b0dd7f1f5b4cb879ebfcc44f34dd3c5afedbdae0065ffd36218f8aa/68747470733a2f2f64617669642d646d2e6f72672f74696d6f786c65792f636f6c756d6e6966792f6465762d7374617475732e737667)](https://david-dm.org/timoxley/columnify#info=devDependencies)

Create text-based columns suitable for console output from objects or arrays of objects.

Columns are automatically resized to fit the content of the largest cell. Each cell will be padded with spaces to fill the available space and ensure column contents are left-aligned.

Designed to [handle sensible wrapping in npm search results](https://github.com/isaacs/npm/pull/2328).

`npm search` before & after integrating columnify:

[![npm-tidy-search](https://camo.githubusercontent.com/97c54bb5ac2cdd3bc6ec6d8ac5ba7c238b870545abf8db1d6896fc8664f71353/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f34333433382f313834383935392f61653032616430342d373661312d313165332d383235352d3437383164656266666332362e676966)](https://camo.githubusercontent.com/97c54bb5ac2cdd3bc6ec6d8ac5ba7c238b870545abf8db1d6896fc8664f71353/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f34333433382f313834383935392f61653032616430342d373661312d313165332d383235352d3437383164656266666332362e676966)

## Installation & Update

```
$ npm install --save columnify@latest
```

## Usage

var columnify \= require('columnify')
var columns \= columnify(data, options)
console.log(columns)

## Examples

### Columnify Objects

Objects are converted to a list of key/value pairs:

var data \= {
  "commander@0.6.1": 1,
  "minimatch@0.2.14": 3,
  "mkdirp@0.3.5": 2,
  "sigmund@1.0.0": 3
}

console.log(columnify(data))

#### Output:

```
KEY               VALUE
commander@0.6.1   1
minimatch@0.2.14  3
mkdirp@0.3.5      2
sigmund@1.0.0     3
```

### Custom Column Names

var data \= {
  "commander@0.6.1": 1,
  "minimatch@0.2.14": 3,
  "mkdirp@0.3.5": 2,
  "sigmund@1.0.0": 3
}

console.log(columnify(data, {columns: \['MODULE', 'COUNT'\]}))

#### Output:

```
MODULE            COUNT
commander@0.6.1   1
minimatch@0.2.14  3
mkdirp@0.3.5      2
sigmund@1.0.0     3
```

### Columnify Arrays of Objects

Column headings are extracted from the keys in supplied objects.

var columnify \= require('columnify')

var columns \= columnify(\[{
  name: 'mod1',
  version: '0.0.1'
}, {
  name: 'module2',
  version: '0.2.0'
}\])

console.log(columns)

#### Output:

```
NAME    VERSION
mod1    0.0.1  
module2 0.2.0  
```

### Filtering & Ordering Columns

By default, all properties are converted into columns, whether or not they exist on every object or not.

To explicitly specify which columns to include, and in which order, supply a "columns" or "include" array ("include" is just an alias).

var data \= \[{
  name: 'module1',
  description: 'some description',
  version: '0.0.1',
}, {
  name: 'module2',
  description: 'another description',
  version: '0.2.0',
}\]

var columns \= columnify(data, {
  columns: \['name', 'version'\]
})

console.log(columns)

#### Output:

```
NAME    VERSION
module1 0.0.1
module2 0.2.0
```

## Global and Per Column Options

You can set a number of options at a global level (ie. for all columns) or on a per column basis.

Set options on a per column basis by using the `config` option to specify individual columns:

var columns \= columnify(data, {
  optionName: optionValue,
  config: {
    columnName: {optionName: optionValue},
    columnName: {optionName: optionValue},
  }
})

### Maximum and Minimum Column Widths

As with all options, you can define the `maxWidth` and `minWidth` globally, or for specified columns. By default, wrapping will happen at word boundaries. Empty cells or those which do not fill the `minWidth` will be padded with spaces.

var columns \= columnify(\[{
  name: 'mod1',
  description: 'some description which happens to be far larger than the max',
  version: '0.0.1',
}, {
  name: 'module-two',
  description: 'another description larger than the max',
  version: '0.2.0',
}\], {
  minWidth: 20,
  config: {
    description: {maxWidth: 30}
  }
})

console.log(columns)

#### Output:

```
NAME                 DESCRIPTION                    VERSION             
mod1                 some description which happens 0.0.1               
                     to be far larger than the max                      
module-two           another description larger     0.2.0               
                     than the max                         
```

#### Maximum Line Width

You can set a hard maximum line width using the `maxLineWidth` option. Beyond this value data is unceremoniously truncated with no truncation marker.

This can either be a number or 'auto' to set the value to the width of stdout.

Setting this value to 'auto' prevent TTY-imposed line-wrapping when lines exceed the screen width.

#### Truncating Column Cells Instead of Wrapping

You can disable wrapping and instead truncate content at the maximum column width by using the `truncate` option. Truncation respects word boundaries. A truncation marker, `…`, will appear next to the last word in any truncated line.

var columns \= columnify(data, {
  truncate: true,
  config: {
    description: {
      maxWidth: 20
    }
  }
})

console.log(columns)

#### Output:

```
NAME       DESCRIPTION          VERSION
mod1       some description…    0.0.1  
module-two another description… 0.2.0  
```

### Align Right/Center

You can set the alignment of the column data by using the `align` option.

var data \= {
  "mocha@1.18.2": 1,
  "commander@2.0.0": 1,
  "debug@0.8.1": 1
}

columnify(data, {config: {value: {align: 'right'}}})

#### Output:

```
KEY                  VALUE
mocha@1.18.2             1
commander@2.0.0          1
debug@0.8.1              1
```

`align: 'center'` works in a similar way.

### Padding Character

Set a character to fill whitespace within columns with the `paddingChr` option.

var data \= {
  "shortKey": "veryVeryVeryVeryVeryLongVal",
  "veryVeryVeryVeryVeryLongKey": "shortVal"
}

columnify(data, { paddingChr: '.'})

#### Output:

```
KEY........................ VALUE......................
shortKey................... veryVeryVeryVeryVeryLongVal
veryVeryVeryVeryVeryLongKey shortVal...................
```

### Preserve Existing Newlines

By default, `columnify` sanitises text by replacing any occurance of 1 or more whitespace characters with a single space.

`columnify` can be configured to respect existing new line characters using the `preserveNewLines` option. Note this will still collapse all other whitespace.

var data \= \[{
  name: "glob@3.2.9",
  paths: \[
    "node\_modules/tap/node\_modules/glob",
    "node\_modules/tape/node\_modules/glob"
  \].join('\\n')
}, {
  name: "nopt@2.2.1",
  paths: \[
    "node\_modules/tap/node\_modules/nopt"
  \]
}, {
  name: "runforcover@0.0.2",
  paths: "node\_modules/tap/node\_modules/runforcover"
}\]

console.log(columnify(data, {preserveNewLines: true}))

#### Output:

```
NAME              PATHS
glob@3.2.9        node_modules/tap/node_modules/glob
                  node_modules/tape/node_modules/glob
nopt@2.2.1        node_modules/tap/node_modules/nopt
runforcover@0.0.2 node_modules/tap/node_modules/runforcover
```

Compare this with output without `preserveNewLines`:

console.log(columnify(data, {preserveNewLines: false}))
// or just
console.log(columnify(data))

```
NAME              PATHS
glob@3.2.9        node_modules/tap/node_modules/glob node_modules/tape/node_modules/glob
nopt@2.2.1        node_modules/tap/node_modules/nopt
runforcover@0.0.2 node_modules/tap/node_modules/runforcover
```

### Custom Truncation Marker

You can change the truncation marker to something other than the default `…` by using the `truncateMarker` option.

var columns \= columnify(data, {
  truncate: true,
  truncateMarker: '>',
  widths: {
    description: {
      maxWidth: 20
    }
  }
})

console.log(columns)

#### Output:

```
NAME       DESCRIPTION          VERSION
mod1       some description>    0.0.1  
module-two another description> 0.2.0  
```

### Custom Column Splitter

If your columns need some bling, you can split columns with custom characters by using the `columnSplitter` option.

var columns \= columnify(data, {
  columnSplitter: ' | '
})

console.log(columns)

#### Output:

```
NAME       | DESCRIPTION                                                  | VERSION
mod1       | some description which happens to be far larger than the max | 0.0.1
module-two | another description larger than the max                      | 0.2.0
```

### Control Header Display

Control whether column headers are displayed by using the `showHeaders` option.

var columns \= columnify(data, {
  showHeaders: false
})

This also works well for hiding a single column header, like an `id` column:

var columns \= columnify(data, {
  config: {
    id: { showHeaders: false }
  }
})

### Transforming Column Data and Headers

If you need to modify the presentation of column content or heading content there are two useful options for doing that: `dataTransform` and `headingTransform`. Both of these take a function and need to return a valid string.

var columns \= columnify(\[{
    name: 'mod1',
    description: 'SOME DESCRIPTION TEXT.'
}, {
    name: 'module-two',
    description: 'SOME SLIGHTLY LONGER DESCRIPTION TEXT.'
}\], {
    dataTransform: function(data) {
        return data.toLowerCase()
    },
    config: {
        name: {
            headingTransform: function(heading) {
              heading \= "module " + heading
              return "\*" +  heading.toUpperCase() + "\*"
            }
        }
    }
})

#### Output:

```
*MODULE NAME* DESCRIPTION                           
mod1          some description text.                
module-two    some slightly longer description text.
```

## Multibyte Character Support

`columnify` uses [mycoboco/wcwidth.js](https://github.com/mycoboco/wcwidth.js) to calculate length of multibyte characters:

var data \= \[{
  name: 'module-one',
  description: 'some description',
  version: '0.0.1',
}, {
  name: '这是一个很长的名字的模块',
  description: '这真的是一个描述的内容这个描述很长',
  version: "0.3.3"
}\]

console.log(columnify(data))

#### Without multibyte handling:

i.e. before columnify added this feature

```
NAME         DESCRIPTION       VERSION
module-one   some description  0.0.1
这是一个很长的名字的模块 这真的是一个描述的内容这个描述很长 0.3.3
```

#### With multibyte handling:

```
NAME                     DESCRIPTION                        VERSION
module-one               some description                   0.0.1
这是一个很长的名字的模块 这真的是一个描述的内容这个描述很长 0.3.3
```

## Contributions

```
 project  : columnify
 repo age : 2 years, 2 months
 active   : 38 days
 commits  : 148
 files    : 56
 authors  :
   114Tim Oxley           77.0%
     8Tim                 5.4%
     7Arjun Mehta         4.7%
     6Dany                4.1%
     5Wei Gao             3.4%
     4Matias Singers      2.7%
     2Dany Shaanan        1.4%
     1Seth Miller         0.7%
     1Isaac Z. Schlueter  0.7%
```

## License

MIT