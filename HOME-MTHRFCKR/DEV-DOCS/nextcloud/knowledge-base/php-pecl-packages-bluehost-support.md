---
created: 2022-08-05T09:11:14 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/php-pecl-package
author: 
---

# PHP PECL Packages | Bluehost Support

---
PECL acts as a repository for PHP Extensions, providing you with a directory of all known extensions and hosting facilities for downloading and development of PHP extensions.

### Viewing Currently Installed PECL Packages

To view the PECL Packages currently installed, you will need SSH access.

If you need to enable SSH access please see our article, _[SSH Access](https://www.bluehost.com/help/article/ssh-access)_.

There is currently no way of viewing installed PECL packages for an individual cPanel user. Instead, you can check within your ~/pecl folder where installed packages would be located.

You can view globally installed PECL packages by using the following command. (73 can be replaced with any other available version of PHP ex. 56, 70, 71, 72, 73, and 74)  
`ea-php73-pecl list -a`

### Installing New PECL Package

You can download and install PECL packages locally to your account. You'll need SSH access.

If you need to enable SSH access please see our article, _[SSH Access](https://www.bluehost.com/help/article/ssh-access)_.

\*\*Instances of “ea-php73” in the following commands can be replaced by other versions of PHP on the server\*\*

Once you're logged in, these are steps for installation:

1.  Create a folder in your home directory to download and compile the packages in.
    
    `mkdir ~/pecl`
    
2.  Create a directory for your php extensions to be located in. Something like ~/php/extensions.
    
    `$ mkdir ~/php )` `$ mkdir ~/php/extensions`
    
3.  Change directories to that created pecl directory, and run the following command:
    
    `c`$ cd ~/pecl  
    $ /opt/cpanel/ea-php73/root/usr/bin/pecl download _<packagename>_  
    \*\* For multiple PECL packages, repeat steps 4-9 and then step 12 \*\*
    
4.  That will download the package which you'll then need to untar with:
    
    `tar –zxvf $package.tgz`
    
5.  Change directories to the extracted directory and run the **phpize** command
    
    `$ cd ~/pecl/`
    
    `$ /opt/cpanel/ea-php73/root/usr/bin/phpize`
    
6.  When that's done, run the following command from inside the module folder
    
    `/opt/cpanel/ea-php73/root/usr/bin/phpize && ./configure --with-php-config=/opt/cpanel/ea-php73/root/usr/bin/php-config --prefix=$HOME/pecl/`
    
7.  If that runs without error, then the package should be compatible with our environment. If it completes successfully, run the following command from the individual module directory make
    
    `make`
    
8.  That will create the module file that you’ll need to put in your php.ini. It’ll be located in the modules directory and will be named **<packagename>****_.so_**
9.  Copy the .so file to your ~/php/extensions directory that you created.
    
    `cp ~/pecl//modules/.so ~/php/extensions/`
    
10.  Copy the existing server-installed extensions from /usr/lib64/php/modules/ to the ~/php/extensions directory:
    
    `cp -rf /usr/lib64/php/modules/* ~/php/extensions/`
    
11.  Edit your PHP config from within the **Advanced** >> **MultiPHP INI Editor**. Use the Editor mode to add in the following line, or edit the existing line.  
    \*\* You can find your /home/user folder by using the “pwd” command in shell. \*\*
    
    `extension_dir = "/home<#>//php/extensions"`
    
12.  Add the extension to your php.ini file. It’ll look like:
    
    `extension=.so`
