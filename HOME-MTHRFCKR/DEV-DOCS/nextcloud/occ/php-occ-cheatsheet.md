# NextCloud Cheat Sheet #

## Get user account id ##

You can acquire this through the database, but it's also possible to utilize the account export command of occ if you know the UID of the user:

Example:

```
php occ mail:account:export pastpresident@mysite.com

Account 11:
- E-Mail: pastpresident@mysite.com
- Name: Past President
- IMAP user: pastpresident@mysite.com
- IMAP host: mysite.com:993, security: ssl
- SMTP user: pastpresident@mysite.com
- SMTP host: mysite.com:587, security: tls
```

## Force Email Sync ##

Run:

```
php occ mail:account:sync -f [ACCOUNT_ID]
```

## Create IAMP Mail Account ##

Run:

```
php occ mail:account:create usr@domain.com "The User" usr@domain.com mail.hostedemail.com 993 ssl usr@domain.com PASSWORD mail.hostedemail.com 587 starttls usr@domain.com PASSWORD

```