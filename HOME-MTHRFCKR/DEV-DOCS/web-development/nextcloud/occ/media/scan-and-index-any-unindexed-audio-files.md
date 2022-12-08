---
tags:: occ
---
# Scan and index any unindexed audio files

 Usage

 `music:scan [--all] [--group GROUP] [--debug] [--clean-obsolete] [--rescan] [--rescan-modified] [--folder [FOLDER]] [--] [<user_id>...]`

scan and index any unindexed audio files

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

 `--debug`

will run the scan in debug mode (memory usage)

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--clean-obsolete`

also check availability of any previously scanned tracks, removing obsolete entries

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--rescan`

rescan also any previously scanned tracks

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--rescan-modified`

rescan files which have mofication time later than the previous scan time (new files not scanned)

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--folder`

scan only files within this folder (path is relative to the user home folder)

 Accept value: yes

 Is value required: no

 Is multiple: no

 Default: `NULL`

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

`notification:generate`

-----------------------