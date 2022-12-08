---
tags:: documents
created: 2022-07-07T11:27:11 (UTC -04:00)
tags: [PDF,Markdown,converter,online]
source: https://pdf2md.morethan.io/
author: 
---

# Nextcloud User Manual

## Release latest: **Jul 04, 2022**

### The Nextcloud developers

## CONTENTS

### CHAPTER ONE



**Welcome to Nextcloud: A safe home for all your data.**

Nextcloud is open source file sync and share software for everyone from individuals operating the free Nextcloud Server  
in the privacy of their own home, to large enterprises and service providers supported by the Nextcloud Enterprise  
Subscription. Nextcloud provides a safe, secure, and compliant file synchronization and sharing solution on servers  
that you control.

You can share one or more files and folders on your computer, and synchronize them with your Nextcloud server. Place  
files in your local shared directories, and those files are immediately synchronized to the server and to other devices  
using the Nextcloud Desktop Sync Client, Android app, or iOS app. To learn more about the Nextcloud desktop client,  
please refer to:

-   Nextcloud Desktop Client

Help translate.

#### 1

**2 Chapter 1. Nextcloud latest user manual introduction**

#### CHAPTER

### TWO

### WHAT’S NEW FOR USERS IN NEXTCLOUD LATEST

1.  Easier way to select a new app:
2.  New Contacts menu to reach your colleagues or friends easier:
3.  A contact popup menu over avatars everywhere:
4.  Ability to send multiple unique sharing links each with their own settings, by entering email addresses (the  
    recipient will receive an email):
5.  Many other improvements and new apps, like screensharing in Video calls, new Circles app for user defined  
    groups, push notifications, notifications of file changes even when shared to another server, undo removal of files  
    from a shared folder even if the removal was done by a recipient, directly sharing to social media and much more.

#### 3

**4 Chapter 2. What’s new for users in Nextcloud latest**

-   1 Nextcloud latest user manual introduction
-   2 What’s new for users in Nextcloud latest
-   3 The Nextcloud Web interface
    -   3.1 Web browser requirements
    -   3.2 Navigating the main user interface
-   4 Files & synchronization
    -   4.1 Accessing your files using the Nextcloud Web interface
    -   4.2 Accessing Nextcloud files using WebDAV
    -   4.3 Managing deleted files
    -   4.4 Desktop and mobile synchronization
    -   4.5 Encrypting your Nextcloud files on the server
    -   4.6 File Sharing
    -   4.7 Federated Shares
    -   4.8 Making anonymous uploads
    -   4.9 Large file uploads
    -   4.10 Storage quota
    -   4.11 Version control
    -   4.12 Projects
    -   4.13 Transfer Ownership
    -   4.14 Using Federation Shares
-   5 Groupware
    -   5.1 Using the Contacts app
    -   5.2 Using the Calendar app
    -   5.3 Synchronizing with Android
    -   5.4 Synchronizing with iOS
    -   5.5 Synchronizing with macOS
    -   5.6 Synchronizing with Thunderbird
    -   5.7 Synchronizing with KDE Kontact
    -   5.8 Synchronizing with the GNOME desktop
    -   5.9 Synchronizing with Windows
-   6 Talk
    -   6.1 Basics of Nextcloud Talk
    -   6.2 Advanced Talk features
    -   6.3 Join a call or chat as guest
-   7 Setting your preferences
-   8 Universal access
    -   8.1 Zoom and responsiveness
    -   8.2 Navigating via keyboard
    -   8.3 Included themes
-   9 Using two-factor authentication
    -   9.1 Configuring two-factor authentication
    -   9.2 Recovery codes in case you lost your 2nd factor
    -   9.3 Logging in with two-factor authentication
    -   9.4 Using two-factor authentication with hardware tokens
    -   9.5 Using client applications with two-factor authentication
    -   9.6 Considerations
-   10 Manage connected browsers and devices
    -   10.1 Managing connected browsers
    -   10.2 Managing devices
    -   10.3 Device-specific passwords and password changes
-   11 External Storage
    -   11.1 Configuring external Storage

**6 Chapter 2. What’s new for users in Nextcloud latest**

#### CHAPTER

### THREE

### THE NEXTCLOUD WEB INTERFACE

You can connect to your Nextcloud server using any Web browser. Just point it to your Nextcloud server URL (e.g.  
cloud.example.com) and enter your username and password:

### 3.1 Web browser requirements

For the best experience with the Nextcloud web interface, we recommend that you use the latest and supported version  
of a browser from this list:

-   Google **Chrome** /Chromium
-   Mozilla **Firefox**
-   Apple **Safari**
-   Microsoft **Edge**

**Note:** If you want to use Nextcloud Talk you need to run Mozilla **Firefox** 52+ or Google **Chrome** /Chromium 49+ to  
have the full experience with video calls and screensharing. Google **Chrome** /Chromium requires a additional plugin  
for screensharing.

**Note:** Microsoft **Internet Explorer** is **NOT** supported.

#### 7

### 3.2 Navigating the main user interface

By default, the Nextcloud Web interface opens to your Dashboard or Files page:

In Files you can add, remove, and share files, and the server administrator can change access privileges.

The Nextcloud user interface contains the following fields and functions:

-   **Apps Selection Menu** (1): Located in the upper left corner, you’ll find all your apps which are available on your  
    instance of Nextcloud. Clicking on an apps icon will redirect you to the app.
-   **Apps Information** field (2): Located in the left sidebar, this provides filters and tasks associated with your  
    selected app. For example, when you are using the Files apps you have a special set of filters for quickly finding  
    your files, such as files that have been shared with you, and files that you have shared with others. You’ll see  
    different items for other apps.
-   **Application View** (3): The main central field in the Nextcloud user interface. This field displays the contents or  
    user features of your selected app.
-   **Navigation Bar** (4): Located over the main viewing window (the Application View), this bar provides a type of  
    breadcrumbs navigation that enables you to migrate to higher levels of the folder hierarchy up to the root level  
    (home).
-   **New** button (5): Located in the Navigation Bar, theNewbutton enables you to create new files, new folders, or  
    upload files.

**Note:** You can also drag and drop files from your file manager into the Files Application View to upload them to your  
instance.

-   **Search** field (6): Click on the Magnifier in the upper right corner to search for files and entries of the current  
    app.
-   **Contacts Menu** (7): Gives you an overview about your contacts and users on your server. Dependent on the  
    given details and available apps, you can directly start a video call with them or send emails.
-   **Grid view** button (8): This looks like four little squares, which toggles the grid view for folders and files.

**8 Chapter 3. The Nextcloud Web interface**

-   **Settings** menu (9): Click on your profile picture, located to the right of the Search field, to open your Settings  
    dropdown menu. Your Settings page provides the following settings and features:  
    **\-** Links to download desktop and mobile apps  
    **\-** Server usage and space availability  
    **\-** Password management  
    **\-** Name, email, and profile picture settings  
    **\-** Manage connected browsers and devices  
    **\-** Group memberships  
    **\-** Interface language settings  
    **\-** Manage notifications  
    **\-** Federated Cloud ID and social media-sharing buttons  
    **\-** SSL/TLS certificate manager for external storages  
    **\-** Your Two-factor Settings  
    **\-** Nextcloud Version information

See _Setting your preferences_ section to learn more about these settings.

**3.2. Navigating the main user interface 9**

**10 Chapter 3. The Nextcloud Web interface**

#### CHAPTER

### FOUR

### FILES & SYNCHRONIZATION

### 4.1 Accessing your files using the Nextcloud Web interface

You can access your Nextcloud files with the Nextcloud Web interface and create, preview, edit, delete, share, and  
re-share files. Your Nextcloud administrator has the option to disable these features, so if any of them are missing on  
your system ask your server administrator.

**4.1.1 Tagging files**

You can assign tags to files. To create tags, open a file to the Details view. Then type your tags. To enter more than one  
tag press the return key after creating each tag. All tags are system tags, and are shared by all users on your Nextcloud  
server.

Then use the Tags filter on the left sidebar to filter files by tags:

#### 11

**12 Chapter 4. Files & synchronization**

**4.1.2 Comments**

Use the Details view to add and read comments on any file or folder. Comments are visible to everyone who has access  
to the file:

**4.1.3 Video player**

You can play videos in Nextcloud with the Video Player app by simply clicking on the file. Video streaming by the native  
Nextcloud video player depends on your Web browser and the video format. If your Nextcloud administrator has enabled  
video streaming, and it doesn’t work in your Web browser, it may be a browser issue. See https://developer.mozilla.  
org/en-US/docs/Web/HTML/Supported\_media\_formats#Browser\_compatibility for supported multimedia formats in  
Web browsers.

**4.1.4 File controls**

Nextcloud can display thumbnail previews for image files, MP3 covers, and text files, if this enabled by your server  
administrator. Hover your cursor over a file or folder to expose the controls for the following operations:

**Favorites**  
Click the star to the left of the file icon to mark it as a favorite:  
You can also quickly find all of your favorites with the Favorites filter on the left sidebar.

**Overflow Menu**  
The Overflow menu (three dots) displays file details, and allows you to rename, download, or delete files:  
The Details view shows Activities, Sharing, and Versions information:

The **Settings** gear icon at the lower left allows you to show or hide hidden files in your Nextcloud Web interface. These  
are also called dotfiles, because they are prefixed with a dot, e.g..mailfile. The dot tells your operating system to

**4.1. Accessing your files using the Nextcloud Web interface 13**

**14 Chapter 4. Files & synchronization**

hide these files in your file browsers, unless you choose to display them. Usually these are configuration files, so having  
the option to hide them reduces clutter.

**4.1.5 Previewing files**

You can display uncompressed text files, OpenDocument files, videos, and image files in the Nextcloud embedded  
viewers by clicking on the file name. There may be other file types you can preview if your Nextcloud administrator  
has enabled them. If Nextcloud cannot display a file, it starts a download process and downloads the file to your  
computer.

**4.1. Accessing your files using the Nextcloud Web interface 15**

**4.1.6 Navigating inside your Nextcloud**

Navigating through folders in Nextcloud is as simple as clicking on a folder to open it and using the back button on  
your browser to move to a previous level. Nextcloud also provides a navigation bar at the top of the Files field for quick  
navigation.

**4.1.7 Sharing status icons**

Any folder that has been shared is marked with theSharedoverlay icon. Public link shares are marked with a chain  
link. Unshared folders are not marked:

**4.1.8 Creating or uploading files and directories**

Upload or create new files or folders directly in a Nextcloud folder by clicking on the _New_ button in the Files app:

The _New_ button provides the following options:

**Up arrow**  
Upload files from your computer into Nextcloud. You can also upload files by dragging and dropping them from  
your file manager.

**Text file**  
Creates a new text file and adds the file to your current folder.

**Folder**  
Creates a new folder in the current folder.

**16 Chapter 4. Files & synchronization**

**4.1.9 Selecting files or folders**

You can select one or more files or folders by clicking on their checkboxes. To select all files in the current directory,  
click on the checkbox located at the top of the files listing.

When you select multiple files, you can delete all of them, or download them as a ZIP file by using theDeleteor  
Downloadbuttons that appear at the top.

**Note:** If theDownloadbutton is not visible, the administrator has disabled this feature.

**4.1.10 Filtering the files view**

The left sidebar on the Files page contains several filters for quickly sorting and managing your files.

**All files**  
The default view; displays all files that you have access to.

**Favorites**  
Files or folders marked with the yellow star.

**Shared with you**  
Displays all files shared with you by another user or group.

**Shared with others**  
Displays all files that you have shared with other users or groups.

**Shared by link**  
Displays all files that are shared by you via public link.

**External Storage (optional)**  
Files that you have access to on external storage devices and services such as Amazon S3, SMB/CIFS, FTP...

**4.1.11 Moving files**

You can move files and folders by dragging and dropping them into any directory.

**4.1.12 Creating or connecting to a Federation Share link**

Federated Cloud Sharing allows you to mount file shares from remote Nextcloud servers, and manage them just like a  
local share. See _Using Federation Shares_ to learn to how to create and connect to new Federated Cloud shares.

