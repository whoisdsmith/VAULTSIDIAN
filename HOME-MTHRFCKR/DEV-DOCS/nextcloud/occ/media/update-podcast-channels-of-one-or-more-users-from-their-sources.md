---
tags:: occ
---
# Update podcast channels of one or more users from their sources

 Usage

 `music:podcast-update [--all] [--group GROUP] [--older-than OLDER-THAN] [--force] [--] [<user_id>...]`

update podcast channels of one or more users from their sources

 Arguments

 `user_id`

specify one or more targeted users

 Is required: no

 Is array: yes

 Default: `array ()`

 Options

 `--all`

target all known users

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--group`

specify a targeted group to include all users of that group

 Accept value: yes

 Is value required: yes

 Is multiple: yes

 Default: `array ()`

 `--older-than`

check updates only for channels which have not been checked for this many hours (sub-hour resolution supported with decimals)

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--force`

update episodes even if there doesn't appear to be any changes

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

`music:reset-cache`

-------------------