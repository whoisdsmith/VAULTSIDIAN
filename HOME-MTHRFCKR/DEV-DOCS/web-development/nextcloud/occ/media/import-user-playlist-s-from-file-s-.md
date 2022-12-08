---
tags:: occ
---
# Import user playlist(s) from file(s)

 Usage

 `music:playlist-import [--all] [--group GROUP] [--file FILE] [--overwrite] [--append] [--] [<user_id>...]`

import user playlist(s) from file(s)

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

 `--file`

path of the playlist file, relative to the user home folder;  and ? are treated as wildcards within the file name but not on the directory name

 Accept value: yes

 Is value required: yes

 Is multiple: yes

 Default: `array ()`

 `--overwrite`

overwrite the target playlist if it already exists

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--append`

append imported tracks to an existing playlist if found

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

`music:podcast-add`

-------------------