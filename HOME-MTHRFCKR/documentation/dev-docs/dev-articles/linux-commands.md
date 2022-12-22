---
created: 2022-08-07T13:17:14 (UTC -04:00)
tags: [Xmind,mindmap,mind map,mind mapping,mind mapping software,free mind mapping software,work from home,WFH,remote]
source: https://www.xmind.net/m/WwtB/
author: Xmind Ltd.
---

# LINUX Commands - Xmind - Mind Mapping Software

---
1.  Shell Job Control
    1.  jobs
        1.  List your jobs.
    2.  &
        1.  Run a job in the background.
    3.  ^Z
        1.  Suspend the current (foreground) job.
    4.  suspend
        1.  Suspend a shell.
    5.  fg
        1.  Unsuspend a job: bring it into the foreground.
    6.  bg
        1.  Make a suspended job run in the background.
2.  Basic File Operations
    1.  ls
        1.  List files in a directory.
    2.  cp
        1.  Copy a file.
    3.  mv
        1.  Rename (“move”) a file.
    4.  rm
        1.  Delete (“remove”) a file.
    5.  ln
        1.  Create links (alternative names) to a file.
    6.  shred
        1.  Completely erase a file when the file is deleted
3.  Directory Operations
    1.  cd
        1.  Change your current directory.
    2.  pwd
        1.  Print the name of your current directory, i.e., “where you are now” in the filesystem.
    3.  basename
        1.  Print the final part of a file path.
    4.  dirname
        1.  Print a file path without its final part.
    5.  mkdir
        1.  Create (make) a directory.
    6.  rmdir
        1.  Delete (remove) an empty directory.
    7.  rm -r
        1.  Delete a nonempty directory and its contents.
4.  File Viewing
    1.  cat
        1.  View files in their entirety.
    2.  less
        1.  View text files one page at a time.
    3.  head
        1.  View the first lines of a text file.
    4.  tail
        1.  View the last lines of a text file.
    5.  nl
        1.  View text files with their lines numbered.
    6.  strings
        1.  Display text that’s embedded in a binary file.
    7.  od
        1.  View data in octal (or other formats).
    8.  xxd
        1.  View data in hexadecimal.
    9.  acroread
        1.  View PDF files.
    10.  gv
        1.  View PostScript or PDF files.
    11.  xdvi
        1.  View TeX DVI files.
5.  File Creation and Editing
    1.  emacs
        1.  Text editor from Free Software Foundation.
    2.  vim
        1.  Text editor, extension of Unix vi.
    3.  soffice
        1.  Office suite for editing Microsoft Word, Excel, and PowerPoint documents.
    4.  abiword
        1.  Edit Microsoft Word documents.
    5.  gnumeric
        1.  Edit Excel spreadsheets.
6.  File Properties
    1.  stat
        1.  Display attributes of files and directories.
    2.  wc
        1.  Count bytes, words, lines in a file.
    3.  du
        1.  Measure disk usage of files and directories.
    4.  file
        1.  Identify (guess) the type of a file.
    5.  touch
        1.  Change timestamps of files and directories.
    6.  chown
        1.  Change owner of files and directories.
    7.  chgrp
        1.  Change group ownership of files and directories.
    8.  chmod
        1.  Change protection mode of files and directories.
    9.  umask
        1.  Set a default mode for new files and directories.
    10.  chattr
        1.  Change extended attributes of files and directories.
    11.  lsattr
        1.  List extended attributes of files and directories.
7.  File Location
    1.  find
        1.  Locate files in a directory hierarchy.
    2.  xargs
        1.  Process a list of located files (and much more).
    3.  locate
        1.  Create an index of files, and search the index for string.
    4.  which
        1.  Locate executables in your search path (command).
    5.  type
        1.  Locate executables in your search path (bash built-in).
    6.  whereis
        1.  Locate executables, documentation, and source files.
8.  File Text Manipulation
    1.  grep
        1.  Find lines in a file that match a regular expression.
    2.  cut
        1.  Extract columns from a file.
    3.  paste
        1.  Append columns.
    4.  tr
        1.  Translate characters into other characters.
    5.  sort
        1.  Sort lines of text by various criteria.
    6.  uniq
        1.  Locate identical lines in a file.
    7.  tee
        1.  Copy a file and print it on standard output, simultaneously.
