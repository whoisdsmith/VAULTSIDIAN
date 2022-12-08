# Configure advanced permissions for a configured group folder

Usage

`groupfolders:permissions [-e|--enable] [-d|--disable] [-m|--manage-add] [-r|--manage-remove] [-u|--user USER] [-g|--group GROUP] [-t|--test] [-`

`-output [OUTPUT]] [--] <folder_id> [<path> [<permissions>...]]`

Configure advanced permissions for a configured group folder

 Arguments

 `folder_id`

Id of the folder to configure

 Is required: yes

 Is array: no

 Default: `NULL`

 `path`

The path within the folder to set permissions for

 Is required: no

 Is array: no

 Default: `NULL`

 `permissions`

 Is required: no

 Is array: yes

 Default: `array ()`

 Options

 `--enable|-e`

Enable advanced permissions for the folder

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--disable|-d`

Disable advanced permissions for the folder

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--manage-add|-m`

Add manage permission for user or group

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--manage-remove|-r`

Remove manage permission for user or group

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--user|-u`

The user to configure the permissions for

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--group|-g`

The group to configure the permissions for

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--test|-t`

Test the permissions for the set path

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

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

`groupfolders:quota`

--------------------