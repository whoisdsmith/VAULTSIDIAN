# How to Use SFTP to Connect to your WordPress Website

There are several reasons why you may want to connect directly to your website’s file system. Whether that is to upload large files, install themes, or customize plugins in a secure shell. Secure FTP is available with your Bluehost hosting account.

## Using SFTP

Our servers do support SFTP, which uses a layer of encryption for security and is restricted to a secured port. SFTP or Secure File Transfer Protocol (sometimes called SSH File Transfer Protocol) was designed as an extension of the SSH (Secure Shell) protocol. It is a secure channel using SSH.  
  
Before you can connect your WordPress site, here are a couple of things that you will need to do to use this option on our servers.

**Important Note**: Only your main FTP/cPanel username can be used for SFTP access. FTP accounts created using the FTP Accounts tool will not work. If you are having trouble finding this information, please [contact our support team.](https://www.bluehost.com/contact)

1.  You will need an SFTP client. Though there are several free and premium clients out there, we recommend the following:
    -   **Free:**
        -   [Filezilla](https://filezilla-project.org/) (MAC/PC)
        -   [Cyberduck](https://cyberduck.io/) (MAC/PC)
        -   [WinSCP](https://winscp.net/eng/download.php) (PC)
    -   **Premium:**
        -   [Transmit](https://panic.com/transmit/) (MAC)
        -   [FlashFXP](https://www.flashfxp.com/) (PC)
            
            **Note**: Common issues are caused when the client is not up to date. Please be sure to use the latest version.
            
2.  You will now need to enable SSH/Shell access to your account. Do this by:
    -   Log into your [Bluehost control panel](https://Bluehost.com/cgi-bin/cplogin).
    -   Select **My Sites** from the side navigation menu to the left.  
        ![rock-bh-my-sites-tab](https://content.bluehost.com/bluehost/img/bluehost/wordpress/rock-bh-my-sites-tab.png)
    -   Select the site you wish to access SSH for using the **Manage Site** link.  
        ![rock-mysites-wp-new](https://content.bluehost.com/bluehost/img/bluehost/wordpress/rock-mysites-wp-new.png)
    -   Select **Settings** from the side navigation menu to the left.
    -   At the bottom of this page, you will see the **Advanced** section; select the SSH Access **View** link. Here is a quick walkthrough below on how-to access SSH Management:  
        ![  ssh-access-gif](https://eig-cap-content-cdn-prod.s3.amazonaws.com/bluehost/img/bluehost/account/ssh-access-gif.gif  )
3.  Log into your SFTP program using the following:
    -   **Connection type** - SFTP
    -   **Hostname -** Your domain name or server IP address
    -   **Username -** Your cPanel username (or root on a VPS/Dedicated server)
    -   **Password -** As appropriate for the user
    -   **Port -** 22

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.