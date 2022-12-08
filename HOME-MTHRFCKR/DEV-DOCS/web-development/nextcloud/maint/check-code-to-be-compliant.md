---
tags:: occ
---
# Check code to be compliant

 Usage

 `app:check-code [-c|--checker CHECKER] [--skip-checkers] [--skip-validate-info] [--] <app-id>`

check code to be compliant

 Arguments

 `app-id`

check the specified app

 Is required: yes

 Is array: no

 Default: `NULL`

 Options

 `--checker|-c`

enable the specified checker(s)

 Accept value: yes

 Is value required: yes

 Is multiple: yes

 Default: `array (  0 => 'private',  1 => 'deprecation',  2 => 'strong-comparison',)`

 `--skip-checkers`

skips the the code checkers to only check info.xml, language and database schema

 Accept value: no

 Is value required: no

 Is multiple: no

 Default: `false`

 `--skip-validate-info`

skips the info.xml/version check

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

`app:disable`

-------------