### 4.2 Accessing Nextcloud files using WebDAV

Nextcloud fully supports the WebDAV protocol, and you can connect and synchronize with your Nextcloud files over  
WebDAV. In this chapter you will learn how to connect Linux, macOS, Windows, and mobile devices to your Nextcloud  
server via WebDAV. Before we get into configuring WebDAV, let’s take a quick look at the recommended way of  
connecting client devices to your Nextcloud servers.

**Note:** In the following examples, you should replace **example.com/nextcloud** with the URL of your Nextcloud server  
(omit the directory part if the installation is in the root of your domain), and “USERNAME” with the username of the  
connecting user.

**4.2. Accessing Nextcloud files using WebDAV 17**

See the WebDAV URL (bottom left in settings) on your Nextcloud.

**Note:** In the following examples, you must use an app-password for login, which you can generate in your security  
settings.

**4.2.1 Nextcloud Desktop and mobile clients**

The recommended way to synchronize a desktop PC with a Nextcloud server is by using Nextcloud/ownCloud sync  
clients. You can configure the client to save files in any local directory and you can choose which directories on the  
Nextcloud server to sync with. The client displays the current connection status and logs all activity, so you always  
know which remote files have been downloaded to your PC and you can verify that files created and updated on your  
local PC are properly synchronized with the server.

The recommended way to synchronize Nextcloud server with Android and Apple iOS devices is by using the mobile  
apps.

To connect your mobile app to a Nextcloud server use the base URL and folder only:

example.com/nextcloud

In addition to the mobile apps provided by Nextcloud or ownCloud, you can use other apps to connect to Nextcloud  
from your mobile device using WebDAV. WebDAV Navigator is a good (proprietary) app for Android devices and  
iPhones. The URL to use on these is:

example.com/nextcloud/remote.php/dav/files/USERNAME/

**4.2.2 WebDAV configuration**

If you prefer, you may also connect your desktop PC to your Nextcloud server by using the WebDAV protocol rather  
than using a special client application. Web Distributed Authoring and Versioning (WebDAV) is a Hypertext Transfer  
Protocol (HTTP) extension that makes it easy to create, read, and edit files on Web servers. With WebDAV you can  
access your Nextcloud shares on Linux, macOS and Windows in the same way as any remote network share, and stay  
synchronized.

**4.2.3 Accessing files using Linux**

You can access files in Linux operating systems using the following methods.

**Nautilus file manager**

**When you configure your Nextcloud account in the** GNOME Control Center, **your files will automatically be  
mounted by Nautilus as a WebDAV share, unless you deselect file access**.

You can also mount your Nextcloud files manually. Use thedavs://protocol to connect the Nautilus file manager to  
your Nextcloud share:

davs://example.com/nextcloud/remote.php/dav/files/USERNAME/

**18 Chapter 4. Files & synchronization**

**Note:** If your server connection is not HTTPS-secured, usedav://instead ofdavs://:

**Note:** The same method works for other file managers that use GVfs, such as MATE’s Caja and Cinnamon’s Nepomuk.

**Accessing files with KDE and Dolphin file manager**

To access your Nextcloud files using the Dolphin file manager in KDE, use thewebdav://protocol:

webdav://example.com/nextcloud/remote.php/dav/files/USERNAME/

You can create a permanent link to your Nextcloud server:

1.  Open Dolphin and click “Network” in the left hand “Places” column.

**4.2. Accessing Nextcloud files using WebDAV 19**

2.  Click on the icon labeled **Add a Network Folder**. The resulting dialog should appear with WebDAV already  
    selected.
