---
tags:: occ
---
# Adds a user

 Usage

 `user:add [--password-from-env] [--display-name [DISPLAY-NAME]] [-g|--group [GROUP]] [--] <uid>`

adds a user

 Arguments

 `uid`

User ID used to login (must only contain a-z, A-Z, 0-9, -, _ and @)

 Is required: yes

 Is array: no

 Default: `NULL`

 Options

 `--password-from-env`

read password from environment variable OC_PASS

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--display-name`

User name used in the web UI (can contain any characters)

 Accept value: yes

 Is value required: no

 Is multiple: no

 Default: `NULL`

 `--group|-g`

groups the user should be added to (The group will be created if it does not exist)

 Accept value: yes

 Is value required: no

 Is multiple: yes

 Default: `array ()`

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

`user:add-app-password`

-----------------------