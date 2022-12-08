---
tags:: occ
---
# Prints a CSV entry with some usage information of the user:

userId,date,assignedQuota,usedQuota,numFiles,numShares,numUploads,numDownloads

"admin","2017-09-18T09:00:01+00:00",5368709120,786432000,1024,23,1400,5678

 Usage

 `usage-report:generate [--field-separator FIELD-SEPARATOR] [--date-format DATE-FORMAT] [--last-login] [--display-name] [--] [<user-id>]`

Prints a CSV entry with some usage information of the user:

userId,date,assignedQuota,usedQuota,numFiles,numShares,numUploads,numDownloads

"admin","2017-09-18T09:00:01+00:00",5368709120,786432000,1024,23,1400,5678

 Arguments

 `user-id`

User to generate the report for, if none is given the report is generated for all users

 Is required: no

 Is array: no

 Default: `NULL`

 Options

 `--field-separator`

Separator for the fields in the list

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `','`

 `--date-format`

Date format of the entries (see [http://php.net/manual/en/function.date.php](http://php.net/manual/en/function.date.php) for more information)

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `'c'`

 `--last-login`

Should the last login date be included in the report

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--display-name`

Should the display name be included in the report

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

`user:add`

----------