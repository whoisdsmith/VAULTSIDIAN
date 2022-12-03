# VPS & Dedicated Hosting: Managing Backups with SFTP

There are a few options to consider when downloading or deleting the server backups on a VPS or Dedicated Server. The first will be how-to manage it with SFTP. To do this, you'll need an FTP client. In this article, we will use Filezilla.

To get started, open Filezilla. To download Filezilla, please see [http://filezilla-project.org](https://filezilla-project.org/index.php).

1.  Go to **File** in the top left and select **Site Manager**.   
    ![User-added image](https://enduranceinternational.secure.force.com/kb/servlet/rtaImage?eid=ka01Q000000h3wn&feoid=00N3600000KNvmI&refid=0EM1Q000003SR1Y) 
2.  Now click **New Site**.  You'll need to enter the following information:
    -   **Host:** _Your Server IP_
    -   **Protocol:** SFTP
    -   **Logon Type:** Normal
    -   **Username:** root
    -   **Password:** _your root password   
        ![User-added image](https://enduranceinternational.secure.force.com/kb/servlet/rtaImage?eid=ka01Q000000h3wn&feoid=00N3600000KNvmI&refid=0EM1Q000003SR1x)_ 
3.  Once you have entered the information, click **Connect**. 
    
    **Note:** When you connect, you will likely be prompted to accept the host key.  Click **OK** and proceed.
    
4.  Once connected, you will be taken to /root (which is the root users directory; you can't do much in there); go up a directory.   
    ![User-added image](https://enduranceinternational.secure.force.com/kb/servlet/rtaImage?eid=ka01Q000000h3wn&feoid=00N3600000KNvmI&refid=0EM1Q000003SR27) 
5.  Now that you're at **/** you can navigate to the **backup** directory and then the **cpbackup** directory.
    -   If you are using Legacy Backup (the default backup manager), you'll want to go to /backup/cpbackup
    -   If you are using Backup Configuration, then you'll want to go to /backup   
        ![User-added image](https://enduranceinternational.secure.force.com/kb/servlet/rtaImage?eid=ka01Q000000h3wn&feoid=00N3600000KNvmI&refid=0EM1Q000003SR2M)
6.  In the **/backup/cpbackup** directory, you will find a daily, weekly, and monthly directory. Depending on which backups you have running, you'll want to go to the directory for them.  By default, daily and monthly backups are running.  So if you want to modify your daily backup, you'd go to the **daily** directory.   
    ![User-added image](https://enduranceinternational.secure.force.com/kb/servlet/rtaImage?eid=ka01Q000000h3wn&feoid=00N3600000KNvmI&refid=0EM1Q000003SR1t) 
7.  The file you want to get will be _username.tar.gz_,  username would be the account's Username. Once you're there, you can drag and drop the file to where you want to download it or delete it if that is your purpose.   
    ![User-added image](https://enduranceinternational.secure.force.com/kb/servlet/rtaImage?eid=ka01Q000000h3wn&feoid=00N3600000KNvmI&refid=0EM1Q000003SR2W)

It is strongly recommended that you download anything before you delete it. Deleting any of your files is a bad idea unless you know what it is, you have got a backup, or you are 100% sure it's not needed.

For further assistance, you may contact our [Chat Support](https://helpchat.bluehost.com/) or Phone Support via **888-401-4678**. You may also refer to our [Knowledge Base](https://www.bluehost.com/help) articles to help answer common questions and guide you through various setup, configuration, and troubleshooting steps.