3.  If WebDAV is not selected, select it.
4.  Click **Next**.
5.  Enter the following settings:
    -   Name: The name you want to see in the **Places** bookmark, for example Nextcloud.
    -   User: The Nextcloud username you used to log in, for example admin.
    -   Server: The Nextcloud domain name, for example **example.com** (without **[http://](https://pdf2md.morethan.io//http://)** before or directories  
        afterwards).
    -   Folder – Enter the pathnextcloud/remote.php/dav/files/USERNAME/.
6.  (Optional) Check the “Create icon” checkbox for a bookmark to appear in the Places column.
7.  (Optional) Provide any special settings or an SSL certificate in the “Port & Encrypted” checkbox.

**4.2.4 Creating WebDAV mounts on the Linux command line**

You can create WebDAV mounts from the Linux command line. This is useful if you prefer to access Nextcloud the  
same way as any other remote filesystem mount. The following example shows how to create a personal mount and  
have it mounted automatically every time you log in to your Linux computer.

1.  Install thedavfs2WebDAV filesystem driver, which allows you to mount WebDAV shares just like any other  
    remote filesystem. Use this command to install it on Debian/Ubuntu:

```
apt-get install davfs2
```

2.  Use this command to install it on CentOS, Fedora, and openSUSE:

```
yum install davfs2
```

3.  Add yourself to thedavfs2group:

```
usermod -aG davfs2 <username>
```

3.  Then create anextclouddirectory in your home directory for the mountpoint, and.davfs2/for your personal  
    configuration file:

```
mkdir ~/nextcloud
mkdir ~/.davfs2
```

4.  Copy/etc/davfs2/secretsto~/.davfs2:

```
cp /etc/davfs2/secrets ~/.davfs2/secrets
```

5.  Set yourself as the owner and make the permissions read-write owner only:

```
chown <linux_username>:<linux_username> ~/.davfs2/secrets
chmod 600 ~/.davfs2/secrets
```

6.  Add your Nextcloud login credentials to the end of thesecretsfile, using your Nextcloud server URL and your  
    Nextcloud username and password:

**20 Chapter 4. Files & synchronization**

```
https://example.com/nextcloud/remote.php/dav/files/USERNAME/ <username> <password>
or
$PathToMountPoint $USERNAME $PASSWORD
for example
/home/user/nextcloud john 1234
```

7.  Add the mount information to/etc/fstab:

```
https://example.com/nextcloud/remote.php/dav/files/USERNAME/ /home/<linux_username>/
˓→nextcloud
davfs user,rw,auto 0 0
```

8.  Then test that it mounts and authenticates by running the following command. If you set it up correctly you won’t  
    need root permissions:

```
mount ~/nextcloud
```

9.  You should also be able to unmount it:

```
umount ~/nextcloud
```

Now every time you login to your Linux system your Nextcloud share should automatically mount via WebDAV in your  
~/nextclouddirectory. If you prefer to mount it manually, changeautotonoautoin/etc/fstab.

**4.2.5 Known issues**

**Problem**

Resource temporarily unavailable

**Solution**

If you experience trouble when you create a file in the directory, edit/etc/davfs2/davfs2.confand add:

use\_locks 0

**Problem**

Certificate warnings

**Solution**

If you use a self-signed certificate, you will get a warning. To change this, you need to configuredavfs2to recognize  
your certificate. Copymycertificate.pemto/etc/davfs2/certs/. Then edit/etc/davfs2/davfs2.confand  
uncomment the lineservercert. Now add the path of your certificate as in this example:

servercert /etc/davfs2/certs/mycertificate.pem

**4.2. Accessing Nextcloud files using WebDAV 21**

**4.2.6 Accessing files using macOS**

**Note:** The macOS Finder suffers from a series of implementation problems and should only be used if the Nextcloud  
server runs on **Apache** and **mod\_php** , or **Nginx 1.3.8+**. Alternative macOS-compatible clients capable of accessing  
WebDAV shares include open source apps like Cyberduck (see instructions here) and Filezilla. Commercial clients  
include Mountain Duck, Forklift, Transmit, and Commander One.

To access files through the macOS Finder:

1.  From the Finder’s top menu bar, choose **Go > Connect to Server...** :
2.  When the **Connect to Server...** window opens, enter your Nextcloud server’s WebDAV address in the **Server**  
    **Address:** field, i.e.:

```
https://cloud.YOURDOMAIN.com/remote.php/dav/files/USERNAME/
```

3.  Click **Connect**. Your WebDAV server should appear on the Desktop as a shared disk drive.

**22 Chapter 4. Files & synchronization**

**4.2.7 Accessing files using Microsoft Windows**

If you use the native Windows implementation of WebDAV, you can map Nextcloud to a new drive using Windows  
Explorer. Mapping to a drive enables you to browse files stored on a Nextcloud server the way you would files stored  
in a mapped network drive.

Using this feature requires network connectivity. If you want to store your files offline, use the Desktop Client to sync  
all files on your Nextcloud to one or more directories of your local hard drive.

**Note:** Windows 10 now defaults to allow Basic Authentication if HTTPS is enabled prior to mapping your drive. On  
older versions of Windows, you must permit the use of Basic Authentication in the Windows Registry: launchregedit  
and navigate toHKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\WebClient\\Parameters. Cre-  
ate or edit theDWORDvalueBasicAuthLevel(Windows Vista, 7 and 8) orUseBasicAuth(Windows XP and Windows  
Server 2003) and set its value data to 1 for SSL connections. Value 0 means that Basic Authentication is disabled, a  
value of 2 allows both SSL and non-SSL connections (not recommended). Then exit Registry Editor, and restart the  
computer.

**Mapping drives with the command line**

The following example shows how to map a drive using the command line. To map the drive:

1.  Open a command prompt in Windows.
2.  Enter the following line in the command prompt to map to the computer Z drive:

```
net use Z: https://<drive_path>/remote.php/dav/files/USERNAME/ /user:youruser
yourpassword
```

```
where <drive_path> is the URL to your Nextcloud server.
```

For example: net use Z: https://example.com/nextcloud/remote.php/dav/files/USERNAME/ /  
user:youruser yourpassword

```
The computer maps the files of your Nextcloud account to the drive letter Z.
```

**Note:** Though not recommended, you can also mount the Nextcloud server using HTTP, leaving the connection  
unencrypted. If you plan to use HTTP connections on devices while in a public place, we strongly recommend using  
a VPN tunnel to provide the necessary security.

An alternative command syntax is:

net use Z: \\example.com@ssl\\nextcloud\\remote.php\\dav /user:youruser  
yourpassword

**4.2. Accessing Nextcloud files using WebDAV 23**

**Mapping drives with Windows Explorer**

To map a drive using the Microsoft Windows Explorer:

1.  Open Windows Explorer on your MS Windows computer.
2.  Right-click on **Computer** entry and select **Map network drive...** from the drop-down menu.
3.  Choose a local network drive to which you want to map Nextcloud.
4.  Specify the address to your Nextcloud instance, followed by **/remote.php/dav/files/USERNAME/**.  
    For example:

```
https://example.com/nextcloud/remote.php/dav/files/USERNAME/
```

**Note:** For SSL protected servers, check **Reconnect at sign-in** to ensure that the mapping is persistent upon subsequent  
reboots. If you want to connect to the Nextcloud server as a different user, check **Connect using different credentials**.

5.  Click theFinishbutton.  
    Windows Explorer maps the network drive, making your Nextcloud instance available.

**24 Chapter 4. Files & synchronization**

**4.2.8 Accessing files using Cyberduck**

Cyberduck is an open source FTP and SFTP, WebDAV, OpenStack Swift, and Amazon S3 browser designed for file  
transfers on macOS and Windows.

**Note:** This example uses Cyberduck version 4.2.1.

To use Cyberduck:

1.  Specify a server without any leading protocol information. For example:  
    example.com
2.  Specify the appropriate port. The port you choose depends on whether or not your Nextcloud server supports  
    SSL. Cyberduck requires that you select a different connection type if you plan to use SSL. For example:  
    80 (for WebDAV)  
    443 (for WebDAV (HTTPS/SSL))
3.  Use the ‘More Options’ drop-down menu to add the rest of your WebDAV URL into the ‘Path’ field. For example:  
    remote.php/dav/files/USERNAME/

Now Cyberduck enables file access to the Nextcloud server.

**4.2.9 Accessing public shares over WebDAV**

Nextcloud provides the possibility to access public shares over WebDAV.

To access the public share, open:

https://example.com/nextcloud/public.php/webdav

in a WebDAV client, use the share token as username and the (optional) share password as password.

**Note: Settings** → **Administration** → **Sharing** → **Allow users on this server to send shares to other servers**. This  
option also allows WebDAV access to public shares needs to be enabled in order to make this feature work.

**4.2.10 Known problems**

**Problem**

Windows does not connect using HTTPS.

**4.2. Accessing Nextcloud files using WebDAV 25**

**Solution 1**

The Windows WebDAV Client might not support Server Name Indication (SNI) on encrypted connections. If you  
encounter an error mounting an SSL-encrypted Nextcloud instance, contact your provider about assigning a dedicated  
IP address for your SSL-based server.

**Solution 2**

The Windows WebDAV Client might not support TLSv1.1 and TLSv1.2 connections. If you have restricted your  
server config to only provide TLSv1.1 and above the connection to your server might fail. Please refer to the WinHTTP  
documentation for further information.

**Problem**

You receive the following error message: **Error 0x800700DF: The file size exceeds the limit allowed and cannot be  
saved.**

**Solution**

Windows limits the maximum size a file transferred from or to a Web-  
DAV share may have. You can increase the value **FileSizeLimitInBytes** in  
**HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\WebClient\\Parameters** by clicking on  
**Modify**.

To increase the limit to the maximum value of 4GB, select **Decimal** , enter a value of **4294967295** , and reboot Windows  
or restart the **WebClient** service.

**Problem**

Accessing your files from Microsoft Office via WebDAV fails.

**Solution**

Known problems and their solutions are documented in the KB2123563 article.

**Problem**

Cannot map Nextcloud as a WebDAV drive in Windows using self-signed certificate.

**Solution**

1.  Go to the your Nextcloud instance via your favorite Web browser.
2.  Click through until you get to the certificate error in the browser status line.
3.  View the cert, then from the Details tab, select Copy to File.
4.  Save to the desktop with an arbitrary name, for examplemyNextcloud.pem.
5.  Start, Run, MMC.
6.  File, Add/Remove Snap-In.

**26 Chapter 4. Files & synchronization**

7.  Select Certificates, Click Add, My User Account, then Finish, then OK.
8.  Dig down to Trust Root Certification Authorities, Certificates.
9.  Right-Click Certificate, Select All Tasks, Import.
10.  Select the Save Cert from the Desktop.
11.  Select Place all Certificates in the following Store, Click Browse.
12.  Check the Box that says Show Physical Stores, Expand out Trusted Root Certification Authorities, and select  
    Local Computer there, click OK, Complete the Import.
13.  Check the list to make sure it shows up. You will probably need to Refresh before you see it. Exit MMC.
14.  Open Browser, select Tools, Delete Browsing History.
15.  Select all but In Private Filtering Data, complete.
16.  Go to Internet Options, Content Tab, Clear SSL State.
17.  Close browser, then re-open and test.

**Problem**

You cannot download more than 50 MB or upload large files when the upload takes longer than 30 minutes using Web  
Client in Windows 7.

**Solution**

Workarounds are documented in the KB2668751 article.

**4.2.11 Accessing files using cURL**

Since WebDAV is an extension of HTTP, cURL can be used to script file operations.

To create a folder with the current date as name:

$ curl -u user:pass -X MKCOL "https://example.com/nextcloud/remote.php/dav/files/  
˓→USERNAME/$(date'+%d-%b-%Y')"

To upload a fileerror.loginto that directory:

$ curl -u user:pass -T error.log "https://example.com/nextcloud/remote.php/dav/files/  
˓→USERNAME/$(date'+%d-%b-%Y')/error.log"

To move a file:

$ curl -u user:pass -X MOVE --header 'Destination: https://example.com/nextcloud/remote.  
˓→php/dav/files/USERNAME/target.jpg' https://example.com/nextcloud/remote.php/dav/files/  
˓→USERNAME/source.jpg

To get the properties of files in the root folder:

**4.2. Accessing Nextcloud files using WebDAV 27**

$ curl -X PROPFIND -H "Depth: 1" -u user:pass https://example.com/nextcloud/remote.  
˓→php/dav/files/USERNAME/ | xml\_pp

/nextcloud/remote.php/dav/files/USERNAME/ Tue, 13 Oct 2015 17:07:45 GMT 163 11802275840 "561d3a6139d05" HTTP/1.1 200 OK /nextcloud/remote.php/dav/files/USERNAME/welcome.txt Tue, 13 Oct 2015 17:07:35 GMT 163 "47465fae667b2d0fee154f5e17d1f0f1" text/plain HTTP/1.1 200 OK

### 4.3 Managing deleted files

When you delete a file in Nextcloud, it is not immediately deleted permanently, only moved into the trash bin. It is not  
permanently deleted until you manually delete it, or when the Deleted Files app deletes it to make room for new files.

Find your deleted files by clicking on the **Deleted files** button on the Files page of the Nextcloud Web interface. You’ll  
have options to either restore or permanently delete files.

**28 Chapter 4. Files & synchronization**

**4.3.1 Quotas**

Deleted files are not counted against your storage quota. Only your personal files count against your quota, not files  
which were shared with you. (See _Storage quota_ to learn more about quotas.)

**4.3.2 What happens when shared files are deleted**

Deleting files gets a little complicated when they are shared files, as this scenario illustrates:

1.  User1 shares a folder “test” with User2 and User3
2.  User2 (the recipient) deletes a file/folder “sub” inside of “test”
3.  The folder “sub” will be moved to the trash bin of both User1 (owner) and User2 (recipient)
4.  But User3 will not have a copy of “sub” in their trash bin

When User1 deletes “sub” then it is moved to User1’s trash bin. It is deleted from User2 and User3, but not placed in  
their trash bins.

When you share files, other users may copy, rename, move, and share them with other people, just as they can for any  
computer files; Nextcloud does not have magic powers to prevent this.

**4.3.3 How the deleted files app manages storage space**

To ensure that users do not run over their storage quotas, the Deleted Files app allocates a maximum of 50% of their  
currently available free space to deleted files. If your deleted files exceed this limit, Nextcloud deletes the oldest files  
(files with the oldest timestamps from when they were deleted) until it meets the memory usage limit again.

Nextcloud checks the age of deleted files every time new files are added to the deleted files. By default, deleted files  
stay in the trash bin for 30 days. The Nextcloud server administrator can adjust this value in theconfig.phpfile  
by setting thetrashbin\_retention\_obligationvalue. Files older than thetrashbin\_retention\_obligation  
value will be deleted permanently. Additionally, Nextcloud calculates the maximum available space every time a new  
file is added. If the deleted files exceed the new maximum allowed space Nextcloud will permanently delete those  
trashed files with the soonest expiration until the space limit is met again.

**Note:** Your administrator may have configured the trash bin retention period to override the storage space management.  
See admin documentation for more details.

### 4.4 Desktop and mobile synchronization

For synchronizing files with your desktop computer, we recommend using the Nextcloud Sync Client for Windows,  
macOS and Linux.

The Nextcloud Desktop Sync Client enables you to connect to your Nextcloud Server. You can create folders in your  
home directory, and keep the contents of those folders synced with your Nextcloud server. Simply copy a file into the  
directory and the Nextcloud desktop client does the rest. Make a change to the files on one computer, it will flow across  
the others using these desktop sync clients. You will always have your latest files with you wherever you are.

Its usage is documented separately in the Nextcloud Desktop Client Manual.

**4.4. Desktop and mobile synchronization 29**

**4.4.1 Mobile clients**

Visit your Personal page in your Nextcloud Web interface to find download links for Android and iOS mobile sync  
clients. Or, visit the Nextcloud download page.

### 4.5 Encrypting your Nextcloud files on the server

Nextcloud includes a server side Encryption app, and when it is enabled by your Nextcloud administrator all of your  
Nextcloud data files are automatically encrypted on the server. Encryption is server-wide, so when it is enabled you  
cannot choose to keep your files unencrypted. You don’t have to do anything special, as it uses your Nextcloud login  
as the password for your unique private encryption key. Just log in and out and manage and share your files as you  
normally do, and you can still change your password whenever you want.

Its main purpose is to encrypt files on remote storage services that are connected to your Nextcloud server. This is an  
easy and seamless way to protect your files on remote storage. You can share your remote files through Nextcloud in  
the usual way, however you cannot share your encrypted files directly from the remote service you are using, because  
the encryption keys are stored on your Nextcloud server, and are never exposed to outside service providers.

If your Nextcloud server is not connected to any remote storage services, then it is better to use some other form of  
encryption such as file-level or whole disk encryption. Because the keys are kept on your Nextcloud server, it is possible  
for your Nextcloud administrator to snoop in your files, and if the server is compromised the intruder may get access  
to your files. (Read Encryption in Nextcloud to learn more.)

**4.5.1 Encryption FAQ**

**How can encryption be disabled?**

The only way to disable encryption is to run the “decrypt all” script, which decrypts all files and disables encryption.

**Is it possible to disable encryption with the recovery key?**

Yes, _if_ every user uses the file recovery key, “decrypt all” will use it to decrypt all files.

**Can encryption be disabled without the user’s password?**

If you don’t have the users password or file recovery key, then there is no way to decrypt all files. What’s more, running  
it on login would be dangerous, because you would most likely run into timeouts.

**Is it planned to move this to the next user login or a background job?**

If we did that, then we would need to store your login password in the database. This could be seen as a security issue,  
so nothing like that is planned.

**30 Chapter 4. Files & synchronization**

**Is group Sharing possible with the recovery key?**

If you mean adding users to groups and make it magically work? No. This only works with the master key.

**4.5.2 Using encryption**

Nextcloud encryption is pretty much set it and forget it, but you have a few options you can use.

When your Nextcloud administrator enables encryption for the first time, you must log out and then log back in to create  
your encryption keys and encrypt your files. When encryption has been enabled on your Nextcloud server you will see  
a yellow banner on your Files page warning you to log out and then log back in:

When you log back in it takes a few minutes to work, depending on how many files you have, and then you are returned  
to your default Nextcloud page.

**Note:** You must never lose your Nextcloud password, because you will lose access to your files. Though there is  
an optional recovery option that your Nextcloud administrator may enable; see the Recovery Key Password section  
(below) to learn about this.

**4.5.3 Sharing encrypted files**

Only users who have private encryption keys have access to shared encrypted files and folders. Users who have not yet  
created their private encryption keys will not have access to encrypted shared files; they will see folders and filenames,  
but will not be able to open or download the files. They will see a yellow warning banner that says “Encryption App is  
enabled but your keys are not initialized, please log-out and log-in again.”

Share owners may need to re-share files after encryption is enabled; users trying to access the share will see a message  
advising them to ask the share owner to re-share the file with them. For individual shares, un-share and re-share the

**4.5. Encrypting your Nextcloud files on the server 31**

file. For group shares, share with any individuals who can’t access the share. This updates the encryption, and then the  
share owner can remove the individual shares.

**Recovery key password**

If your Nextcloud administrator has enabled the recovery key feature, you can choose to use this feature for your account.  
If you enable “Password recovery” the administrator can read your data with a special password. This feature enables  
the administrator to recover your files in the event you lose your Nextcloud password. If the recovery key is not enabled,  
then there is no way to restore your files if you lose your login password.

**4.5.4 Files not encrypted**

Only the data in your files is encrypted, and not the filenames or folder structures. These files are never encrypted:

-   Old files in the trash bin.
-   Image thumbnails from the Gallery app.
-   Previews from the Files app.
-   The search index from the full text search app.
-   Third-party app data

Only those files that are shared with third-party storage providers can be encrypted, the rest of the files may not be  
encrypted.

**Change private key password**

This option is only available if the encryption password has not been changed by the administrator, but only the log-in  
password. This can occur if your Nextcloud provider uses an external user back-end (for example, LDAP) and changed  
your login password using that back-end configuration. In this case, you can set your encryption password to your new  
login password by providing your old and new login password. The Encryption app works only if your login password  
and your encryption password are identical.

**32 Chapter 4. Files & synchronization**

### 4.6 File Sharing

Nextcloud users can share files and folders. Possible targets are:

-   public links
-   users
-   groups
-   circles
-   talk conversations
-   users or groups on federated Nextcloud servers

**Note:** Some options may not be available due to administrative configuration. See administrator documentation for  
details.

**4.6.1 Public link shares**

You can share files and folders via public links.

A random 15-digit token will be created. The link will look like https://cloud.example.com/s/  
yxcFKRWBJqYYzp4.

A number of options are available for public _folder_ shares:

-   **Read only** to allow viewing and downloading
-   **Allow upload and editing**
-   With **File drop** , the sharee can only upload files to a folder without seeing the files that are already in that folder.
-   **Hide download** hides the download buttons and the default browser right-click options in order to make down-  
    loading for the sharee harder
-   **Password protect**
-   **Set expiration date** will automatically disable the share
-   **Note to recipient**
-   **Unshare** to revert the share
-   **Add another link** to create multiple public links with different rights

For public _file_ shares, you may allow editing the file with one of Nextcloud’s collaborative editing solutions:

**Note:** Password protection as well as file expiration are not propagated using Federated File Sharing in current  
Nextcloud releases. This will be adjusted in Nextcloud 22.

**4.6. File Sharing 33**

**34 Chapter 4. Files & synchronization**

**4.6. File Sharing 35**

**4.6.2 Internal shares with users and groups**

When sharing with users, groups, circles or members of a Talk conversation, rights for the files or folder contents are  
adjustable:

As a sharee, you can configure if you automatically want to accept all incoming shares and have them added to your  
root folder, or if you want to be asked each time if you want to accept or decline the share.

For adjusting the acceptance setting, go to **Settings** > **Personal** > **Sharing** :

**4.6.3 Others with access**

In order to find out if a file or folder is accessible to others through sharing of a superior folder hierarchy level, click  
on **Others with access** in the sharing tab:

The list shows all users, groups, chats etc. that the current object has been given access to through sharing of a superior  
folder in the hierarchy:

Click on the three dots to:

-   see who initiated the share
-   see where the share was initiated (click to navigate to the folder, as far as you have access there)

**36 Chapter 4. Files & synchronization**

**4.6. File Sharing 37**

**38 Chapter 4. Files & synchronization**

-   unshare the initial share (only accessible for the share owner)

**Note:** This information is only visible to the owner of a file/folder or sharees with resharing rights.

### 4.7 Federated Shares

Federation Sharing allows you to mount file shares from remote Nextcloud servers, in effect creating your own cloud  
of Nextclouds. You can create direct share links with users on other Nextcloud servers.

**4.7.1 Creating a new Federation Share**

Federation sharing is enabled by default. Follow these steps to create a new share with other Nextcloud or ownCloud  
servers:

Go to yourFilespage and click the Share icon on the file or directory you want to share. In the sidebar enter the user-  
name and URL of the remote user in this form:@<nc-server-url>. In this example, that isbob@cloud.  
example.com:

The sharee is receiving a notification in their Nextcloud, allowing them to either accept or decline the incoming share:

**4.7. Federated Shares 39**

**4.7.2 Adding a public share to your Nextcloud**

Nextcloud public link share pages offer an option to add that file or folder as a federated share into your own Nextcloud  
instance. Just enter your@<nc-server-url>just like shown for outbound shares above:

### 4.8 Making anonymous uploads

You may create your own special upload directories so that other people can upload files to you without having to log  
in to the server, and without being a Nextcloud user. They will not be allowed to see the contents of this directory, or  
to make any changes. This is an excellent alternative to sending large attachments via email, using an FTP server, or  
using commercial file-sharing services.

**4.8.1 Setting up your own file drop**

Go to Files and create or choose the folder, the anonymous upload should be made to:

Check Share Link, Allow editing, Hide file listing:

**40 Chapter 4. Files & synchronization**

Now you can send the link to the upload folder manually or by using the Nextcloud send function, if your administrator  
has enabled it.

**4.8.2 Uploading files**

Using the anonymous upload function is simple. You receive a link to the upload folder, click the link, and then you’ll  
see a Nextcloud page with a “ **Click to upload** ” button:

This opens a file picker, and you select the file or directory you want to upload. You’re also able to just drop files into  
the window.

When your upload is completed, the filenames are listed:

**4.8. Making anonymous uploads 41**

### 4.9 Large file uploads

When uploading files through the web client, Nextcloud is limited by PHP and Apache configurations. By default, PHP  
is configured for only 2 megabyte uploads. As this default upload limit is not entirely useful, we recommend that your  
Nextcloud administrator increase the Nextcloud variables to sizes appropriate for users.

Modifying certain Nextcloud variables requires administrative access. If you require larger upload limits than have  
been provided by the default (or already set by your administrator):

-   Contact your administrator to request an increase in these variables
-   Refer to the section in the Administration Documentation that describes how to manage file upload size limits.

### 4.10 Storage quota

Your Nextcloud administrator has the option to set a storage quota on users. Look at your the Personal page to see what  
your quota is, and how much you have used.

It may be helpful to understand how your quota is calculated.

Metadata (thumbnails, temporary files, cache, and encryption keys) takes up about 10% of disk space, but is not counted  
against user quotas. Some apps store information in the database, such as the Calendar and Contacts apps. This data is  
excluded from your quota.

When other users share files with you, the shared files count against the original share owner’s quota. When you share  
a folder and allow other users or groups to upload files to it, all uploaded and edited files count against your quota.  
When you re-share files shared with you, the re-share still counts against the quota of the original share owner.

Encrypted files are a little larger than unencrypted files; the unencrypted size is calculated against your quota.

Deleted files that are still in the trash bin do not count against quotas. The trash bin is set at 50% of quota. Deleted  
file aging is set at 30 days. When deleted files exceed 50% of quota then the oldest files are removed until the total is  
below 50%.

**Note:** Your administrator may have configured the trash bin retention period to override the storage space management.  
See administrator documentation for more details.

**42 Chapter 4. Files & synchronization**

When version control is enabled, the older file versions are not counted against quotas.

If you create a public share via URL and allow uploads, any uploaded files count against your quota.

### 4.11 Version control

Nextcloud supports simple version control system for files. Versioning creates backups of files which are accessible  
via the Versions tab on the Details sidebar. This tab contains the history of the file where you can roll back a file to any  
previous version. Changes made at intervals greater than two minutes are saved in **data/\[user\]/files\_versions**.

To restore a specific version of a file, click the circular arrow to the left. Click on the timestamp to download it.

The versioning app expires old versions automatically to make sure that the user doesn’t run out of space. This pattern  
is used to delete old versions:

-   For the first second we keep one version
-   For the first 10 seconds Nextcloud keeps one version every 2 seconds
-   For the first minute Nextcloud keeps one version every 10 seconds
-   For the first hour Nextcloud keeps one version every minute
-   For the first 24 hours Nextcloud keeps one version every hour
-   For the first 30 days Nextcloud keeps one version every day
-   After the first 30 days Nextcloud keeps one version every week

The versions are adjusted along this pattern every time a new version gets created.

The version app never uses more that 50% of the user’s currently available free space. If the stored versions exceed this  
limit, Nextcloud deletes the oldest versions until it meets the disk space limit again.

**4.11. Version control 43**

### 4.12 Projects

Users can associate files, chats and other items with each other in projects. The various apps will present these items  
in a list, allowing users to immediately jump to them. Projects are Nextcloud wide. When a user shares a file that is  
part of a project, the share recipient can see that project, too. A click on any of the items in a project leads right to it,  
be it a chat, a file or a task.

**4.12.1 Create a new project**

A new project can be created by linking two items together. Start off by opening a file or folders sharing sidebar.

Click _Add to a project_ and select the type of item you want to link with the current file/folder. A selector will open that  
allows you selecting a Talk conversation for example.

**44 Chapter 4. Files & synchronization**

**4.12. Projects 45**

Once the item has been selected a new project is being created and listed in the sharing tab of the sidebar. The same  
project will also appear in the sharing sidebar of the linked items.

The list entry shows quick links to a limited number of items. By opening the context menu, the project can be renamed  
and the full list of items can be expanded.

**4.12.2 Adding more entries to a project**

If another item should be added to an already existing project this can be done by searching for the project name in the  
_Add to a project_ picker.

**4.12.3 Visibility of projects**

Projects do not influence the access and visibility of the different items. Users will only see projects of other users if  
they have access to all contained items.

### 4.13 Transfer Ownership

Users can transfer the ownership of files and folders to other users. Sharing ownerships of those transfered files/folders  
will also be transferred.

1.  Navigate to _Settings_ > _Personal_ > _Sharing_ > _Files_.
2.  Click on _Choose file or folder to transfer_ >> A file picker opens, showing all files and folders in the user’s account.
3.  Pick a file or folder and click on _Choose_ >> The chosen file or folder name gets displayed.
4.  Click on _Change_ to change the choice if necessary.
5.  Pick a new owner by typing their name into the search field next to _New owner_.
6.  Click on _Transfer_.

```
Note: The username autocompletion or listing may be limited due to administrative visibility con-
figuration. See administrator documentation for details.
```

7.  The target user receives a notification where they are being asked whether to accept or reject the incoming transfer.

**46 Chapter 4. Files & synchronization**

**4.13. Transfer Ownership 47**

8.  If accepted, the target user finds the transferred files and folders in their root under a folder _Transferred from_  
    _\[user\] on \[timestamp\]_.
9.  The source user gets informed about the acceptance or rejection by a notification.

### 4.14 Using Federation Shares

Federation Sharing allows you to mount file shares from remote Nextcloud servers, in effect creating your own cloud  
of Nextclouds. You can create direct share links with users on other Nextcloud servers.

**4.14.1 Creating a new Federation Share**

Federation sharing is enabled on new or upgraded Nextcloud installations by default. Follow these steps to create a  
new share with other Nextcloud or ownCloud 9+ servers:

1.  Go to yourFilespage and click the **Share** icon on the file or directory you want to share. In the sidebar enter  
    the username and URL of the remote user in this form:@<oc-server-url>. The form automatically  
    confirms the address that you type and labels it as “remote”. Click on the label.
2.  When your local Nextcloud server makes a successful connection with the remote Nextcloud server you’ll see a  
    confirmation. Your only share option is **Can edit**.

Click the Share button anytime to see who you have shared your file with. Remove your linked share anytime by clicking  
the trash can icon. This only unlinks the share, and does not delete any files.

**4.14.2 Creating a new Federated Cloud Share via email**

Use this method when you are sharing with users on ownCloud 8.x and older.

What if you do not know the username or URL? Then you can have Nextcloud create the link for you and email it to  
your recipient.

When your recipient receives your email they will have to take a number of steps to complete the share link. First they  
must open the link you sent them in a Web browser, and then click the **Add to your Nextcloud** button.

The **Add to your Nextcloud** button changes to a form field, and your recipient needs to enter the URL of their Nextcloud  
or ownCloud server in this field and press the return key, or click the arrow.

Next, they will see a dialog asking to confirm. All they have to do is click the **Add remote share** button and they’re  
finished.

Remove your linked share anytime by clicking the trash can icon. This only unlinks the share, and does not delete any  
files.

**48 Chapter 4. Files & synchronization**

**4.14. Using Federation Shares 49**

**50 Chapter 4. Files & synchronization**

#### CHAPTER

### FIVE

### GROUPWARE

Nextcloud Groupware is a bundle of apps which is consisting of an **Mail** -client (IMAP/POP3) and a **Calendar** and  
**Contacts** server (CalDAV/CardDAV) with the respective web interfaces.

We complete those productivity tools with **Deck** , a project management tool which allows you to create Kanban-style  
task boards and share them with your team.

You can find out more about Nextcloud Groupware on our website.

### 5.1 Using the Contacts app

The Contacts app is not enabled by default in Nextcloud latest and needs to be installed separately from our App Store.

The Nextcloud Contacts app is similar to other mobile contact applications, but with more functionality. Let’s run  
through basic features that will help you maintain your address book in the application.

Below, you will learn how to add contacts, edit or remove contacts, upload a contact picture and manage your Contact  
app address books.

**5.1.1 Adding Contacts**

When you first access the Contacts app, an empty default address book becomes available:

To add contacts into your address book, you can use one of the following methods:

-   Import contacts using a Virtual Contact File (VCF/vCard) file
-   Add contacts manually

The fastest way to add a contact is to use a Virtual Contact File (VCF/vCard) file.

**Importing Virtual Contacts**

To Import Contacts Using a VCF/vCard File:

1.  Find “Settings” at the bottom of the left sidebar, next to the gear button:
2.  Click the gear button. The Contacts app “Import” button will appear:

#### 51

```
Fig. 1: Default Address Book (empty)
```

**52 Chapter 5. Groupware**

**Note:** The Contacts app only supports import of vCards version 3.0 and 4.0.

3.  Click the “Import” button and upload your VCF/vCard file.

After the import is complete, you will see your new contact in your address book.

**Adding Contacts Manually**

If you can’t import virtual contacts, the Contacts app enables you to **add contacts** manually.

To Create a New Contact:

1.  Click the+ New contactbutton.  
    An empty new contact configuration opens in the Application View field:
2.  Specify the new contact information. Changes that you made are implemented immediately.

**Edit or Remove Contact Information**

The Contacts app enables you to edit or remove contact information.

To edit or remove contact information:

1.  Navigate to the specific contact that you want to modify.
2.  Select the information in the field that you want to edit or remove.
3.  Make your modifications or click on the trash bin.

Changes or removals that you made to any contact information are implemented immediately.

**5.1. Using the Contacts app 53**

**Contact Picture**

To add a picture for your new contacts, click on the upload button:

After you have set a contact picture, it will look like this:

If you want to upload a new one, remove it, view it in full size or download it, click on the contacts picture for the  
following options to appear:

**5.1.2 Adding and Managing Address Books**

Clicking on the “Settings” (gear) button at the bottom of the left sidebar provides access to Contacts app settings. This  
field shows all available address books, certain options for each address book, and enables you to create new address  
books, simply by specifying an address books name:

The Contacts settings is also where you can share, export and delete address books. You will find the CardDAV URLs  
there.

See _Groupware_ for more details about syncing your address books with iOS, macOS, Thunderbird and other CardDAV  
clients.

### 5.2 Using the Calendar app

**Note:** The Calendar app comes installed with Nextcloud Hub by default, but can be disabled. Please ask your Admin-  
istrator for it.

The Nextcloud Calendar app works similar to other calendar applications you can sync your Nextcloud calendars and  
events with.

When you first access the Calendar app, a default first calendar will be created for you.

**54 Chapter 5. Groupware**

**5.2. Using the Calendar app 55**

**5.2.1 Managing your calendars**

**Create a new Calendar**

If you plan on setting up a new calendar without transferring any old data from your previous calendar, creating a new  
calendar is the way you should go.

1.  Click on+ New Calendarin the left sidebar.
2.  Type in a name for your new calendar, e.g. “Work”, “Home” or “Marketing planning”.
3.  After clicking on the checkmark, your new calendar is created and can be synced across your devices, filled with  
    new events and shared with your friends and colleagues.

**Import a Calendar**

If you want to transfer your calendar and their respective events to your Nextcloud instance, importing is the best way  
to do so.

1.  Click on the settings-icon labeled withSettings & Importat the left-bottom.
2.  After clicking on+ Import Calendaryou can select one or more calendar files from your local device to  
    upload.
3.  The upload can take some time and depends on how big the calendar you import is.

**56 Chapter 5. Groupware**

**Note:** The Nextcloud Calendar application only supports iCalendar-compatible.ics-files, defined in RFC 5545.

**Edit, Export or Delete a Calendar**

Sometimes you may want to change the color or the entire name of a previous imported or created calendar. You may  
also want to export it to your local hard drive or delete it forever.

**Note:** Please keep in mind that deleting a calendar is a irreversible action. After deletion, there is no way of restoring  
the calendar unless you have a local backup.

1.  Click on the three-dot-menu of the respective calendar.
2.  Click on _Edit name_ , _Edit color_ , _Export_ or _Delete_.

**Sharing calendars**

You may share your calendar with other users or groups. Calendars may be shared with write access or read-only.  
When sharing a calendar with write access, users with whom the calendar is shared will be able to create new events  
into the calendar as well as edit and delete existing ones.

**Note:** Calendar shares currently cannot be accepted or rejected. If you want to stop having a calendar that someone  
shared with you, you can click on the 3-dot menu next to the calendar in the calendar list and click on “Unshare from  
me”. Calendars shared with a group cannot be unshared by individuals.

**5.2. Using the Calendar app 57**

**58 Chapter 5. Groupware**

**Publishing a calendar**

Calendars can be published through a public link to make them viewable (read-only) to external users. You may create  
a public link by opening the share menu for a calendar and clicking on « + » next to « Share link ». Once created you  
can copy the public link to your clipboard or send it through email.

There’s also an « embedding code » that provides an HTML iframe to embed your calendar into public pages.

Multiple calendars can be shared together by adding their unique tokens to the end of an embed link. Individual tokens  
can be found at the end of each calendar’s public link. The full address will look likehttps://cloud.example.  
com/index.php/apps/calendar/embed/\-\-

To change the default view or date of an embedded calendar, you need to provide an URL that looks likehttps:/  
/cloud.example.com/index.php/apps/calendar/embed///. In this url you need to  
replace the following variables:

-   with the calendar’s token,
-   with one ofmonth,week,day,listMonth,listWeek,listDay. The default view ismonthand the  
    normally used list islistMonth,
-   withnowor any date with the following format\-\-(e.g.2019-12-28).

On the public page, users are able to get the subscription link for the calendar and export the whole calendar directly.

**Subscribe to a Calendar**

You can subscribe to iCal calendars directly inside of your Nextcloud. By supporting this interoperable standard (RFC

5545.  we made Nextcloud calendar compatible to Google Calendar, Apple iCloud and many other calendar-servers you  
    can exchange your calendars with, including subscription links from calendar published on other Nextcloud instances,  
    as described above.

1.  Click on+ New Subscriptionin the left sidebar.
2.  Type in or paste the link of the shared calendar you want to subscribe to.

Finished. Your calendar subscriptions will be updated regularly.

**Note:** Subscriptions are refreshed every week by default. Your administrator may have changed this setting.

**5.2.2 Managing Events**

**Create a new event**

Events can be created by clicking in the area when the event is scheduled. In the day- and week-view of the calendar  
you just click, pull and release your cursor over the area when the event is taking place.

The month-view only requires a single click into the area of the target day.

After that, you can type in the event’s name (e.g. **Meeting with Lukas** ), choose the calendar in which you want to save  
the event to (e.g. **Personal** , **Work** ), check and concretize the time span or set the event as an all-day event. Optionally  
you can specify a location and a description.

If you want to edit advanced details such as the **Attendees** or **Reminders** , or if you want to set the event as a repeating-  
event, click on theMorebutton to open the advanced sidebar editor.

**5.2. Using the Calendar app 59**

**Note:** If you always want to open the advanced sidebar editor instead of the simple event editor popup, you can set a  
Skip simple event editorcheckmark in theSettings & Importsection of the app.

Clicking on the blueCreatebutton will finally create the event.

**Edit or delete an event**

If you want to edit or delete a specific event, you just need to click on it. After that you will be able to re-set all event  
details and open the advanced sidebar-editor by clicking onMore.

Clicking on theUpdatebutton will update the event. To cancel your changes, click on the close icon on top right of  
the popup or sidebar editor.

If you open the sidebar view and click the three dot menu next to the event name, you have an option to export the event  
as an.icsfile or remove the event from your calendar.

**Tip:** If you delete events they will go into your _trash bin_. You can restore accidentally deleted events there.

**Invite attendees to an event**

You may add attendees to an event to let them know they’re invited. They will receive an email invitation and will be  
able to confirm or cancel their participation to the event. Attendees may be other users on your Nextcloud instances,  
contacts in your address books and direct email addresses. You may also change the level of participation per attendees,  
or disable the email information for a specific attendee.

**60 Chapter 5. Groupware**

**5.2. Using the Calendar app 61**

**Tip:** When adding other Nextcloud users as attendees to an event, you may access their free-busy information if  
available, helping you determine when the best time slot for your event is. Set your _working hours_ to let others know  
when you are available. Free-busy information is only available for other users on the same Nextcloud instance.

```
Attention: Only the calendar owner can send out invitations. The sharees are not able to do that, whether they
have write access to the event’s calendar or not.
```

```
Attention: The server administration needs to setup the e-mail server in theBasic settingstab, as this mail
will be used to send invitations.
```

**Assign rooms and resources to an event**

Similar to attendees you can add rooms and resources to your events. The system will make sure that each room and  
resource is booked without conflict. The first time a user adds the room or resource to an event, it will show as accepted.  
Any further events at overlapping times will show the room or resource as rejected.

**Note:** Rooms and resources are not managed by Nextcloud itself and the Calendar app will not allow you to add or  
change a resource. Your Administrator has to install and possibly configure resource back ends before you can use them  
as a user.

**Set up reminders**

You can set up reminders to be notified before an event occurs. Currently supported notification methods are:

-   Email notifications
-   Nextcloud notifications

You may set reminders at a time relative to the event or at a specific date.

**Note:** Only the calendar owner and people or groups with whom the calendar is shared with write access will get  
notifications. If you don’t get any notifications but think you should, your Administrator could also have disabled this  
for your server.

**Note:** If you synchronize your calendar with mobile devices or other 3rd-party clients, notifications may also show  
up there.

**62 Chapter 5. Groupware**

**Add recurring options**

An event may be set as “recurring”, so that it can happen every day, week, month or year. Specific rules can be added  
to set which day of the week the event happens or more complex rules, such as every fourth Wednesday of each month.

You can also tell when the recurrence ends.

**Trash bin**

If you delete events, tasks or a calendar in Calendar, your data is not gone yet. Instead, those items will be collected  
in a _trash bin_. This offers you to undo a deletion. After a period which defaults to 30 days (your administration may  
have changed this setting), those items will be deleted permanently. You can also permanently delete items earlier if  
you wish.

TheEmpty trash binbuttons will wipe all trash bin contents in one step.

**Tip:** The trash bin is only accessible from the Calendar app. Any connected application or app won’t be able to display  
its contents. However, events, tasks and calendars deleted in connected applications or app will also end up in the trash  
bin.

**5.2. Using the Calendar app 63**

**64 Chapter 5. Groupware**

**5.2.3 Responding to invitations**

You can directly respond to invitations inside the app. Click on the event and select your participation status. You can  
respond to an invitation by accepting, declining or accepting tentatively.

You can respond to an invitation from the sidebar too.

**5.2.4 Availability (Working Hours)**

The general availability independent of scheduled events can be set in the groupware settings of Nextcloud. These  
settings will be reflected in the free-busy view when you _schedule a meeting with other people_ in Calendar. Some  
connected clients like Thunderbird will show this data as well.

**5.2. Using the Calendar app 65**

**5.2.5 Birthday calendar**

The birthday calendar is a auto-generated calendar which will automatically fetch the birthdays from your contacts.  
The only way to edit this calendar is by filing your contacts with birthday dates. You can not directly edit this calendar  
from the calendar-app.

**Note:** If you do not see the birthday calendar, your Administrator may have disabled this for your server.

**5.2.6 Appointments**

As of Calendar v3 the app can generate appointment slots which other Nextcloud users but also people without an  
account on the instance can book. Appointments offer fine-granular control over when you are possibly free to meet  
up. This can eliminate the need to send emails back and forth to settle on a date and time.

In this section we’ll use the term _organizer_ for the person who owns the calendar and sets up appointment slots. The  
_attendee_ is the person who books one of the slots.

**66 Chapter 5. Groupware**

**5.2. Using the Calendar app 67**

**Creating an appointment configuration**

As an organizer of appointments you open the main Calendar web UI. In the left sidebar you’ll find a section for  
appointments, were you can open the dialogue to create a new one.

One of the basic infos of every appointment is a title describing what the appointment is about, e.g. “One-on-one” when  
a user wants to offer colleagues a personal call. The duration of the appointment can be picked from a predefined list.  
Next, you can set the desired increment. The increment is the rate at which possible slots are available. For example,  
you could have one hour long slots, but you give them away at 30 minute increments so an attendee can book at 9:00AM  
but also at 9:30AM. Optional infos about location and a description give the attendees some more context.

Every booked appointment will be written into one of your calendars, so you can chose which one that should be. Only  
slots that do not conflict with existing events in your calendars will be shown to attendees.

Appointments can be _public_ or _private_. Public appointments can be discovered through the profile page of a Nextcloud  
user. Private appointments are only accessible to the people who receive the secret URL.

The organizer of an appointment can specify at which times of the week it’s generally possible to book a slot. This  
could be the working hours but also any other customized schedule.

Some appointments require time to prepare, e.g. when you meet at a venue and you have to drive there. The organizer  
can chose to select a time duration that must be free. Only slots that do not conflict with other events during the  
preparation time will be available. Moreover there is the option to specify a time after each appointment that has to be  
free.

To prevent an attendee from booking too short notice it’s possible to configure how soon the next possible appointment  
might take place.

Setting a maximum number of slots per day can limit how many appointments are possibly booked by attendees.

The configured appointment will then be listed in the left sidebar. You can copy its link and share it with the target  
attendees, or let them discover your public appointment via the profile page.

**Booking an appointment**

The booking page shows an attendee the title, location, description and length of an appointment. For a selected day  
there will be a list with all the possible time slots. On days with no available slots, too many conflicts or a reached daily  
maximum limit of already booked appointments, the list might be empty.

For the booking users have to enter a name and an email address. Optionally they can also add a comment.

To verify that the email is valid, a confirmation email will be sent. Only after clicking the confirmation link from the  
email the appointment booking will be finished. Until then the time slot might also be booked by another user who  
confirms their booking earlier. The system will detect the conflict and offer to pick a new time slot.

**Working with the booked appointment**

Once the booking is done, the organizer will find an event in their calendar with the appointment details and the _attendee_.  
As with any other event that has attendees, changes and cancellations will trigger a notification to the attendee’s email.

If attendees wish to cancel the appointment they have to get in contact with the organizer, so that the organizer can  
cancel or even delete the event.

**68 Chapter 5. Groupware**

### 5.3 Synchronizing with Android

**5.3.1 Files and notifications**

1.  Install the Nextcloud Android client from Google Play Store or from F-Droid.
2.  Start the app. There are two ways of setting it up:  
    _Either_ : enter your server URL, continue, enter your user name and password and confirm to grant access.  
    _Or_ : In Nextcloud’s web GUI, go to the user preferences, go to **Security**. Generate an App password, click  
    “Generate QR code” and tap the QR scanner icon in the Nextcloud app, point your phone’s camera towards the  
    screen.

**5.3.2 Contacts and Calendar**

**With the Nextcloud mobile app**

1.  Install DAVx^5 (formerly known as DAVDroid) on your Android device, from Google Play Store or from F-Droid.
2.  In the Nextcloud mobile, go to **Settings** / **More** , tap on “ **Sync calendars & contacts** ”.
3.  Now, DAVx^5 will open Nextcloud’s Webflow login window, where you will have to enter your credentials and  
    grant access.
4.  DAVx^5 will open and ask you to create an account. Set the account name to one of your choosing, and set  
    **Contact Group Method** to **Groups are per-contact categories**.
5.  After this, DAVx^5 will close and the Nextcloud app reappears. In order to finish setup, you have to manually  
    launch DAVx^5 again.
6.  Tap on the icon for the account DAVx^5 has just created, when requested grant DAVx^5 access to your calendars  
    and contacts. Optionally install OpenTasks (Google Play Store or F-Droid) and grant DAVx^5 access to your tasks,  
    too.
7.  When you tap the icon for the account DAVx^5 has set up, it will discover the available address books and calendars.  
    Choose which ones you want to synchronize and finish.

**Without the Nextcloud mobile app**

If you do not want to install the Nextcloud mobile app, the following steps are required:

1.  Install DAVx^5 (formerly known as DAVDroid) on your Android device, from Google Play Store or from F-Droid.
2.  Optionally install OpenTasks (Google Play Store or F-Droid).
3.  Create a new account (“+” button).
4.  Select **Connection with URL and username**. **Base URL:** URL of your Nextcloud instance (e.g.https://  
    sub.example.com/remote.php/dav) and **Contact Group Method:** as credentials.
5.  Choose the optionGroups are per-contact categories.
6.  Click **Connect**.
7.  Select the data you want to sync.
8.  When requested, grant access permissions to DAVx^5 for your contacts, calendars and optionally tasks.

**5.3. Synchronizing with Android 69**

**Note:** Enter your email address as DAVx^5 account name (mandatory if you want to be able to send calendar invitation).  
If your email address is registered in your Nextcloud preferences and you have set up your account using the Nextcloud  
mobile app, this all should be aready the case.

**Tip:** DAVx^5 lists the calendar subscriptions made through the Nextcloud Calendar app, but you need to install the  
ICSx^5 (formerly known as ICSDroid) app on your Android device, from the Google Play Store or from F-Droid to sync  
them.

### 5.4 Synchronizing with iOS

**5.4.1 Calendar**

1.  Open the settings application.
2.  Select Calendar.
3.  Select Accounts.
4.  Select Add Account.
5.  Select Other as account type.
6.  Select Add CalDAV account.
7.  For server, type the domain name of your server i.e.example.com.
8.  Enter your user name and password.
9.  Select Next.

Your calendar will now be visible in the Calendar application.

**Note:** Beginning with iOS 12 an SSL encryption is necessary. Therefore do **not** disable **SSL** (For this reason a  
certificate is required at your domain, https://letsencrypt.org/ will do).

**5.4.2 Contacts**

1.  Open the settings application.
2.  Select Contacts.
3.  Select Accounts.
4.  Select Add Account.
5.  Select Other as account type.
6.  Select Add CardDAV account.
7.  For server, type the domain name of your server i.e.example.com.
8.  Enter your user name and password.
9.  Select Next.

**70 Chapter 5. Groupware**

You should now find your contacts in the address book of your iPhone.

**Note:** Beginning with iOS 12 an SSL encryption is necessary. Therefore do **not** disable **SSL** (For this reason a  
certificate is required at your domain, https://letsencrypt.org/ will do).

If it’s still not working, have a look at Troubleshooting Contacts & Calendar or Troubleshooting Service Discovery.

### 5.5 Synchronizing with macOS

**5.5.1 Setup your Accounts**

In the following steps you will add your server resources for **CalDAV** (Calendar) and **CardDAV** (Contacts) to your  
Nextcloud.

1.  Open the **system preferences** of your macOS device.
2.  Navigate to **Internet Accounts** :
3.  Click on **Add Other Account...** and click on **CalDAV Account** for Calendar or **CardDAV Account** for Con-  
    tacts:

**Note:** You can not setup Calendar/Contacts together. You need to setup them in **separate accounts**.

4.  Select **Manual** as Account-Type and type in your respective credentials:  
    **Username** : Your Nextcloud username or email  
    **Password** : Your generated app-password/token (Learn more).

**5.5. Synchronizing with macOS 71**

```
Server Address : URL of your Nextcloud server (e.g.https://cloud.example.com)
```

5.  Click on **Sign In**.

For **CalDAV (Calendar)** : You can now select, with which applications you want to use this resource. In the most  
cases, this will be the “Calendar” application, sometimes you may also want to use it for your **Tasks and reminders**.

**5.5.2 Troubleshooting**

-   macOS does **not** support syncing CalDAV/CardDAV over non-encryptedhttp://connections. Make sure you  
    havehttps://enabled and configured on server- and client-side.
-   **Self-signed certificates** need to be properly set up in the macOS keychain.

**72 Chapter 5. Groupware**

**5.5. Synchronizing with macOS 73**

### 5.6 Synchronizing with Thunderbird

Thunderbird is a feature-rich and mature mail client that can be turned into a full-fledged PIM. However, it lacks  
support for address book synchronisation via CardDAV and it also lacks the ability to automatically discover calendars  
and address books available on the server. Therefore, to synchronise with Nextcloud, add-ons are required, which can  
be easily installed through Thunderbird’s add-on manager.

**5.6.1 Recommended method**

For this method, you need to have two add-ons installed:

1.  TbSync.
2.  The TbSync provider for CalDAV and CardDAV.

When they are installed, if you are on Windows, go to **Extras** / **Synchronisation settings (TbSync)** or  
**Edit/Synchronisation settings (TbSync)** if on Linux, and then:

-   In the account manager choose “ **Add account** / **CalDAV / CardDAV account** ”
-   In the next window, go with the default called **Automatic configuration** and click **next**
-   Enter an **account name** , which you can freely choose, **user name** , **password** and the **URL of your server** and  
    click **next**
-   In the next window, TbSync should have autodiscovered the CalDAV and CardDAV addresses. When it has, click  
    **Finish**
-   Now check the box **Enable and synchronize this account**. TbSync will discover all address books and calenders  
    your account has access to on the server
-   Check the box next to each calender and address book you want to have synchronised, also set how often you  
    want them to be synchronised and push the button **sychronize now**

**74 Chapter 5. Groupware**

-   After the first successful synchronisation is complete, you can close the window. Henceforth, TbSync will do  
    the work for you. You are done and can skip the next sections (unless you need a more advanced address book)

**5.6.2 Alternative: Using the CardBook add-on (Contacts only)**

CardBook is an advanced alternative to Thunderbird’s address book, which supports CardDAV. You can have TbSync  
and CardBook installed in parallel.

1.  Click the CardBook icon in the upper right corner of Thunderbird:
2.  In CardBook:
    -   Address book > New Address book **Remote** > Next
    -   Select **CardDAV** , fill in the address of your Nextcloud server, your user name and password
3.  Click on “Validate”, click Next, then choose the name of the address book and click Next again:

**5.6. Synchronizing with Thunderbird 75**

5.  When you are finished, CardBook synchronizes your address books. You can always trigger a synchronisation  
    manually by clicking “Synchronize” in the top left corner of CardBook:

**5.6.3 The old method: Manually subscribing to calendars**

This method is only needed if you don’t want to install TBSync.

1.  Go to your Nextcloud Calendar and click on the 3 dotted menu for the calendar that you want to synchronize  
    which will display an URL that looks something like this:  
    https://cloud.nextcloud.com/remote.php/dav/calendars/daniel/personal/
2.  Go to the calendar view in Thunderbird and right click in the calendar menu to the left (where the names of the  
    calendars are) to add a **New Calendar**.
3.  Choose **On the Network** :

**76 Chapter 5. Groupware**

4.  Choose **CalDAV** and fill in the missing information:

**5.6. Synchronizing with Thunderbird 77**

**5.6.4 Fix for Thunderbird 60**

If you are still using Thunderbird 60, you need to change a configuration setting to make CalDAV/CardDAV work  
around Thunderbird bug #1468918 as described here.

### 5.7 Synchronizing with KDE Kontact

KOrganizer, Kalendar and KAddressBook can synchronize your calendar, contacts and tasks with a Nextcloud server.

This can be done by following these steps depending on if you use KOrganizer or Kalendar:

In KOrganizer:

1.  Open KOrganizer and in the calendar list (bottom left) right-click and chooseAdd Calendar:

**78 Chapter 5. Groupware**

2.  In the resulting list of resources, pickDAV groupware resource:

**5.7. Synchronizing with KDE Kontact 79**

In Kalendar:

1.  Open Kalendar and in the menu bar open the setting and then chooseCalendar Sources->Add Calendar:

**80 Chapter 5. Groupware**

2.  In the resulting list of resources, pickDAV groupware resource:

**5.7. Synchronizing with KDE Kontact 81**

In KOrganizer and Kalendar:

3.  Enter your username. As password, you need to generate an app-password/token (Learn more):

**82 Chapter 5. Groupware**

4.  ChooseNextcloudas Groupware server option:

**5.7. Synchronizing with KDE Kontact 83**

5.  Enter your Nextcloud server URL and, if needed, installation path (anything that comes after the first /, for  
    examplemynextcloudinhttps://exampe.com/mynextcloud). Then click next:

**84 Chapter 5. Groupware**

6.  You can now test the connection, which can take some time for the initial connection. If it does not work, you  
    can go back and try to fix it with other settings:

**5.7. Synchronizing with KDE Kontact 85**

**86 Chapter 5. Groupware**

7.  Pick a name for this resource, for exampleWorkorHome. By default, both CalDAV (Calendar) and CardDAV  
    (Contacts) are synced:

**5.7. Synchronizing with KDE Kontact 87**

**Note:** You can set a manual refresh rate for your calendar and contacts resources. By default this setting is set to 5  
minutes and should be fine for the most use cases. When you create a new appointment it is synced to Nextcloud right  
away. You may want to change this for saving your power or cellular data plan, so that you can update with a right-click  
on the item in the calendar list.

8.  After a few seconds to minutes depending on your internet connection, you will find your calendars and contacts  
    inside the KDE Kontact applications KOrganizer, Kalendar and KAddressBook as well as Plasma calendar applet:

**88 Chapter 5. Groupware**

**5.7. Synchronizing with KDE Kontact 89**

**90 Chapter 5. Groupware**

### 5.8 Synchronizing with the GNOME desktop

The GNOME desktop has built-in support for Nextcloud’s calendar, contacts and tasks which will be displayed by the  
Evolution PIM or the Calendar, Tasks and Contacts app as well has for files, which it integrates into the Nautilus file  
manager via WebDAV. The latter works only while the computer is connected.

This can be done by following these steps:

1.  In the GNOME settings, open Online Accounts.
2.  Under “Add an account” pickNextcloud:
3.  Enter your server URL, username and password. If you have enabled two factor authentification, you need to  
    generate an app-password/token, because GNOME Online Accounts doesn’t support Nextcloud’s webflow login  
    yet (Learn more):

**5.8. Synchronizing with the GNOME desktop 91**

4.  In the next window, select which resources GNOME should access and press the cross in the top left to close:

**92 Chapter 5. Groupware**

Nextcloud tasks, calendars and contacts should now be visible in the Evolution PIM, the task, contacts and calendars  
app.

Files will be shown as a WebDAV resource in the Nautilus file manager (and also be available in the GNOME file  
open/save dialogues). Documents should be integrated into the GNOME Documents app.

All resources should also be searchable from anywhere by pressing the Windows key and entering a search term.

### 5.9 Synchronizing with Windows 10

**5.9.1 Calendar**

1.  In your browser, navigate to the Nextcloud Calendar app. Under “Settings & import”, copy the address using  
    “Copy iOS/macOS CalDAV address” into your clipboard.
2.  Launch the Windows 10 Calendar app. Then, click the settings icon (gear icon) and select “Manage accounts”.
3.  Click “Add account” and choose “iCloud”.
4.  Enter an email, username and password. None of this information has to be valid-it will all be changed in the  
    upcoming steps.
5.  Click “Done”. A message should appear indicating the settings were saved successfully.
6.  In the “Manage Accounts” menu, click on the iCloud account created in previous steps, and select “Change  
    settings”. Then, click on “Change mailbox sync settings”.
7.  Scroll to the bottom of the dialog box, select “Advanced mailbox settings”. Scroll once more to the bottom of  
    the dialog box and paste your CalDAV URL in the field labelled “Calendar server (CalDAV)”.
8.  Click “Done”. Enter your Nextcloud username and password in the appropriate fields, and change the account  
    name to whatever you prefer (e. g. “Nextcloud Calendar”). Click “Save”.

**5.9.2 Contacts**

1.  In the bottom left of the Contacts View (in Nextcloud Contacts) look for a little impeller symbol that looks like  
    this:

which will display a URL that looks something like this: https://cloud.nextcloud.com/remote.php/dav/addressbooks/  
users/daniel/Thunderbird/

2.  Launch the Windows 10 Calendar app. Then, click the settings icon (gear icon) and select “Manage accounts”.
3.  Click “Add account” and choose “iCloud”.
4.  Enter an email, username and password. None of this information has to be valid-it will all be changed in the  
    upcoming steps.
5.  Click “Sign in” and then “Done”. A message should appear indicating the settings were saved successfully.
6.  In the “Manage Accounts” menu, click on the iCloud account created in previous steps, and select “Change  
    settings”. Then, click on “Change mailbox sync settings”.
7.  Scroll to the bottom of the dialog box, select “Advanced mailbox settings”. Scroll once more to the bottom of  
    the dialog box and paste your CardDAV URL in the field labelled “Contacts server (CardDAV)”.

**5.9. Synchronizing with Windows 10 93**

8.  Click “Done”. Enter your Nextcloud username and password in the appropriate fields, and change the account  
    name to whatever you prefer (e. g. “Nextcloud Contacts”). Click “Save”.

**5.9.3 Troubleshooting**

After following all these steps, your Nextcloud calendar should synchronize. If not, check your username and password.  
Otherwise, repeat these steps.

**NOTE: You will not be able to synchronize your calendar if you have two-factor authentication enabled. Follow  
the steps below to get an app password that can be used with the Calendar client app:**

1.  Log into Nextcloud. Click on your user icon, then click on “Settings”.
2.  Click on “Security”, then locate a button labeled “Create new app password”. Next to this button, enter “Windows  
    10 Calendar app”. Then, click the button, copy and paste the password. Use this password instead of your  
    Nextcloud password for Step 8.

Special thanks to this Reddit user for their post: https://www.reddit.com/r/Nextcloud/comments/5rcypb/using\_the\_  
windows\_10\_calendar\_application\_with/

**5.9.4 Contacts**

1.  Repeat steps 1–7 from the Calendar instructions. If you already have setup the Calendar synchronization, you  
    can use the same account for this.
2.  In the “Advanced mailbox settings” paste your CalDAV URL in the field labelled “Contacts server (CardDAV)”.
3.  Replace the path “principals” within the URL with “addressbooks”.
4.  Click “Done”. Enter your Nextcloud username and password in the appropriate fields, and change the account  
    name to whatever you prefer (e. g. “Nextcloud”). Click “Save”.

**94 Chapter 5. Groupware**

#### CHAPTER

### SIX

### TALK

Nextcloud Talk offers audio/video and text chat integrated in Nextcloud. It offers a web interface as well as mobile  
apps.

You can find out more about Nextcloud Talk on our website.

### 6.1 Basics of Nextcloud Talk

Nextcloud Talk lets you chat and have video calls on your own server.

Chats and calls take place in conversations. You can create any number of conversations. There are two kinds of  
conversations:

1.  **One-on-one conversations.** This is where you have a private chat or call with another Talk user. You can’t add  
    other people to this conversation or share it with a link. You start a direct one-on-one chat by looking for another  
    user in the search bar and then clicking their name.
2.  **Group conversations.** Besides the person who created the conversation, a group conversation can have any  
    number of people in it. A group conversation can be shared publicly with a link, so external guest users can join  
    a call. It can also be listed, so other people on your Nextcloud server can join the conversation.

#### 95

**6.1.1 Creating a chat**

You can create a direct, one-on-one chat by searching for the name of a user, a group or a circle and clicking it. For a  
single user, a conversation is immediately created and you can start your chat. For a group or circle you get to pick a  
name and settings before you create the conversation and add the participants.

If you want to create a custom group conversation, click theplusbutton next to the search field. You can then pick  
a name for the conversation and select if the conversation should be open to external users and if other users on the  
server can see and join the conversation.

**96 Chapter 6. Talk**

In the second step, you get to add participants and finalize the creation of the conversation.

**6.1. Basics of Nextcloud Talk 97**

You can cancel the creation of a conversation by clicking outside the white menu area at any time.

**98 Chapter 6. Talk**

**6.1.2 Sharing files in a chat**

You can share files in a chat in 3 ways.

First, you can simply drag’n’drop them on the chat.

Second, you can select a file from your Nextcloud Files or a file manager by choosing the little paperclip and selecting  
where you’d like to pick the file from.

**6.1. Basics of Nextcloud Talk 99**

You can add more files until you are done and decide to share the files.

**100 Chapter 6. Talk**

All users will be able to click the files to view, edit or download them, irrespective of them having a user account. Users  
with an account will have the file automatically shared with them while external guest users will get them shared as a  
public link.

**6.1. Basics of Nextcloud Talk 101**

**6.1.3 Inserting emoji**

You can add emoji using the picker on the left of the text input field.

**6.1.4 Replying to messages and more**

You can reply to a message using the arrow that appears when you hover a message.

**102 Chapter 6. Talk**

In the...menu you can also choose to reply privately. This will open a one-on-one chat.

Here you can also create a direct link to the message or mark it unread so you will scroll back there next time you enter  
the chat. When it is a file, you can view the file in Files.

**6.1.5 Managing a conversation**

You are always moderator in your new conversation. In the participant list you can promote other participants to  
moderators using the...menu to the right of their user name, assign them custom permissions or remove them from  
the conversation.

**6.1. Basics of Nextcloud Talk 103**

Moderators can configure the conversation. SelectConfiguration settingsfrom the gear menu of the conversation  
on the top to access the settings.

**104 Chapter 6. Talk**

Here you can configure the description, guest access, if the conversation is visible to others on the server and more.

**6.1. Basics of Nextcloud Talk 105**

**106 Chapter 6. Talk**

**6.1.6 Starting a call**

When you’re in a conversation, you can start a call any time with theStart callbutton. Other participants will get  
notified and can join the call. If somebody else has started a call already, the button will change in a greenJoin call  
button.

During a call, you can mute your microphone and disable your video with the buttons on the right side of the top bar,  
or using the shortcutsMto mute audio andVto disable video. You can also use the space bar to toggle mute. When  
you are muted, pressing space will unmute you so you can speak until you let go of the space bar. If you are unmuted,  
pressing space will mute you until you let go.

You can hide your video (useful during a screen share) with the little arrow just above the video stream. Bring it back  
with the little arrow again.

You can access your settings and choose a different webcam, microphone and other settings in the...menu in the top  
bar.

**6.1. Basics of Nextcloud Talk 107**

**6.1.7 Starting a screen share**

You can click the monitor icon on your video stream to share your screen. Depending on your browser, you will get the  
option to share a monitor, an application window or a single browser tab.

**6.1.8 Changing view in a call**

You can switch the view in a call with the little four-block icon in the top-right between promoted-view and grid view.  
The grid view will show everyone equally big and if the people do not fit on the screen, buttons will appear on the left  
and right that let you navigate.

**108 Chapter 6. Talk**

The promoted view shows the speaker large and others in a row below. If the people do not fit on the screen, buttons  
will appear on the left and right that let you navigate.

**6.1. Basics of Nextcloud Talk 109**

### 6.2 Advanced Talk features

Nextcloud Talk has a number of advanced features users might find useful.

**6.2.1 Matterbridge**

Matterbridge integration in Nextcloud Talk makes it possible to create ‘bridges’ between Talk conversations and con-  
versations on other chat services like MS Teams, Discord, Matrix and others. You can find a list of supported protocols  
on the Matterbridge github page.

A moderator can add a Matterbridge connection in the chat conversation settings.

**110 Chapter 6. Talk**

Each of the bridges has its own need in terms of configuration. Information for most is available on the Matterbridge  
wiki and can be accessed behindmore informationmenu in the...menu. You can also access the wiki directly.

**6.2. Advanced Talk features 111**

**6.2.2 Lobby**

The lobby feature allows you to show guests a waiting screen until the call starts. This is ideal for webinars with external  
participants, for example.

You can choose to let the participants join the call at a specific time, or when you dismiss the lobby manually.

**6.2.3 Commands**

Nextcloud allows users to execute actions using commands. A command typically looks like:

```
/wiki airplanes
```

Administrators can configure, enable and disable commands. Users can use thehelpcommand to find out what  
commands are available.

```
/help
```

**112 Chapter 6. Talk**

Find more information in the administrative documentation for Talk.

**6.2.4 Talk from Files**

In the Files app, you can chat about files in the sidebar, and even have a call while editing it. You first have to join the  
chat.

**6.2. Advanced Talk features 113**

**114 Chapter 6. Talk**

You can then chat or have a call with other participants, even when you start editing the file.

In Talk, a conversation will be created for the file. You can chat from there, or go back to the file using the...menu  
in the top-right.

**6.2. Advanced Talk features 115**

**6.2.5 Create tasks from chat or share tasks in chat**

If Deck is installed, you can use the...menu of a chat message and turn the message into a Deck task.

**116 Chapter 6. Talk**

From within Deck, you can share tasks into chat conversations.

**6.2. Advanced Talk features 117**

### 6.3 Join a call or chat as guest

Nextcloud Talk offers audio/video call and text chat integrated in Nextcloud. It offers a web interface as well as mobile  
apps.

You can find out more about Nextcloud Talk on our website.

**118 Chapter 6. Talk**

**6.3.1 Joining a chat**

If you received a link to a chat conversation, you can open this in your browser to join the chat.

You can change your name by clicking theEditbutton, located top-right.

Your camera and microphone settings can be found in theSettingsmenu. There you can also find a list of shortcuts  
you can use.

**6.3. Join a call or chat as guest 119**

**6.3.2 Joining a call**

You can start a call any time with theStart callbutton. Other participants will get notified and can join the call. If  
somebody else has started a call already, the button will change in a greenJoin callbutton.

Before actually joining the call you will see a device check, where you can pick the right camera and microphone,  
enable background blur or even join with any devices.

**120 Chapter 6. Talk**

During a call, you can find the Camera and Microphone settings in the...menu in the top bar.

**6.3. Join a call or chat as guest 121**

During a call, you can mute your microphone and disable your video with the buttons in the top-right, or using the  
shortcutsMto mute audio andVto disable video. You can also use thespace barto toggle mute. When you are  
muted, pressing space will unmute you so you can speak until you let go of the space bar. If you are unmuted, pressing  
space will mute you until you let go.

You can hide your video (useful during a screen share) with the little arrow just above the video stream. Bring it back  
with the little arrow again.

**6.3.3 Starting a screen share**

You can click the monitor icon on your video stream to share your screen. Depending on your browser, you will get the  
option to share a monitor, an application window or a single browser tab.

**6.3.4 More settings**

In the conversation menu you can choose to go full-screen. You can also do this by using theFkey on your keyboard.  
In the conversation settings, you can find notification options and the full conversation description.

**122 Chapter 6. Talk**

**6.3. Join a call or chat as guest 123**

**124 Chapter 6. Talk**

#### CHAPTER

### SEVEN

### SETTING YOUR PREFERENCES

As a user, you can manage your personal settings.

To access your personal settings:

1.  Click on your profile picture in the top, right corner of your Nextcloud instance.  
    The Personal Settings Menu opens:

```
Personal Settings Menu
```

2.  Choose _Settings_ from the drop down menu:

**Note:** If you are an administrator, you can also manage users and administer the server. These links do not appear to  
a non-administrator user.

The options listed in the Personal Settings Page depend on the applications that are enabled by the administrator. Some  
of the features you will see include the following:

-   Usage and available quota
-   Manage your profile picture
-   Full name (You can make this anything you want, as it is separate from your Nextcloud login name, which is  
    unique and cannot be changed)
-   Email address
-   List of your Group memberships
-   Change your password

#### 125

-   _Using two-factor authentication_
-   _Setting your preferences_
-   Choose the language for your Nextcloud interface
-   Links to desktop and mobile apps
-   Manage your Activity stream and notifications
-   Default folder to save new documents to
-   Your Federated sharing ID
-   Social sharing links
-   Nextcloud version

**Note:** Available options and settings depending on your administrators configuration. If you are not able to change  
the password or the display-name in your personal settings, please contact your administrator for help.

**126 Chapter 7. Setting your preferences**

#### CHAPTER

### EIGHT

### UNIVERSAL ACCESS

Universal access is very important to us. We follow web standards and check to make everything usable also with  
keyboard and assistive software such as screen readers. We aim to be compliant with the Web Content Accessibility  
Guidelines 2.1 on AA level, with the high contrast theme even on AAA level. We also follow the German BITV 2.0  
guidelines.

If you find any issues, don’t hesitate to report them on our issue tracker. And if you want to get involved, come join our  
design team!

### 8.1 Zoom and responsiveness

The Nextcloud interface is fully responsive and usable on any size of screen. You can zoom in and out to fit the text  
and element size to your liking. The navigation and sidebar can be expanded or collapsed.

### 8.2 Navigating via keyboard

You can navigate the web interface with keyboard only just like you can with the mouse:

-   TabandShift + Tabto move between elements
-   EnterorSpaceto activate or open the element (depending on the type of element)
-   Escapeto be used to close modals, popover menus, and file viewers
-   Left arrowandRight arrowto navigate between photos in the viewer
-   Ctrl + Fto focus the search field
-   Ctrl + Sto save changes in editors like Nextcloud Text

For quicker navigation, we offer 2 “skip links” at the beginning of the document which allow you to:

-   Skip to main content
-   Skip to navigation of app

Nextcloud Talk has shortcuts which are also documented inside the settings of the app itself:

-   Cto focus the message input field
-   Escapeto unfocus the message input field to be able to use shortcuts
-   Fto fullscreen the chat or call
-   **While in a call:**  
    **\-** Mto toggle the microphone on and off

#### 127

**\-** Vto toggle video on and off  
**\-** Spacefor push to talk or push to mute  
**\-** Rto raise or lower hand

Nextcloud Mail has shortcuts as well, also documented inside the settings of the app itself:

-   Cto compose a new message
-   Left arrowto switch to a newer message
-   Right arrowto switch to an older message
-   Sto toggle a message as favorite
-   Uto toggle a message unread
-   Delto delete a message
-   Ctrl + Enterto send
-   Rto refresh and load new mails

### 8.3 Included themes

We offer several themes you can activate to aid accessibility:

-   **High contrast theme:** A high contrast mode to ease your navigation. Visual quality will be reduced but clarity  
    will be increased.
-   **Dark theme:** A dark theme to ease your eyes by reducing the overall luminosity and brightness. It is still under  
    development, so please report any issues you may find.
-   **Dyslexia font:** OpenDyslexic is a free typeface/font designed to mitigate some of the common reading errors  
    caused by dyslexia.

To reach the accessibility settings:

1.  Open the settings menu at the end of the header
2.  Pick **Settings**
3.  In the navigation, pick **Accessibility**

**Note:** Contrast of elements can vary based on custom theming. For example, the primary theming color is used as  
background color by the header, log in page, and primary buttons. If this causes contrast issues, please contact your  
administrator for help.

**128 Chapter 8. Universal access**

#### CHAPTER

### NINE

### USING TWO-FACTOR AUTHENTICATION

Two-factor authentication (2FA) is a way to protect your Nextcloud account against unauthorized access. It works by  
requiring two different ‘proofs’ of your identity. For example, _something you know_ (like a password) and _something  
you have_ like a physical key. Typically, the first factor is a password like you already have and the second can be a text  
message you receive or a code you generate on your phone or another device ( _something you have_ ). Nextcloud supports  
a variety of 2nd factors and more can be added.

Once a two-factor authentication app has been enabled by your administrator you can enable and configure it in _Setting  
your preferences_. Below you can see how.

### 9.1 Configuring two-factor authentication

In your Personal Settings look up the Second-factor Auth setting. In this example this is TOTP, a Google Authenticator  
compatible time-based code:

You will see your secret and a QR code which can be scanned by the TOTP app on your phone (or another device).  
Depending on the app or tool, type in the code or scan the QR and your device will show a login code which changes  
every 30 seconds.

### 9.2 Recovery codes in case you lost your 2nd factor

You should always generate backup codes for 2FA. If your 2nd factor device gets stolen or is not working, you will be  
able to use one of these codes to unlock your account. It effectively functions as a backup 2nd factor. To get the backup  
codes, go to your Personal Settings and look under Second-factor Auth settings. Choose _Generate backup codes_ :

You will then be presented with a list of one-time-use backup codes:

You should put these codes in a safe spot, somewhere you can find them. Don’t put them together with your 2nd factor  
like your mobile phone but make sure that if you lose one, you still have the other. Keeping them at home is probably  
the best thing to do.

#### 129

**130 Chapter 9. Using two-factor authentication**

**9.2. Recovery codes in case you lost your 2nd factor 131**

### 9.3 Logging in with two-factor authentication

After you have logged out and need to log in again, you will see a request to enter the TOTP code in your browser. If you  
enable not only the TOTP factor but another one, you will see a selection screen on which you can choose two-factor  
method for this login. Select TOTP:

Now, just enter your code:

If the code was correct you will be redirected to your Nextcloud account.

**Note:** Since the code is time-based, it’s important that your server’s and your smartphone’s clock are almost in sync.  
A time drift of a few seconds won’t be a problem.

### 9.4 Using two-factor authentication with hardware tokens

You can use two-factor authentication based on hardware tokens. The following devices are known to work:

-   TOTP based:  
    **\-** Nitrokey Pro  
    **\-** Nitrokey Storage
-   FIDO U2F based:  
    **\-** Nitrokey FIDO U2F

**132 Chapter 9. Using two-factor authentication**

### 9.5 Using client applications with two-factor authentication

Once you have enabled 2FA, your clients will no longer be able to connect with just your password unless they also  
have support for two-factor authentication. To solve this, you should generate device specific passwords for them. See  
_Manage connected browsers and devices_ for more information on how to do this.

### 9.6 Considerations

If you use WebAuthn to login to your Nextcloud be sure to not use the same token for 2FA. As this would mean you  
are again only using a single factor.

**9.5. Using client applications with two-factor authentication 133**

**134 Chapter 9. Using two-factor authentication**

#### CHAPTER

### TEN

### MANAGE CONNECTED BROWSERS AND DEVICES

The personal settings page allows you to have an overview on the connected browsers and devices.

### 10.1 Managing connected browsers

In the list of connected browsers you see which browsers connected to your account recently:

You can use the trash icon to disconnect any of the browsers in the list.

#### 135

### 10.2 Managing devices

In the list of connected devices you see all the devices and clients you generated a device password for and their last  
activity:

You can use the trash icon to disconnect any of the devices in the list.

At the bottom of the list you find a button to create a new device-specific password. You can choose a name to identify  
the token later. The generated password is used for configuring the new client. Ideally, generate individual tokens for  
every device you connect to your account, so you can disconnect those individually if necessary:

**Note:** You have only access to the device password when creating it, Nextcloud will not save the plain password,  
hence it’s recommended to enter the password on the new client immediately.

**Note:** If you are _Using two-factor authentication_ for your account, device-specific passwords are the only way to  
configure clients. The server will deny connections of clients using your login password then.

**136 Chapter 10. Manage connected browsers and devices**

**10.2. Managing devices 137**

### 10.3 Device-specific passwords and password changes

For password changes in external user backends the device-specific passwords are marked as invalid and once a login  
of the user account with the main password happens all device-specific passwords are updated and work again.

**138 Chapter 10. Manage connected browsers and devices**

#### CHAPTER

### ELEVEN

### EXTERNAL STORAGE

### 11.1 Configuring external Storage

The External Storage application allows you to mount external storage services, such as Amazon S3, SMB/CIFS file-  
servers and FTP servers... in Nextcloud. Your Nextcloud server administrator controls which of these are available to  
you. Please see Configuring External Storage (GUI) in the Nextcloud Administrator’s manual for configuration howtos  
and examples.