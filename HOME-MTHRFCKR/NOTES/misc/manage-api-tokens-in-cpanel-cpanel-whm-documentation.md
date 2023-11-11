---
tags:: notes
created: 2022-07-08T18:01:55 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/security/manage-api-tokens-in-cpanel/
author: 
---

# Manage API Tokens in cPanel | cPanel & WHM Documentation

> ## Excerpt
> This feature lets you create, list, update, and revoke API tokens.

---
1.  [cPanel & WHM Documentation](https://docs.cpanel.net/)
2.  [cPanel](https://docs.cpanel.net/cpanel/)
3.  [Security](https://docs.cpanel.net/cpanel/security/)
4.  Manage API Tokens in cPanel

*Valid for versions 82 through the latest version*

## Version

## [82](https://docs.cpanel.net/cpanel/security/manage-api-tokens-in-cpanel/)

___

Last modified: *September 20, 2021*

# Overview

Important:

-   This functionality is **experimental**. It may change in future versions.
-   The *Unrestricted* application programming interface (API) tokens can access API functions that do **not** have an associated feature.

This feature lets you create, list, update, and revoke API tokens. The server recognizes API tokens and allows you to run API functions. API functions allow you to view and change account data without the need to log in to the cPanel interface. You can issue API tokens to allow others to run API functions with your account’s data. For example, you could issue an API token to a reseller. The reseller could use that token to check disk usage.

Note:

-   API tokens run [UAPI](https://api.docs.cpanel.net/cpanel/introduction/) functions and [cPanel API 2](https://documentation.cpanel.net/display/DD/Guide+to+cPanel+API+2) functions, not [cPanel API 1](https://documentation.cpanel.net/display/DD/Guide+to+cPanel+API+1) functions.
-   Use API tokens to run API functions from the command line. For more information, read our [How to Use cPanel API Tokens](https://docs.cpanel.net/knowledge-base/security/how-to-use-cpanel-api-tokens) documentation.
-   For more information about using API functions, read our [Quickstart Development Guide](https://api.docs.cpanel.net/guides/quickstart-development-guide/) documentation.

# Create an API Token

To create an API token, perform the following steps:

1.  Click *Create*. The *Create API Token* interface will appear.
2.  Enter a unique name in the *API Token Name* text box.
    

    Note:

    
    -   An API token name can **only** contain up to 50 characters.
    -   You can **only** enter letters (`a` - `z` and `A` - `Z`), numbers (`0` - `9`), dashes ( `-` ), and underscores ( `_` ).  

3.  Select one of the following options from the *Should the API Token Expire?* section:
    -   *The API Token will not expire.* — This will create a token that does **not** have an expiration date.
    -   *Specify an expiration date.* — This allows you to create a token that expires on a specific date. By default, tokens expire one year from the current date. When you select this option, the interface displays the *API Token Expiration Date* section. Use the the calendar icon (![Calendar](https://docs.cpanel.net/img/calendar.png)) to open a calendar to select a desired expiration date. You can also enter a custom date in the calendar text box, in `YYYY-MM-DD` format. The token will expire on the date you select at `23:59:59`, server time.
        

        Important:

        
        -   You **cannot** edit an API token expiration date after creation.
        -   When an API token expires, the system will **not** remove it. You **must** [manually delete](https://docs.cpanel.net/cpanel/security/manage-api-tokens-in-cpanel/#revoke-the-token) an API token.  

4.  Click *Create*. A new interface will appear.
    -   To copy the API token, click *Copy*. Think of this token like a password. You must enter this token each time that you use it.
        

        Warning:

        

        You **cannot** access the token after you navigate away from the interface. If you forget or misplace this token, you **must** revoke the token and then create a new one.

        
5.  Click *Yes, I Saved My Token*.
    -   To create a new token, select the *Create another token after I click Yes, I saved my token* checkbox.
    -   To return to the *List API Tokens* interface, deselect the *Create another token after I click Yes, I saved my token* checkbox.

# The API Tokens Table

This table displays all of your API tokens. You can perform the following functions:

-   To display more API tokens per page, click the gear icon (![Gear](https://docs.cpanel.net/img/gear.png)) and then select a number.
-   To revoke multiple tokens:
    1.  Select the checkboxes for each token to revoke. Select the checkbox at the top of the table to select **every** token.
    2.  Click *Revoke*. A confirmation message will appear.
    3.  Click *Revoke Selected API Tokens*.

The API tokens table contains the following information:

-   *Token Name* — The API token’s name.
-   *Created* — The date and time that you created the API token.
-   *Expires* — If an API token expires, the date and time on which the token will expire:
    -   When an API token will soon expire, the interface displays its entry row in yellow. It also displays a notice icon (![Notice](https://docs.cpanel.net/img/warn.png)).
    -   The interface displays expired API token entry rows in red. It also displays a notice icon (![Notice](https://docs.cpanel.net/img/warn.png)).
        

        Remember:

        

        When API tokens expire, the system does **not** remove them. You **must** manually delete expired API tokens.

        
-   *Manage* — Click *Manage* to open a new interface where you can perform the following actions:
    -   *Rename Token* — Assign a new name for the token.
    -   *Revoke the Token* — Delete the token, and prevent it from accessing the server or any API functions.

# Manage an API Token

To manage an API token, locate the token in the API Tokens table and then click *Manage*. The *Manage API Token* interface will appear.

# Rename Token

To assign a new name for the token, enter a new name in the *New API Token Name* text box. Then click *Update*.

# Revoke the Token

Warning:

If you revoke an API token, users will **not** be able to run any scripts or API functions using that token.

To revoke an API token:

1.  Click *Revoke*. A confirmation message will appear.
2.  Click *Yes, Revoke the Token* to revoke the token.

Note:

To remove an API token on the command line, use the UAPI [`Tokens::revoke`](https://api.docs.cpanel.net/openapi/cpanel/operation/revoke/) function.

## Additional Documentation

___

-   [Guide to SSL](https://docs.cpanel.net/knowledge-base/security/guide-to-ssl/)
-   [Hotlink Protection](https://docs.cpanel.net/cpanel/security/hotlink-protection/)
-   [Manage API Tokens in WHM](https://docs.cpanel.net/whm/development/manage-api-tokens-in-whm/)
-   [The convert\_accesshash\_to\_token Script](https://docs.cpanel.net/whm/scripts/the-convert_accesshash_to_token-script/)
-   [Two-Factor Authentication for cPanel](https://docs.cpanel.net/cpanel/security/two-factor-authentication-for-cpanel/)
-   [The cPanel Glossary](https://docs.cpanel.net/knowledge-base/cpanel-product/cpanel-glossary/)

[![](https://docs.cpanel.net/img/cpanel-logo.min.svg "cPanel, L.L.C.")](https://cpanel.com/ "cPanel, L.L.C.")

cPanel, WebHost Manager and WHM are registered trademarks of cPanel, L.L.C. for providing its computer software that facilitates the management and configuration of internet web servers.