9.  File Compression and Packaging
    1.  tar
        1.  Package multiple files into a single file.
    2.  gzip
        1.  Compress files with GNU Zip.
    3.  gunzip
        1.  Uncompress GNU Zip files.
    4.  bzip2
        1.  Compress files in BZip format.
    5.  bunzip2
        1.  Uncompress BZip files.
    6.  bzcat
        1.  Compress/uncompress BZip files via standard input/output.
    7.  compress
        1.  Compress files with traditional Unix compression.
    8.  uncompress
        1.  Uncompress files with traditional Unix compression.
    9.  zcat
        1.  Compress/uncompress file via standard input/output (gzip or compress).
    10.  zip
        1.  Compress files in Windows Zip format.
    11.  unzip
        1.  Uncompress Windows Zip files.
    12.  metamail
        1.  Extract MIME data to files.
10.  File Comparison
    1.  diff
        1.  Line-by-line comparison of two files or directories.
    2.  comm
        1.  Line-by-line comparison of two sorted files.
    3.  cmp
        1.  Byte-by-byte comparison of two files.
    4.  md5sum
        1.  Compute a checksum of the given files (MD5).
11.  Printing
    1.  lpr
        1.  Print a file.
    2.  lpq
        1.  View the print queue.
    3.  lprm
        1.  Remove a print job from the queue.
12.  Spell Checking
    1.  look
        1.  Look up the spelling of a word quickly.
    2.  aspell
        1.  Interactive spelling checker.
    3.  spell
        1.  Batch spelling checker.
13.  Disks and Filesystems
    1.  df
        1.  Display available space on mounted filesystems.
    2.  mount
        1.  Make a disk partition accessible.
    3.  umount
        1.  Unmount a disk partition (make it inaccessible).
    4.  fsck
        1.  Check a disk partition for errors.
    5.  sync
        1.  Flush all disk caches to disk.
    6.  lshw
    7.  inxi
    8.  lsblk
14.  Backups and Remote Storage
    1.  dump
        1.  Write a disk partition to a backup medium.
    2.  restore
        1.  Restore the results of a dump.
    3.  cdrecord
        1.  Burn a CD, DVD, or Blu-ray disc.
    4.  rsync
        1.  Mirror a set of files onto another device or host.
    5.  mt
        1.  Control a tape drive.
15.  Viewing Processes
    1.  ps
        1.  List process.
    2.  uptime
        1.  View the system load.
    3.  w
        1.  List active processes for all users.
    4.  top
        1.  Monitor resource-intensive processes interactively.
    5.  htop
    6.  iotop
    7.  powertop
    8.  gnome-system-monitor
        1.  Monitor system load and processes graphically.
    9.  xload
        1.  Simple, graphical monitor of system load.
    10.  free
        1.  Display free memory.
    11.  pidof
        1.  Command, which looks up and prints the PID of a process by its name
    12.  nmon
16.  check
    1.  ssh
    2.  munin - monitoring
17.  Controlling Processes
    1.  kill
        1.  Terminate a process (or send it a signal).
    2.  killall
    3.  nice
        1.  Invoke a program at a particular priority.
    4.  renice
        1.  Change a process’s priority as it runs.
    5.  cpulimit
18.  Scheduling Jobs
    1.  sleep
        1.  Wait a set number of seconds, doing nothing.
    2.  watch
        1.  Run a program at set intervals.
    3.  at
        1.  Schedule a job for a single, future time.
    4.  crontab
        1.  Schedule jobs for many future times.
19.  Logins, Logouts, and Shutdowns
    1.  shutdown
        1.  Halts or reboots a Linux system
20.  Users and Their Environment
    1.  logname
        1.  Print your login name.
    2.  whoami
        1.  Print your current, effective username.
    3.  id
        1.  Print the user ID and group membership of a user.
    4.  who
        1.  List logged-in users, long output.
    5.  users
        1.  List logged-in users, short output.
    6.  finger
        1.  Print information about users.
    7.  last
        1.  Determine when someone last logged in.
    8.  printenv
        1.  Print your environment.
21.  User Account Management
    1.  useradd
        1.  Create an account.
    2.  userdel
        1.  Delete an account.
    3.  usermod
        1.  Modify an account.
    4.  passwd
        1.  Change a password.
    5.  chfn
        1.  Change a user’s personal information.
    6.  chsh
        1.  Change a user’s shell.
22.  Group Management
    1.  groups
        1.  Print the group membership of a user.
    2.  groupadd
        1.  Create a group.
    3.  groupdel
        1.  Delete a group.
    4.  groupmod
        1.  Modify a group.
