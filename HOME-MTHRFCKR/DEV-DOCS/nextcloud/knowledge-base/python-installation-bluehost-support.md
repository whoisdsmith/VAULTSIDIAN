---
created: 2022-08-05T09:12:10 (UTC -04:00)
tags: []
source: https://www.bluehost.com/help/article/python-installation
author: 
---

# Python Installation | Bluehost Support

---
___

-   [Overview](https://www.bluehost.com/help/article/python-installation#Overview)
-   [Download up to the latest Python version 3.9.2](https://www.bluehost.com/help/article/python-installation#download)
-   [Python Installation](https://www.bluehost.com/help/article/python-installation#install)
-   [Modify the .bashrc](https://www.bluehost.com/help/article/python-installation#bashrc)
-   [Configuration Error](https://www.bluehost.com/help/article/python-installation#Error)

___

## Overview

Bluehost uses the preinstalled version of Python that ships with CentOS. Because of this, it is often not the latest release. This article will explain how to install an updated version of Python locally.

**Note:** In order to install Python locally, you will need to be added to the Compiler group. Please contact our Support at **888-401-4678** to request you be added to the Compiler group before proceeding.

## Download up to the latest Python version 3.9.2

Enter the following commands to download and extract Python 3.9.2 to your hosting account. You can also use this reference [Index of Python.org/ftp/](https://www.python.org/ftp/python/) to get your preferred version.

```
mkdir ~/python

cd ~/python

wget http://www.python.org/ftp/python/3.9.2/Python-3.9.2.tgz

tar zxfv Python-3.9.2.tgz

find ~/python -type d | xargs chmod 0755

cd Python-3.9.2
```

## Python Installation

Once extracted, you can use the following commands to configure and install Python.

```
./configure --prefix=$HOME/python

make

make install
```

## Modify the .bashrc

For your local version of python to load, you will need to add it to the .bashrc file.

```
vim ~/.bashrc
```

Press _i_

Enter:

```
export PATH=$HOME/python/Python-3.9.2/:$PATH
```

Write the changes (press `ESC`) and close vim:

```
:wq
```

Press Enter

```
source ~/.bashrc
```

**Note**: You may need to log out for the environment to update.  
Enter _python -V_ to check the version of python installed.

## Configuration Error

```
configure: error: in `/home2/tomstec2/Python_3.9.2/Python-3.9.2':
configure: error: no acceptable C compiler found in $PATH
See `config.log' for more details
```

**Important Note**: If this configuration error occurs when you attempt to configure python with **./configure --prefix=$HOME/python**, this means that your cPanel user is not added to the C compiler group on the server. 

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.
