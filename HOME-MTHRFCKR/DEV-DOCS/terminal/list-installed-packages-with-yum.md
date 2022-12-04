# List installed packages with YUM

![](https://electrictoolbox.com/wp-content/uploads/yum-list-installed-packages.jpg?ezimgfmt=ng%3Awebp%2Fngcb1%2Frs%3Adevice%2Frscb1-1)

This post looks at how to list the installed packages with YUM from the command line for YUM based Linux distributions, such as CentOS and Fedora.

It’s very simple:

```
yum list installed

```

This will result in a list of all installed packages in case-sensitive alphabetical order, like in the following example:

if(typeof ez_ad_units!='undefined'){ez_ad_units.push([[300,250],'electrictoolbox_com-medrectangle-3','ezslot_1',148,'0','0'])};__ez_fad_position('div-gpt-ad-electrictoolbox_com-medrectangle-3-0');

```
Loading "fastestmirror" plugin
Loading "installonlyn" plugin
Installed Packages
Deployment_Guide-en-US.noarch            5.1.0-11.el5.centos.1  installed
GConf2.i386                              2.14.0-9.el5           installed
GConf2.x86_64                            2.14.0-9.el5           installed
ImageMagick.i386                         6.2.8.0-3.el5.4        installed
ImageMagick.x86_64                       6.2.8.0-3.el5.4        installed
MAKEDEV.x86_64                           3.23-1.2               installed
NetworkManager.x86_64                    1:0.6.4-6.el5          installed
ORBit2.i386                              2.14.3-4.el5           installed
ORBit2.x86_64                            2.14.3-4.el5           installed
SysVinit.x86_64                          2.86-14                installed
acl.x86_64                               2.2.39-2.1.el5         installed
acpid.x86_64                             1.0.4-5                installed
...
zip.x86_64                               2.31-1.2.2             installed
zlib.x86_64                              1.2.3-3                installed
zlib.i386                                1.2.3-3                installed
zlib-devel.i386                          1.2.3-3                installed
zlib-devel.x86_64                        1.2.3-3                installed

```

The list is going to be pretty long, so you might want to pipe it through “more” or “less” so you can scroll through it a page at a time:

```
yum list installed | more
yum list installed | less

```

or direct it out to a file for viewing in a text editor:

if(typeof ez_ad_units!='undefined'){ez_ad_units.push([[300,250],'electrictoolbox_com-medrectangle-4','ezslot_6',149,'0','0'])};__ez_fad_position('div-gpt-ad-electrictoolbox_com-medrectangle-4-0');

```
yum list installed > /tmp/yum-list.txt

```

If you need to see all packages, installed and available, you can use:

```
yum list all

```

Or maybe just available packages:

```
yum list available

```