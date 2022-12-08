# Export user playlist(s) to file(s)

 Usage

 `music:playlist-export [--all] [--group GROUP] [--list-id LIST-ID] [--list-name LIST-NAME] [--all-lists] [--dir DIR] [--overwrite] [--] [<user_i

d>...]`

export user playlist(s) to file(s)

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

 `--list-id`

ID of the playlist to export

 Accept value: yes

 Is value required: yes

 Is multiple: yes

 Default: `array ()`

 `--list-name`

name of the playlist to export

 Accept value: yes

 Is value required: yes

 Is multiple: yes

 Default: `array ()`

 `--all-lists`

export all playlists of the user

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--dir`

target directory, relative to the user home folder (the dir must exist)

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `''`

 `--overwrite`

overwrite the target file if it already exists

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

`music:playlist-import`

-----------------------