23.  Host Information
    1.  uname
        1.  Print basic system information.
    2.  hostname
        1.  Print the system’s hostname.
    3.  dnsdomainname
        1.  Same as hostname -d.
    4.  domainname
        1.  Same as hostname -y.
    5.  nisdomainname
        1.  Same as hostname -y.
    6.  ypdomainname
        1.  Same as hostname -y.
    7.  ip
        1.  Set and display network interface information.
    8.  ifconfig
        1.  Older command to set and display network interface information.
24.  Host Location
    1.  host
        1.  Look up hostnames, IP addresses, and DNS info.
    2.  whois
        1.  Look up the registrants of Internet domains.
    3.  ping
        1.  Check if a remote host is reachable.
    4.  traceroute
        1.  View the network path to a remote host.
    5.  dig
        1.  ex
        2.  http://kb.mediatemple.net/questions/909/Understanding+the+dig+command
        3.  http://www.cyberciti.biz/faq/linux-unix-dig-command-examples-usage-syntax/
25.  Network Connections
    1.  ssh
        1.  Securely log into a remote host, or run commands on it.
    2.  telnet
        1.  Log into a remote host (insecure!).
    3.  scp
        1.  Securely copy files to/from a remote host (batch).
    4.  sftp
        1.  Securely copy files to/from a remote host (interactive).
    5.  ftp
        1.  Copy files to/from a remote host (interactive, insecure!).
26.  Email
    1.  thunderbird
        1.  Graphical mail client.
    2.  evolution
        1.  Graphical mail client.
    3.  mutt
        1.  Text-based mail client.
    4.  mail
        1.  Minimal text-based mail client.
    5.  mailq
        1.  View the outgoing mail queue on your system.
27.  Web Browsing
    1.  firefox
        1.  Full-featured web browser.
    2.  lynx
        1.  Text-only web browser.
    3.  wget
        1.  Download web pages and files.
28.  Usenet News
    1.  slrn
        1.  Usenet newsreader
29.  Instant Messaging
    1.  gaim
        1.  Instant messaging and IRC client.
    2.  talk
        1.  Linux/Unix chat program.
    3.  write
        1.  Send messages to a terminal.
    4.  mesg
        1.  Prohibit talk and write.
    5.  tty
        1.  Print your terminal device name.
30.  Screen Output
    1.  echo
        1.  Print simple text on standard output.
    2.  printf
        1.  Print formatted text on standard output.
    3.  yes
        1.  Print repeated text on standard output.
    4.  seq
        1.  Print a sequence of numbers on standard output.
    5.  clear
        1.  Clear the screen or window.
31.  Math and Calculations
    1.  xcalc
        1.  Display a graphical calculator.
    2.  expr
        1.  Evaluate simple math on the command line.
    3.  dc
        1.  Text-based calculator.
32.  Dates and Times
    1.  xclock
        1.  Display a graphical clock.
    2.  cal
        1.  Print a calendar.
    3.  date
        1.  Print or set the date and time.
    4.  ntpdate
        1.  Set the system time using a remote timeserver.
33.  Graphics and Screensavers
    1.  eog
        1.  Display graphics files.
    2.  geeqie
        1.  Display graphics files and slideshows.
    3.  ksnapshot
        1.  Take a screenshot (screen capture).
    4.  gimp
        1.  Edit graphics files.
    5.  dia
        1.  Draw structured diagrams.
    6.  gnuplot
        1.  Create graphs and plots.
    7.  xscreensaver
        1.  Run a screensaver.
34.  Audio
    1.  amarok, rhythmbox, xmms
        1.  Audio file players (MP3, WAV, OGG).
    2.  grip
        1.  CD player, ripper, and MP3 encoder.
    3.  cdparanoia
        1.  Rip audio from CDs to WAV files.
    4.  lame
        1.  Convert from WAV to MP3.
    5.  id3tag
        1.  Edit ID3 tags.
    6.  audacity
        1.  Edit audio files.
    7.  k3b
        1.  CD burner with graphical interface.
35.  Video
    1.  mplayer
        1.  Video file playback.
    2.  gxine
        1.  Simple DVD player.
    3.  kino
        1.  Video editor.
    4.  HandBrake
        1.  Video ripper.
36.  Network
    1.  traceroute
        1.  View the network path to a remote host.
    2.  ifconfig
        1.  Older command to set and display network interface information.
    3.  netstat
        1.  Commands
    4.  who
        1.  List logged-in users, long output.
    5.  tcpdump
    6.  ping
        1.  Check if a remote host is reachable.
    7.  ifup/ifdown
    8.  nslookup
    9.  dig
    10.  mtr
        1.  mtr combines the functionality of the traceroute and ping programs in a single network diagnostic tool
