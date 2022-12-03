**Directory** **Description** `/` The root directory where the file system begins. The root directory will probably contain only subdirectories. `/boot` This is where the Linux kernel and boot loader files are kept. The kernel is a file called `vmlinuz`. `/etc` The `/etc` directory contains the configuration files for the system. All of the files in `/etc` should be text files. Some points of interest are:

`/etc/passwd`

The `passwd` file contains the essential information for each user. This is where user accounts are defined.

`/etc/fstab`

The `fstab` file contains a table of devices that get mounted when the system boots. This file defines the system's disk drives.

`/etc/hosts`

This file lists the network host names and IP addresses that are intrinsically known to the system.

`/etc/init.d`

This directory contains the scripts that start various system services at boot time.

`/bin, /usr/bin` These two directories contain most of the programs for the system. The `/bin` directory has the essential programs that the system requires to operate, while `/usr/bin` contains applications for the system's users. `/sbin, /usr/sbin` The `sbin` directories contain programs for system administration, mostly for use by the superuser. `/usr` The `/usr` directory contains a variety of things that support user applications. Some highlights:

`/usr/share/X11`

Support files for the X Window system

`/usr/share/dict`

Dictionaries for the spelling checker. Yes, Linux comes with a spelling checker. See [`look`](http://linuxcommand.org/lc3_man_pages/look1.html) and [`aspell`](http://linuxcommand.org/lc3_man_pages/aspell1.html).

`/usr/share/doc`

Various documentation files in a variety of formats.

`/usr/share/man`

The man pages are kept here.

`/usr/local` `/usr/local` and its subdirectories are used for the installation of software and other files for use on the local machine. What this really means is that software that is not part of the official distribution (which usually goes in `/usr/bin`) goes here.

When you find interesting programs to install on your system, they should be installed in one of the `/usr/local` directories. Most often, the directory of choice is `/usr/local/bin`.

`/var` The `/var` directory contains files that change as the system is running. This includes:

`/var/log`

Directory that contains log files. These are updated as the system runs. It's a good idea to view the files in this directory from time to time, to monitor the health of your system.

`/var/spool`

This directory is used to hold files that are queued for some process, such as mail messages and print jobs. When a user's mail first arrives on the local system (assuming it has local mail, a rare occurrence on modern machines that are not mail servers), the messages are first stored in `/var/spool/mail`

`/lib` The shared libraries (similar to DLLs in that other operating system) are kept here. `/home` `/home` is where users keep their personal work. In general, this is the only place users are allowed to write files. This keeps things nice and clean :-) `/root` This is the superuser's home directory. `/tmp` `/tmp` is a directory in which programs can write their temporary files. `/dev` The `/dev` directory is a special directory, since it does not really contain files in the usual sense. Rather, it contains devices that are available to the system. In Linux (like Unix), devices are treated like files. You can read and write devices as though they were files. For example `/dev/fd0` is the first floppy disk drive, `/dev/sda` is the first hard drive. All the devices that the kernel understands are represented here. `/proc` The `/proc` directory is also special. This directory does not contain files. In fact, this directory does not really exist at all. It is entirely virtual. The `/proc` directory contains little peep holes into the kernel itself. There are a group of numbered entries in this directory that correspond to all the processes running on the system. In addition, there are a number of named entries that permit access to the current configuration of the system. Many of these entries can be viewed. Try viewing `/proc/cpuinfo`. This entry will tell you what the kernel thinks of the system's CPU. `/media` Finally, we come to `/media`, a normal directory which is used in a special way. The `/media` directory is used for _mount points_. As we learned in the [second lesson](http://linuxcommand.org/lc3_lts0020.php), the different physical storage devices (like hard disk drives) are attached to the file system tree in various places. This process of attaching a device to the tree is called _mounting_. For a device to be available, it must first be mounted.

When your system boots, it reads a list of mounting instructions in the `/etc/fstab` file, which describes which device is mounted at which mount point in the directory tree. This takes care of the hard drives, but we may also have devices that are considered temporary, such as optical disks and USB storage devices. Since these are removable, they do not stay mounted all the time. The `/media` directory is used by the automatic device mounting mechanisms found in modern desktop oriented Linux distributions. To see what devices and mount points are used, type [`mount`](http://linuxcommand.org/lc3_man_pages/mount8.html).