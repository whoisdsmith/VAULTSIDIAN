# Read and modify user settings

 Usage

 `user:setting [--output [OUTPUT]] [--ignore-missing-user] [--default-value DEFAULT-VALUE] [--update-only] [--delete] [--error-if-not-exists] [--] <uid> [<app> [<key> [<value>]]]`

Read and modify user settings

 Arguments

 `uid`

User ID used to login

 Is required: yes

 Is array: no

 Default: `NULL`

 `app`

Restrict the settings to a given app

 Is required: no

 Is array: no

 Default: `''`

 `key`

Setting key to set, get or delete

 Is required: no

 Is array: no

 Default: `''`

 `value`

The new value of the setting

 Is required: no

 Is array: no

 Default: `NULL`

 Options

 `--output`

Output format (plain, json or json_pretty, default is plain)

 Accept value: yes

 Is value required: no

 Is multiple: no

 Default: `'plain'`

 `--ignore-missing-user`

Use this option to ignore errors when the user does not exist

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--default-value`

(Only applicable on get) If no default value is set and the config does not exist, the command will exit with 1

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

 `--delete`

Specify this option to delete the config

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--error-if-not-exists`

Checks whether the setting exists before deleting it

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

`versions:cleanup`

------------------