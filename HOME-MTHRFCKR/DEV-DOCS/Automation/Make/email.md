-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Tools](https://www.make.com/en/help/tools.html)
-   Email

The Email app allows you to download emails via IMAP, send emails via SMTP, create new drafts, move and copy emails from one folder to another folder, mark emails as read or unread, and delete emails.

## Prerequisites

-   An email account
    

### Caution

The module dialog fields that are displayed in **bold** (in the Make scenario, **not** in this documentation article) are mandatory!

## Connecting Email to Make

You can connect your Email account toMake using the following methods:

-   [Connecting using a Gmail account](https://www.make.com/en/help/tools/email.html#connecting-using-a-gmail-account "Connecting using a Gmail account")
    
-   [Connecting other email using IMAP](https://www.make.com/en/help/tools/email.html#connecting-other-email-using-imap "Connecting other email using IMAP")
    

### Connecting using a Gmail account

1.  Go to Make and open the **Email** module's **Create a connection** dialogue and select the Connection type as Google.
    
2.  In the **Connection name** field, enter a name for the connection and click **Save**.
    
3.  Confirm the access by clicking **Allow**.
    

The connection has been established.

### Connecting other email using IMAP

1.  Go to Make and open the **Email** module's **Create a connection** dialogue and select **Connection type as Others (IMAP)**.
    
2.  In the **Connection name** field, enter a name for the connection.
    
3.  In the **Email provider** field, do one of the following:
    
    1.  Select the email account.
        
        1.  **User name:** Enter your email address.
            
        2.  **Password:** Enter your password.
            
    2.  If your email account extension is not mentioned in the drop-down list, select **Other** and provide the following details:
        
        1.  **IMAP Server:** Enter incoming mail server address (IMAP). If you do not have this information available, contact your email service provider.
            
        2.  **Port:** Enter the port number.
            
        3.  **Use Secure Connection (TLS):** Select to establish a secure connection between the servers.
            
        4.  **Use explicit TLS:** Select to keep your connection encrypted.
            
        5.  **User name:** Enter your email address.
            
        6.  **Password:** Enter your password.
            
4.  Click **Continue**.
    

The connection has been established.

## Triggers

### Watch Emails

Triggers when a new email is received for processing according to specified criteria.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Folder</strong></span></p></td><td><p>Select the folder whose emails you want to watch.</p></td></tr><tr><td><p><span><strong>Criteria</strong></span></p></td><td><p>Select the criteria of the emails you want to watch:</p><div><ul><li><p><span><em>All Emails</em></span></p></li><li><p><span><em>Only Read Emails</em></span></p></li><li><p><span><em>Only Unread Emails</em></span></p></li></ul></div></td></tr><tr><td><p><span><strong>Sender Email Address</strong></span></p></td><td><p>Enter the email address of the sender whose emails you want to watch.</p></td></tr><tr><td><p><span><strong>Recipient Email Address</strong></span></p></td><td><p>Enter the email address of the recipient whose emails you want to watch.</p></td></tr><tr><td><p><span><strong>Subject</strong></span></p></td><td><p>Enter the subject of the email you want to watch.</p></td></tr><tr><td><p><span><strong>Phrase</strong></span></p></td><td><p>Enter any keywords to watch only those emails containing specific phrases.</p></td></tr><tr><td><p><span><strong>Mark message(s) as read when fetched</strong></span></p></td><td><p>Select the option if you want to mark the unread email as read after retrieving the details.</p></td></tr><tr><td><p><span><strong>Maximum number of results</strong></span></p></td><td><p>The maximum number of emails <span>Make</span> should return during one <span>scenario</span> execution cycle.</p></td></tr></tbody></table>

## Actions

### Copy an email

Copies an email or a draft into a selected folder.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Source Folder</strong></span></p></td><td><p>Select the folder from which you want to copy the email. For example, Inbox, Primary, Work, and so on.</p></td></tr><tr><td><p><span><strong>Destination Folder</strong></span></p></td><td><p>Select the folder to which you want to copy the email. For example, Inbox, Primary, Work, and so on.</p></td></tr><tr><td><p><span><strong>Email ID (UID)</strong></span></p></td><td><p>Enter the Email ID UID of the email you want to copy to the destination folder. You can get the UID of the email by using <span>Make</span>'s Watch Email module or Search Email module.</p></td></tr></tbody></table>

### Create a Draft

Copies an email or a draft into a selected folder.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Folder</strong></span></p></td><td><p>Select the folder in which you want to create the draft email.</p></td></tr><tr><td><p><span><strong>To</strong></span></p></td><td><p>Enter the email address to which you want to send the email.</p></td></tr><tr><td><p><span><strong>Subject</strong></span></p></td><td><p>Enter the subject line of the email.</p></td></tr><tr><td><p><span><strong>Content Type</strong></span></p></td><td><p>Select the content type for the email:</p><div><ul><li><p>HTML</p></li><li><p>Plain Text</p></li></ul></div></td></tr><tr><td><p><span><strong>HTML</strong></span></p></td><td><p>Enter the email content in HTML format using HTML tags or in the plain text as selected in the Content type field.</p></td></tr><tr><td><p><span><strong>Attachments</strong></span></p></td><td><p>Add an attachment:</p><p><span><strong>File name</strong></span></p><p>Enter the file name. For example, sample.doc.</p><p><span><strong>Data</strong></span></p><p>Enter the path to the folder to upload the attachment.</p><p><span><strong>Content-ID</strong></span></p><p>Enter the content ID to insert the attachment (image) in the content.</p></td></tr><tr><td><p><span><strong>Copy Recipient</strong></span></p></td><td><p>Enter the email address to whom you want to send a copy of this email.</p></td></tr><tr><td><p><span><strong>Blind Copy Recipient</strong></span></p></td><td><p>Enter the email address to whom you want to send a copy of this email without appearing their email addresses in the email.</p></td></tr><tr><td><p><span><strong>From</strong></span></p></td><td><p>Enter the email address that appears in the From field.</p></td></tr><tr><td><p><span><strong>Sender</strong></span></p></td><td><p>Enter the email address that appears in the Sender field.</p></td></tr><tr><td><p><span><strong>Reply-To</strong></span></p></td><td><p>Enter the details of the email for which you are sending this email as a reply.</p></td></tr><tr><td><p><span><strong>In-Reply-To</strong></span></p></td><td><p>Enter the details of the email for which you are drafting this email in reply to.</p></td></tr><tr><td><p><span><strong>References</strong></span></p></td><td><p>Enter the details of any reference you want to add to the email.</p></td></tr><tr><td><p><span><strong>Priority</strong></span></p></td><td><p>Select the priority:</p><div><ul><li><p><span><em>High</em></span></p></li><li><p><span><em>Low</em></span></p></li><li><p><span><em>Normal</em></span></p></li></ul></div></td></tr><tr><td><p><span><strong>Headers</strong></span></p></td><td><p>Add the headers:</p><p><span><strong>Key</strong></span></p><p>Add the key.</p><p><span><strong>Value</strong></span></p><p>Enter the value fo the key.</p></td></tr></tbody></table>

### Delete an Email

Removes an email or a draft from a selected folder.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Folder</strong></span></p></td><td><p>Select the folder of the email you want to delete. For example, Inbox, Primary, Work, and so on.</p></td></tr><tr><td><p><span><strong>Email ID (UID)</strong></span></p></td><td><p>Enter the <a href="https://www.make.com/en/help/tools/email.html#the-unique-email-id-in-imap-protocol-935249" title="The Unique Email ID in IMAP protocol">Email UID</a> of the email you want to delete. You can get the UID of the email by using <span>Make</span>'s Watch Email module or Search Email module.</p></td></tr><tr><td><p><span><strong>Expunge</strong></span></p></td><td><p>If selected, permanently removes all the messages marked as Deleted in the currently open mailbox. When you use Gmail then the behavior is driven by the setting in <span><em>Settings &gt; Forwarding POP/IMAP</em></span> in IMAP access section.</p></td></tr></tbody></table>

### Get Emails

Returns emails that match the specified criteria.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Folder</strong></span></p></td><td><p>Select the folder whose email details you want to retrieve. For example, Inbox, Primary, Work, and so on.</p></td></tr><tr><td><p><span><strong>Mark message(s) as read when fetched</strong></span></p></td><td><p>Select the option if you want to mark the unread email as read after retrieving the details.</p></td></tr><tr><td><p><span><strong>Criteria</strong></span></p></td><td><p>Select the emails you want to retrieve:</p><div><ul><li><p><span><em>All Emails</em></span></p></li><li><p><span><em>Only Read Emails</em></span></p></li><li><p><span><em>Only Unread Emails</em></span></p></li></ul></div></td></tr><tr><td><p><span><strong>Sender email address</strong></span></p></td><td><p>Enter the email address of the sender whose emails you want to retrieve.</p></td></tr><tr><td><p><span><strong>Recipient email address</strong></span></p></td><td><p>Enter the email address of the recipient whose emails you want to retrieve.</p></td></tr><tr><td><p><span><strong>From date</strong></span></p></td><td><p>Enter the date to retrieve the emails processed on or after the specified date.</p></td></tr><tr><td><p><span><strong>Before date</strong></span></p></td><td><p>Enter the date to retrieve the emails processed on or before the specified date.</p></td></tr><tr><td><p><span><strong>Subject</strong></span></p></td><td><p>Enter the subject of the email you want to retrieve.</p></td></tr><tr><td><p><span><strong>Phrase</strong></span></p></td><td><p>Enter any keywords to retrieve only those containing those phrases.</p></td></tr><tr><td><p><span><strong>Email ID (UID)</strong></span></p></td><td><p>Enter the <a href="https://www.make.com/en/help/tools/email.html#the-unique-email-id-in-imap-protocol-935249" title="The Unique Email ID in IMAP protocol">Email ID</a> (UID) of the email whose details you want to retrieve. You can get the UID of the email by using <span>Make</span>'s Watch Email module or Search Email module.</p></td></tr><tr><td><p><span><strong>Maximum number of results</strong></span></p></td><td><p>The maximum number of emails <span>Make</span> should return during one <span>scenario</span> execution cycle.</p></td></tr><tr><td><p><span><strong>Continue the execution of the route even if the module returns no results</strong></span></p></td><td><p>Select if you want to continue to run the module even if there are no results returned.</p></td></tr></tbody></table>

### Mark an Email as Read

Marks an email or a draft in a selected folder as read by setting the Read flag.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Folder</strong></span></p></td><td><p>Select the folder of the email you want to mark as read. For example, Inbox, Primary, Work, and so on.</p></td></tr><tr><td><p><span><strong>Email ID (UID)</strong></span></p></td><td><p>Enter the <a href="https://www.make.com/en/help/tools/email.html#the-unique-email-id-in-imap-protocol-935249" title="The Unique Email ID in IMAP protocol">Email UID</a> of the email you want to mark as read. You can get the UID of the email by using <span>Make</span>'s Watch Email module or Search Email module.</p></td></tr></tbody></table>

### Mark an Email as Unread

Marks an email or a draft in a selected folder as unread by setting the Unread flag.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Folder</strong></span></p></td><td><p>Select the folder of the email you want to mark as unread. For example, Inbox, Primary, Work, and so on.</p></td></tr><tr><td><p><span><strong>Email ID</strong></span></p></td><td><p>Enter the <a href="https://www.make.com/en/help/tools/email.html#the-unique-email-id-in-imap-protocol-935249" title="The Unique Email ID in IMAP protocol">Email UID</a> of the email you want to mark as unread. You can get the UID of the email by using <span>Make</span>'s Watch Email module or Search Email module.</p></td></tr></tbody></table>

### Move an Email

Moves a chosen email or a draft to a selected folder.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Source Folder</strong></span></p></td><td><p>Select the folder from which you want to move the email. For example, Inbox, Primary, Work, and so on.</p></td></tr><tr><td><p><span><strong>Destination Folder</strong></span></p></td><td><p>Select the folder to which you want to add the email. For example, Inbox, Primary, Work, and so on.</p></td></tr><tr><td><p><span><strong>Email ID (UID)</strong></span></p></td><td><p>Enter the <a href="https://www.make.com/en/help/tools/email.html#the-unique-email-id-in-imap-protocol-935249" title="The Unique Email ID in IMAP protocol">Email ID</a> UID of the email you want to move to the destination folder. You can get the UID of the email by using <span>Make</span>'s Watch Email module or Search Email module.</p></td></tr></tbody></table>

### Send an Email

Sends a new email.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Connection</strong></span></p></td><td><p><a href="https://www.make.com/en/help/tools/email.html#connecting-email-to-make-935249" title="Connecting Email to Make">Establish a connection to your Email account</a>.</p></td></tr><tr><td><p><span><strong>Save Message after Sending</strong></span></p></td><td><p>Select whether you want to save the email in your mail box after sending it.</p></td></tr><tr><td><p><span><strong>To</strong></span></p></td><td><p>Enter the email address to whom you want to send the email.</p></td></tr><tr><td><p><span><strong>Subject</strong></span></p></td><td><p>Enter the subject line of the email.</p></td></tr><tr><td><p><span><strong>Content Type</strong></span></p></td><td><p>Select the content type for the email:</p><div><ul><li><p><span><em>HTML</em></span></p></li><li><p><span><em>Plain Text</em></span></p></li></ul></div></td></tr><tr><td><p><span><strong>Content</strong></span></p></td><td><p>Enter the email content in HTML format using HTML tags or in the plain text as selected in the <span><em>Content Type</em></span> field.</p></td></tr><tr><td><p><span><strong>Attachments</strong></span></p></td><td><p>Add an attachment:</p><p><span><strong>File name</strong></span></p><p>Enter the file name. For example, sample.doc.</p><p><span><strong>Data</strong></span></p><p>Enter the path to the folder to upload the attachment.</p><p><span><strong>Content-ID</strong></span></p><p>Enter the content ID to insert the attachment (image) in the content.</p></td></tr><tr><td><p><span><strong>Copy Recipient</strong></span></p></td><td><p>Enter the email address to whom you want to send a copy of this email.</p></td></tr><tr><td><p><span><strong>Blind Copy Recipient</strong></span></p></td><td><p>Enter the email address to whom you want to send a copy of this email without having their email addresses appear in the email.</p></td></tr><tr><td><p><span><strong>From</strong></span></p></td><td><p>Enter the email address (and name, if needed) that appears in the <span><em>From</em></span> field in the email. Use the correct syntax: <code>name@email.com</code> or <code>"Name" name@email.com</code></p></td></tr><tr><td><p><span><strong>Sender</strong></span></p></td><td><p>Enter the email address that appears in the <span><em>Sender</em></span> field in the email.</p><p>1. Open the <span><em>Send an email</em></span> action advanced settings using the checkbox</p><div id="UUID-46e0cf8d-30ce-2858-9298-099258a18ddf_mediaobject-idm4579545536704032900424400913"><p><img src="https://www.make.com/en/help/image/1621f615db9303.png" alt="Show_advanced_settings.png"></p></div><p>2. Enter the required sender name or email</p><p>Use the correct syntax as shown in the hint on the screenshot below. <code>name@email.com</code> or <code>"Name" name@email.com</code></p><div id="UUID-46e0cf8d-30ce-2858-9298-099258a18ddf_mediaobject-idm4581976602998432915836011514"><p><img src="https://www.make.com/en/help/image/1621f615dbcebb.png" alt="emailSendEmail.png"></p></div></td></tr><tr><td><p><span><strong>Reply-To</strong></span></p></td><td><p>Enter the details of the email for which you are sending this email as a reply.</p></td></tr><tr><td><p><span><strong>In-Reply-To</strong></span></p></td><td><p>Enter the details of the email for which you are drafting this email in reply to.</p></td></tr><tr><td><p><span><strong>References</strong></span></p></td><td><p>Enter the details of any reference you want to add to the email.</p></td></tr><tr><td><p><span><strong>Priority</strong></span></p></td><td><p>Select the priority of the email:</p><div><ul><li><p><span><em>High</em></span></p></li><li><p><span><em>Low</em></span></p></li><li><p><span><em>Normal</em></span></p></li></ul></div></td></tr><tr><td><p><span><strong>Headers</strong></span></p></td><td><p>Add the headers:</p><p><span><strong>Key</strong></span></p><p>Add the key. For example, Sender, Date, To, and so on.</p><p><span><strong>Value</strong></span></p><p>Enter the value for the key.</p></td></tr></tbody></table>

### The Unique Email ID in IMAP protocol

The Unique Email ID known as 'Email ID (UID)' is the email's identifier. The Email ID is specific for each of the email's folders.

### Tip

For getting and deleting the same email from the same folder, you can see below:

Getting an email from your **Inbox**

Deleting the email from your **Inbox**

## Iterators

### Iterate Attachments

Iterates received attachments one by one.

The email iterator module lets you manage email attachments separately. For example, you can set up to watch emails to iterate the emails with attachments and receive alerts.

For more information about iterators, see [Iterator](https://www.make.com/en/help/tools/flow-control.html#iterator-935250 "Iterator").