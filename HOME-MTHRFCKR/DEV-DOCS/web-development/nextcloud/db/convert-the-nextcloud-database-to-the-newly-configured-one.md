# Convert the Nextcloud database to the newly configured one

 Usage

 `db:convert-type [--port PORT] [--password PASSWORD] [--clear-schema] [--all-apps] [--chunk-size CHUNK-SIZE] [--] <type> <username> <hostname> <

database>`

Convert the Nextcloud database to the newly configured one

 Arguments

 `type`

the type of the database to convert to

 Is required: yes

 Is array: no

 Default: `NULL`

 `username`

the username of the database to convert to

 Is required: yes

 Is array: no

 Default: `NULL`

 `hostname`

the hostname of the database to convert to

 Is required: yes

 Is array: no

 Default: `NULL`

 `database`

the name of the database to convert to

 Is required: yes

 Is array: no

 Default: `NULL`

 Options

 `--port`

the port of the database to convert to

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--password`

the password of the database to convert to. Will be asked when not specified. Can also be passed via stdin.

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--clear-schema`

remove all tables from the destination database

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--all-apps`

whether to create schema for all apps instead of only installed apps

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--chunk-size`

the maximum number of database rows to handle in a single query, bigger tables will be handled in chunks of this size. Lower this if the process r

uns out of memory during conversion.

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `'1000'`

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

`duplicates:clear`

------------------