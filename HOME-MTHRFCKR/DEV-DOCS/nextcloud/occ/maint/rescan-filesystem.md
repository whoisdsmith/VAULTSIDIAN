---
tags:: occ
---
# Rescan filesystem

 Usage

 `files:scan [--output [OUTPUT]] [-p|--path PATH] [--all] [--unscanned] [--shallow] [--home-only] [--] [<user_id>...]`

rescan filesystem

 Arguments

 `user_id`

will rescan all files of the given user(s)

 Is required: no

 Is array: yes

 Default: `array ()`

 Options

 `--output`

Output format (plain, json or json_pretty, default is plain)

 Accept value: yes

 Is value required: no

 Is multiple: no

 Default: `'plain'`

 `--path|-p`

limit rescan to this path, eg. --path="/alice/files/Music", the user_id is determined by the path and the user_id parameter and --all are ignored

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--all`

will rescan all files of all known users

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--unscanned`

only scan files which are marked as not fully scanned

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--shallow`

do not scan folders recursively

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--home-only`

only scan the home storage, ignoring any mounted external storage or share

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

`files:scan-app-data`

---------------------

rescan the AppData folder

 Usage

 `files:scan-app-data [--output [OUTPUT]] [--] [<folder>]`

rescan the AppData folder

 Arguments

 `folder`

The appdata subfolder to scan

 Is required: no

 Is array: no

 Default: `''`

 Options

 `--output`

Output format (plain, json or json_pretty, default is plain)

 Accept value: yes

 Is value required: no

 Is multiple: no

 Default: `'plain'`

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

`files:transfer-ownership`

--------------------------