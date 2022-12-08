---
tags:: occ
---
# Manage logging configuration

 Usage

 `log:manage [--backend BACKEND] [--level LEVEL] [--timezone TIMEZONE]`

manage logging configuration

 Options

 `--backend`

set the logging backend [file, syslog, errorlog, systemd]

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--level`

set the log level [debug, info, warning, error, fatal]

 Accept value: yes

 Is value required: yes

 Is multiple: no

 Default: `NULL`

 `--timezone`

set the logging timezone

 Accept value: yes

 Is value required: yes

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

`log:tail`

----------