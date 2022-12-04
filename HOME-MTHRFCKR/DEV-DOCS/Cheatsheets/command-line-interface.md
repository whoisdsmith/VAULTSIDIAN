# Command Line Interface (CLI) | Day One Help

> ## Excerpt
> Instructions for installing and using CLI with Day One 2.0

---

**Note: The following information applies to Day One Mac 2.1.2 and later.**

## Name

**dayone2** - Command line interface for the Day One journaling application.

## Install

Use this to install the CLI tool (You only ever need to do this once, even for future versions):

```
sudo bash /Applications/Day\ One.app/Contents/Resources/install_cli.sh
```

Note: You may need to enter your macOS device login password.

## Description

The **dayone2** tool provides a way to interact with your Day One journal file through the command line. It is typically used for custom import scripts and utilities.

**dayone2** will only work properly if you have purchased the Day One application and have run it at least one time on your computer.

A command must always be specified. Supported command is **new**. The entry text is read from stdin.

Run `**dayone2 -h**` in Terminal for these instructions as well.

## Usage

**dayone2 \[options\] command**

## Commands

**new \[text\] \[text\]**

Creates new entry with optional text. Every text argument will be separated by a single space when placed into the new entry. If no text arguments are provided then standard input is used by default for the entry text. Use --no-stdin to override this behavior.

## Options

The options must come before the command (**new**). For example:

**`dayone2`** `**--journal** [journal name] **--photos** [photo1][photo2]**--** **new** [text]`

———

**_\-p, --photos:_**

Path to one or more photo file(s). If desired you can use \[{photo}\] in entry text to position photo. Multiple photos are supported with the Plus account status (up to 10) and Premium account status (up to 30).

If multiple photos are added. a -- must be placed at the end of the list prior to the command, otherwise the command would be considered a photo path instead.

Example:

```
-p photo1 photo2
```

———

**_\-z, --time-zone:_**

Time zone to use, for a list see /usr/share/zoneinfo. The name is expected to be a name from the IANA Time Zone Database. (see [http://www.iana.org/time-zones](http://www.iana.org/time-zones) or /usr/share/zoneinfo) Alternatively, you can specify the name as a GMT offset.

Examples:

```
-z America/Anchorage
```

```
-z Australia/Victoria
```

```
-z GMT-0700
```

———

**_\-s, --starred:_**

Star entry if flag is present.

Example:

```
--starred
```

———

**_\-d, --date:_**

Date to use, otherwise will use today/now. Example Format (time/seconds are optional):

```
yyyy-mm-dd [hh:mm[:ss]] [AM|PM]
```

Uses current system time zone unless you use the --timeZone option. Other formats are possible, such as 'Next Tuesday' or '12/30/2016', etc.

Example Use:

```
--date='2015-06-01 15:53:10'
```

———

**_\--coordinate:_**

Coordinate of entry location, must provide two numbers with the first a latitude, and the second a longitude.

Example:

```
--coordinate 32.513 35.621
```

———

**_\--isoDate:_**

Date to use in ISO 8601 format. Format:

```
yyyy-mm-ddThh:mm:ssZ
```

Always interprets the time in the UTC time zone in the gregorian calendar. Entry its self will still use current system time zone unless --timeZone option is used.

Example:

```
--isoDate=2015-06-01T15:53:10Z
```

———

**_\-j, --journal:_**

Name of journal for entry. Journal must already exist. If not specified then the default journal will be used.

———

**_\-t, --tags:_**

One or more tags for entry.

Example:

```
--tags Soccer\ Match Win
```

This example would assign the tags 'Soccer Match' and 'Win' to the entry.

Using -- will stop parsing options, you can use this at the end of a list of tags if needed.

## Environment

**DAYONE\_APP\_PATH:**  
If the DAYONE\_APP\_PATH environment variable is defined we will look for Day One at the path in variable. The Day One app is needed for CLI to work.

These paths are searched in order, first one that works is the one used:

1. DAYONE\_APP\_PATH
    
2. /Applications/Day One.app
    
3. Asking system for path to app for com.bloombuilt.dayone-mac
