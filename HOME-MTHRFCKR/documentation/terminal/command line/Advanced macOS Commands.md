
## Advanced macOS Command-Line Tools

macOS is fortunate to have access to the huge arsenal of standard Unix tools. There are also a good number of macOS-specific command-line utilities that provide unique macOS functionality. To view the full documentation for any of these commands, run `man <command>`.

#### `caffeinate` - set Mac sleep behavior

Running `caffeinate` with no flags or arguments prevents your Mac from going to sleep as long as the command continues to run.

`caffeinate -u -t <seconds>` prevents sleep for the specified number of seconds.

Adding the `-d` flag also prevents the display from going to sleep.

Specifying an existing process with `-w <pid>` automatically exits the caffeinate command once the specified process exits.

Passing a command with `caffeinate <command>` starts the given command in a new process and will prevent sleep until that process exits.

#### `textutil` - document file converter

`textutil` can convert files to and from Microsoft Word, plain text, rich text, and HTML formats.

`textutil -convert html journal.doc` converts `journal.doc` into `journal.html`.

The possible values for `-convert` are: `txt`, `html`, `rtf`, `rtfd`, `doc`, `docx`.

#### `mdfind` - search with Spotlight

`mdfind <query>` performs a keyword-based Spotlight search with the given query.

`mdfind -name <name>` searches for all files matching the given name.

The `-onlyin <dir>` flag restricts the search to the given directory.

#### `networkQuality` - measure Internet speed

Run `networkQuality` to run an Internet speed test from your Mac.

Add the `-v` flag to view more detailed information.

Use the `-i` flag to run the network test on a specific network interface.

#### `screencapture` - take screenshots

`screencapture -c` takes a screenshot and copies it to the clipboard.

`screencapture <file>` takes a screenshot and saves it to the given file.

Add the `-T <seconds>` flag to take the screenshot after the given delay in seconds.

#### `pbcopy`, `pbpaste` - interact with system clipboard

`<command> | pbcopy` copies the output of the command to the clipboard.

`pbpaste` outputs the contents of the clipboard to stdout.

#### `taskpolicy` - control scheduling of processes

`taskpolicy -b <command>` starts executing the given command in the background. On Apple silicon Macs, the process will only run on the efficiency cores.

`taskpolicy -b -p <pid>` downgrades an existing process to run in the background.

`taskpolicy -B -p <pid>` removes the specified process from running in the background. On Apple silicon Macs, the process may now run on the efficiency or performance cores. Note that this only works on processes that have been downgraded to the background, and not processes that started in the background.

`taskpolicy -s <command>` starts the given command in the suspended state. This is useful to allow a debugger to attach to the process right at the start of execution.

#### `say` - text-to-speech engine

`say <message>` announces the given message.

`say -f input.txt -o output.aiff` will create an audiobook from the given text file.

#### `sips` - image manipulation

`sips -z <height> <width> <image>` resizes the specified image, ignoring the previous aspect ratio.

`sips -Z <size> <image>` resizes the largest side of the specified image, preserving the aspect ratio.

`sips -r <degrees> <image>` rotate the image by the specified degrees.

#### `open` - open files and applications

`open -a <app> <file>` opens the given file with the specified application.

`open .` opens the current directory in a new Finder window.

#### `pmset` - configure power management

`pmset -g` prints all available power configuration information.

`pmset -g assertions` displays information about power-related assertions made by other processes. This can be useful for finding a process that is preventing your Mac from going to sleep.

`pmset -g thermlog` displays information about any processes that have been throttled (useful when running benchmarks).

`pmset displaysleepnow` immediately puts the display to sleep without putting the rest of the system to sleep.

`pmset sleepnow` immediately puts the entire system to sleep.

#### `networksetup` - configure network settings

`networksetup -listnetworkserviceorder` prints a list of available network services.

`networksetup -getinfo <networkservice>` prints information about the specified network service.

`networksetup -getdnsservers <networkservice>` prints the DNS servers for the specified network service.

`networksetup -setairportnetwork <device> <network> [password]` joins the specified Wi-Fi network. (In most cases, the <device> argument should be "en0".)

#### `softwareupdate` - manage OS updates

`softwareupdate --list` prints out available software updates.

`sudo softwareupdate -ia` installs all available updates.

`softwareupdate --fetch-full-installer --full-installer-version <version>` tries to download the full installer of the specified macOS version to /Applications.
