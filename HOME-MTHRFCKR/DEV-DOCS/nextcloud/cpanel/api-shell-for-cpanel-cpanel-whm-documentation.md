---
created: 2022-08-05T11:30:13 (UTC -04:00)
tags: []
source: https://docs.cpanel.net/cpanel/advanced/api-shell-for-cpanel/
author: 
---

# API Shell for cPanel | cPanel & WHM Documentation

---
## API Shell for cPanel

_Valid for versions 82 through the latest version_

#### Version:

#### [82](https://docs.cpanel.net/cpanel/advanced/api-shell-for-cpanel/)

___

Last modified: _July 6, 2022_

## Overview

This interface allows you to run cPanel API functions interactively.

Important:

-   This interface is **only** available to reseller accounts.
-   Only [cPanel API 2](https://documentation.cpanel.net/display/DD/Guide+to+cPanel+API+2) and [UAPI](https://api.docs.cpanel.net/cpanel/introduction/) functions are available in the _API Shell_ interface.

Warning:

This feature uses **live** data from your server. API function calls may change or delete data on your server, which can cause your server to fail.

-   Read the documentation for a function **thoroughly** before you use it in the _API Shell_ interface.
-   To see an example of the function’s output, read the function’s _Response samples_ section in our [cPanel Developer Documentation](https://api.docs.cpanel.net/cpanel/introduction/).

### Enable the API Shell interface

To use this feature, your hosting provider must enable it for you. Ask them to perform the following steps in WHM:

1.  Select _On_ for the _cPanel & WHM API shell (for developers)_ setting in the _System_ tab of WHM’s [_Tweak Settings_](https://docs.cpanel.net/whm/server-configuration/tweak-settings#system) interface (_WHM >> Home >> Server Configuration >> Tweak Settings_).
2.  Grant the _API Shell_ feature to your account’s feature list in WHM’s [_Feature Manager_](https://docs.cpanel.net/whm/packages/feature-manager) interface (_WHM >> Home >> Packages >> Feature Manager_).

## Call an API function

To call an API function, perform the following steps:

1.  Select either the [_UAPI (API 3)_](https://api.docs.cpanel.net/cpanel/introduction/) or [_API 2_](https://documentation.cpanel.net/display/DD/Guide+to+cPanel+API+2) option in the _cPanel API version_ section.
2.  Select the API function from the selected API version’s menu.
3.  In the _Variables_ section, enter the API function’s keys and values in the text boxes. If the API function has any required key and value pairs, you **must** enter them.
    -   To add a new variable entry, click _Add_.
    -   To remove a variable entry, click the _X_ icon.
4.  To filter, sort, or paginate the results, click _Show Sort/Filter/Paginate Options_:
    -   To select the first record to show from the results, enter a number in the _Index of first results to show, zero-based_ text box or use the menu to select a number.
        -   A `0` value displays unlimited results.
    -   To limit the number of results to display, enter a number in the _Maximum # of results to show_ text box or use the menu to select a number.
        -   A `0` value displays unlimited results.
    -   To filter the results, click _Add_ in the _Filters_ section of the interface. You can specify the field to use to filter the results, the conditions (_Contains_, _Begins With_, _Equals_, _Greater Than (numeric)_, or _Less Than (numeric)_), and the term to apply to the conditions.
        -   To add a new filter, click _Add_.
        -   To remove a filter, click the _X_ icon.
    -   To sort the results, click _Add_ in the _Sorts_ section of the interface. You can specify a field by which you wish to sort the results, the conditions (_lexicographic_, _numeric_, _numeric\_zero\_as\_max_, or _ipv4_), and whether to reverse the sort order.
        -   To add a new sort method, click _Add_.
        -   To remove a sort order, click the _X_ icon.
    -   To limit the columns to display, click _Add_ in the _Columns_ section of the interface. Then, enter the column number in the _Column_ text box.
        -   To add more columns to display, click _Add_.
        -   To remove a column, click the _X_ icon.
5.  Click _Submit_.

As you modify the API function’s values, the interface updates the _URL_ and _API call data structure_ sections’ entries.

## API call response

After you click _Submit_, the API function’s returns appear in the _API call response_ section of the interface. You can view the results in the _Tree view_, _Table view_, and _Raw view_ tabs.

Note:

-   The _Raw view_ tab separates the API call’s response from the HTTP headers.
-   The _Table view_ may be unavailable for certain function data.
