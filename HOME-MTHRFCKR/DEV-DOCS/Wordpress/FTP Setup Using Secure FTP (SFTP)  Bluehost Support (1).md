# FTP Setup Using Secure FTP (SFTP)

## Overview

**Secure FTP (SFTP)** is available with your Bluehost hosting account and is recommended for use when uploading content. It is more secure than regular FTP, as data is encrypted while being transmitted over the internet.   
To use it on a shared hosting account, you will first need to [enable SSH Access](http://www.Bluehost.com/help/article/ssh-access) for your account. On a VPS or Dedicated server, SFTP is enabled by default.

**Note:** Additional FTP users created through the control panel are **not** able to connect using SFTP. On shared, SFTP is available for use only by the account username. On VPS and Dedicated servers, any cPanel account username or the **root** user can connect through SFTP. 

___

-   [Using SFTP](https://www.bluehost.com/help/article/sftp#sftp)
-   [Changing an existing connection in FileZilla](https://www.bluehost.com/help/article/sftp#connection)
-   [Setting up a new SFTP connection](https://www.bluehost.com/help/article/sftp#setup)
-   [Additional Tips](https://www.bluehost.com/help/article/sftp#tips)

___

## Using SFTP

Our servers do support Secure FTP or SFTP. There are a couple of things that you will need to do to use this option on our servers.

1.  Download an FTP program that supports Secure FTP. Most popular programs should do so.
    
2.  (For Shared only) You will need to enable SSH/Shell access to your account. If you do not already have SSH/Shell access, [click here](http://www.Bluehost.com/help/article/ssh-access) for further information.
    
3.  Configure your FTP program to use SFTP on port 22 (For VPS/Dedicated: if the ssh port has been changed from the default of 22, the SFTP port also changes inline.)
    

## Changing an existing connection in FileZilla

If you have an existing FTP connection, changing it to use SFTP is very simple. In the Site Manager for the connection, change the protocol from FTP to SFTP, as shown below:  
![SFTP-settings](https://content.bluehost.com/bluehost/img/third-party/tools/SFTP-settings.png)  
When you do so, the **Encryption** option will be disabled. There is no need to provide a port unless you are on a VPS/Dedicated server and have changed the ssh port (see image above). Otherwise, the field should be left blank.

## Setting up a new SFTP connection

If you are setting up a new connection, enter the following settings. The ones below are intended for use with FileZilla, but most FTP clients will have similar options.

-   **Host:** Your domain name or server IP address.
-   **Port:** Leave blank (For VPS/Dedicated only: or provide your custom ssh port)
-   **Protocol:** SFTP - SSH File Transfer Protocol
-   **Encryption:** N/A
-   **Logon Type:** Normal or Ask for Password
-   **User:** Your cPanel username (or root on a VPS/Dedicated server)
-   **Password:** As appropriate for the user

## Additional Tips

-   If using SFTP and connecting to an IP address, you will typically receive a warning about the **_secure certificate not matching_**. This certificate can be accepted, though it’s generally best to use a domain name that is covered by an SSL.
    
-   After connection and login, there should be no difference between an SFTP session and an FTP one. Files are uploaded and downloaded in the same way.
    
-   (For VPS/Dedicated only) When connecting as the **root** user, you will be in the /root folder. You can go up one level from there to see all files and folders on the server. Please be very careful if making any changes this way, as it is very easy to break a server.
    

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.