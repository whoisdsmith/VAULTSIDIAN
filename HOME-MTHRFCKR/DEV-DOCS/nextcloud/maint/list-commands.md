---
tags:: occ
---
# List commands

 Usage

 `list [--raw] [--format FORMAT] [--] [<namespace>]`

The list command lists all commands:

  php /index.php list

You can also display the commands for a specific namespace:

  php /index.php list test

You can also output the information in other formats by using the --format option:

  php /index.php list --format=xml

It's also possible to get raw list of commands (useful for embedding command runner):

  php /index.php list --raw

 Arguments

 `namespace`

The namespace name

 Is required: no

 Is array: no

 Default: `NULL`

 Options

 `--raw`

To output raw command list

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--format`

The output format (txt, xml, json, or md)

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `'txt'`

`status`

--------