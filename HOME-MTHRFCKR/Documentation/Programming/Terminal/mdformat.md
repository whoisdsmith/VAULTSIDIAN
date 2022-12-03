Toggle table of contents sidebar

## Installing[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#installing "Permalink to this headline")

Install with [CommonMark](https://spec.commonmark.org/current/) support:

Alternatively install with [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/) support:

Or with [Markedly Structured Text (MyST)](https://myst-parser.readthedocs.io/en/latest/using/syntax.html) support:

pip install mdformat-myst

Warning

The formatting style produced by mdformat may change in each version. It is recommended to pin mdformat dependency version.

## Command line usage[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#command-line-usage "Permalink to this headline")

### Format files[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#format-files "Permalink to this headline")

Format files `README.md` and `CHANGELOG.md` in place

mdformat README.md CHANGELOG.md

Format `.md` files in current working directory recursively

Read Markdown from standard input until `EOF`. Write formatted Markdown to standard output.

### Check formatting[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#check-formatting "Permalink to this headline")

mdformat --check README.md CHANGELOG.md

This will not apply any changes to the files. If a file is not properly formatted, the exit code will be non-zero.

### Options[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#options "Permalink to this headline")

foo@bar:~$ mdformat --help
usage: mdformat \[-h\] \[--check\] \[--version\] \[--number\] \[--wrap {keep,no,INTEGER}\] \[--end-of-line {lf,crlf}\] \[paths \[paths ...\]\]

CommonMark compliant Markdown formatter

positional arguments:
 paths                 files to format

optional arguments:
 -h, --help            show this help message and exit
 --check               do not apply changes to files
 --version             show program's version number and exit
 --number              apply consecutive numbering to ordered lists
 --wrap {keep,no,INTEGER}
 paragraph word wrap mode (default: keep)
 --end-of-line {lf,crlf}
 output file line ending mode (default: lf)

## Python API usage[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#python-api-usage "Permalink to this headline")

### Format text[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#format-text "Permalink to this headline")

import mdformat

unformatted \= "\\n\\n\# A header\\n\\n"
formatted \= mdformat.text(unformatted)
assert formatted \== "# A header\\n"

### Format a file[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#format-a-file "Permalink to this headline")

Format file `README.md` in place:

import mdformat

\# Input filepath as a string...
mdformat.file("README.md")

\# ...or a pathlib.Path object
import pathlib

filepath \= pathlib.Path("README.md")
mdformat.file(filepath)

### Options[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#id1 "Permalink to this headline")

All formatting style modifying options available in the CLI are also available in the Python API, with equivalent option names:

import mdformat

mdformat.file(
    "FILENAME.md",
    options\={
        "number": True,  \# switch on consecutive numbering of ordered lists
        "wrap": 60,  \# set word wrap width to 60 characters
    }
)

## Usage as a pre-commit hook[¶](https://mdformat.readthedocs.io/en/stable/users/installation_and_usage.html#usage-as-a-pre-commit-hook "Permalink to this headline")

`mdformat` can be used as a [pre-commit](https://github.com/pre-commit/pre-commit) hook. Add the following to your project’s `.pre-commit-config.yaml` to enable this:

\- repo: https://github.com/executablebooks/mdformat
 rev: 0.7.13 \# Use the ref you want to point at
 hooks:
 \- id: mdformat
 \# Optionally add plugins
 additional\_dependencies:
 \- mdformat-gfm
 \- mdformat-black