---
tags:: occ
---
# Display help for a command

 Usage

 `help [--format FORMAT] [--raw] [--] [<command_name>]`

The help command displays help for a given command:

  php /index.php help list

You can also output the help in other formats by using the --format option:

  php /index.php help --format=xml list

To display the list of available commands, please use the list command.

 Arguments

 `command_name`

The command name

 Is required: no

 Is array: no

 Default: `'help'`

 Options

 `--format`

The output format (txt, xml, json, or md)

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `'txt'`

 `--raw`

To output raw command help

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--help|-h`

Display this help message

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--quiet|-q`

Do not output any message

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--verbose|-v|-vv|-vvv`

Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--version|-V`

Display this application version

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--ansi`

Force ANSI output

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--no-ansi`

Disable ANSI output

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--no-interaction|-n`

Do not ask any interactive question

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--no-warnings`

Skip global warnings, show command output only

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

`list`

------