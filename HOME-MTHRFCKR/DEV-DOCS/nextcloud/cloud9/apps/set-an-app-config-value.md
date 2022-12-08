---
tags:: apps
---
# Set an app config value

 Usage

 `config:app:set [--output [OUTPUT]] [--value VALUE] [--update-only] [--] <app> <name>`

Set an app config value

 Arguments

 `app`

Name of the app

 Is required: yes

 Is array: no

 Default: `NULL`

 `name`

Name of the config to set

 Is required: yes

 Is array: no

 Default: `NULL`

 Options

 `--output`

Output format (plain, json or json_pretty, default is plain)

 Accept value: yes

 Is value required: no

 Is multiple: no

 Default: `'plain'`

 `--value`

The new value of the config

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--update-only`

Only updates the value, if it is not set before, it is not being added

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

`config:import`

---------------

Import a list of configs

 Usage

 `config:import [<file>]`

Import a list of configs

 Arguments

 `file`

File with the json array to import

 Is required: no

 Is array: no

 Default: `NULL`

 Options

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

`config:list`

-------------