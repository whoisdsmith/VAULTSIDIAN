---
tags:: occ
---
# All files and folders are moved to another user - outgoing shares and incoming user file shares (optionally) are moved as well.

 Usage

 `files:transfer-ownership [--path PATH] [--move] [--transfer-incoming-shares [TRANSFER-INCOMING-SHARES]] [--] <source-user> <destination-user>`

All files and folders are moved to another user - outgoing shares and incoming user file shares (optionally) are moved as well.

 Arguments

 `source-user`

owner of files which shall be moved

 Is required: yes

 Is array: no

 Default: `NULL`

 `destination-user`

user who will be the new owner of the files

 Is required: yes

 Is array: no

 Default: `NULL`

 Options

 `--path`

selectively provide the path to transfer. For example --path="folder_name"

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `''`

 `--move`

move data from source user to root directory of destination user, which must be empty

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--transfer-incoming-shares`

transfer incoming user file shares to destination user. Usage: --transfer-incoming-shares=1 (value required)

 Accept value: yes

 Is value required: no

 Is multiple: no

 Default: `'2'`

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

`group:add`

-----------