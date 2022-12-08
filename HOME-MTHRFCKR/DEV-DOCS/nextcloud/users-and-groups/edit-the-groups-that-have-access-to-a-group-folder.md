# Edit the groups that have access to a group folder

 Usage

 `groupfolders:group [-d|--delete] [--output [OUTPUT]] [--] <folder_id> <group> [<permissions>...]`

Edit the groups that have access to a group folder

 Arguments

 `folder_id`

Id of the folder to configure

 Is required: yes

 Is array: no

 Default: `NULL`

 `group`

The group to configure

 Is required: yes

 Is array: no

 Default: `NULL`

 `permissions`

The permissions to set for the group, leave empty for read only

 Is required: no

 Is array: yes

 Default: `array ()`

 Options

 `--delete|-d`

Remove access for the group

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

`groupfolders:list`

-------------------