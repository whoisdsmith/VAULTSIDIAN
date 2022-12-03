# Types of Modules 

Make distinguishes five types of modules: **Actions**, **Searches**, **Triggers**, **Aggregators** and **Iterators**. The two latter ones are intended for advanced scenarios.

## Actions

**Actions** are the most common module type.

-   A typical action module returns **just a single bundle** which is then passed on to the next module for processing.
    
-   Action modules can be placed **at the beginning, middle, or end of a scenario.**
    
-   Scenarios can contain **an unlimited number** of action modules.
    

### Examples:

1.  **[Dropbox](https://www.make.com/en/help/apps/file-and-document-management/dropbox.html "Dropbox") > Upload a file** sends a file to a selected Dropbox folder and returns its identifier.
    
2.  **[Image](https://www.make.com/en/help/tools/image.html "Image") > Resize** receives an image, resizes it to specified dimensions, and passes the resized image on to the next action.
    
3.  **[Google Analytics](https://www.make.com/en/help/apps/business-intelligence/google-analytics.html "Google Analytics") > Create a report** gets information about web traffic and passes it on for further processing.
    

### Update

The Action type has four sub-types: Create, Read, Update and Delete. The Update sub-type enables the following three operations:

1.  **Erase the content of a field.** This operation takes place when the content of the field is evaluated to `erase` keyword (not to be confused with _empty_):
    
2.  **Leave the content of a field unchanged.** This operation takes place when the field is left empty or the content of the field is evaluated to _empty_ (represented via _null_ in JSON):
    
3.  **Replace the content of a field.** This operation takes place in all other cases than those two described above.
    

### Note

If you do not see the `erase` keyword in the mapping panel than either the module is not an update module or it has not been updated to the latest apps specification yet.

The reason, why it has been decided that _empty_ will result in no change of the field content is that if there is a need to act differently and erase the field instead then it is easily achievable with the following formula:

whereas leaving the content of the field unchanged when the field's content is evaluated to _empty_ is currently not possible.

## Searches

-   A typical search module returns **zero, one, or more bundles** which are then passed on to the next module for processing.
    
-   Search modules can be placed **at the beginning, middle, or end of a scenario.**
    
-   Scenarios can contain **an unlimited number** of search modules.
    

### Examples:

-   **[Monday](https://www.make.com/en/help/apps/productivity/monday-v2.html "Monday v2") > List pulses in all boards** returns all account's pulses.
    

## Triggers

Trigger modules generate bundles when there has been a _change_ in a given service. The change can be a creation of a new record(s), deletion of a record(s), update of a record(s), etc. Make distinguishes between two types of triggers: **Polling triggers** and **Instant triggers**.

-   Every trigger can return **zero, one, or more bundles** which are then passed on to the next module for processing.
    
-   Triggers can be placed only **at the beginning of** a scenario.
    
-   Each scenario can contain **only one** trigger.
    

### Polling triggers

Polling triggers are designed to regularly poll a given service whether there has been a change since their previous run. So you will typically [schedule a scenario](https://www.make.com/en/help/scenarios/scheduling-a-scenario.html "Scheduling a scenario") containing a polling trigger module to run periodically by selecting for example At regular intervals option from the Schedule setting panel. If there is a change the trigger will return bundles containing information about the change. If there is no change the trigger will output no bundles.

Polling triggers allow you to select the first bundle they should output via the [epoch panel](https://www.make.com/en/help/modules/selecting-the-first-bundle.html "Selecting the first bundle"). The panel is displayed automatically after you save a trigger or when you make a substantial change in the trigger settings. You can also display the panel by right-clicking the module and choosing "Choose where to start" from the context menu.

### Note

Settings made in the epoch panel affect only the first execution of the module. Once the module is executed, it will remember the last outputted bundle and the settings made via epoch panel will be voided.

#### Examples:

-   **[Dropbox](https://www.make.com/en/help/apps/file-and-document-management/dropbox.html "Dropbox") > Watch files** returns files that were newly added since the last time the scenario was run.
    
-   **[Twitter](https://www.make.com/en/help/apps/marketing/twitter.html "Twitter") > Watch Tweets** returns new Tweets posted by the user since the last time the scenario was run.
    
-   **[Tumblr](https://www.make.com/en/help/apps/marketing/tumblr.html "Tumblr") > Watch posts** returns new posts added to a selected blog since the last time the scenario was run.
    

### Instant triggers

Instant triggers enable the service to notify Make about the _change_ immediately. You will typically wish to schedule a scenario containing an instant trigger to run immediately by selecting the _Immediately_ option from the [Schedule setting panel](https://www.make.com/en/help/scenarios/scheduling-a-scenario.html "Scheduling a scenario"). See also [Webhooks](https://www.make.com/en/help/tools/webhooks.html "Webhooks") for further details on how the incoming data are handled.

#### Examples:

-   **[Paypal](https://www.make.com/en/help/apps/commerce/paypal.html "PayPal") > New notification** returns new payment notifications.
    

## Aggregators

**[Aggregators](https://www.make.com/en/help/modules/aggregator.html "Aggregator")** are modules that accumulate multiple bundles into one single bundle.

-   Every aggregator returns **only one bundle** which is then passed on to the next module for further processing.
    
-   Aggregators can be placed only **in the middle** of a scenario.
    
-   Scenarios can contain **an unlimited number** of aggregators.
    

### Examples:

-   **[Archive](https://www.make.com/en/help/apps/built-in-apps/archive.html "Archive") > Create an archive** compresses received files into a zip archive.
    
-   **[CSV](https://www.make.com/en/help/apps/file-and-document-management/csv.html "CSV") > Aggregate to CSV** merges multiple strings from a CSV file into a single row.
    
-   **[Tools](https://www.make.com/en/help/tools/tools.html "Tools") > Text aggregator** combines several strings together into one single string.
    

## Iterators

**[Iterators](https://www.make.com/en/help/tools/flow-control.html#iterator-935250 "Iterator")** are modules that split arrays into multiple, separate bundles.

-   Every iterator returns **one or more bundles** which are then passed on to the next module for processing.
    
-   Iterators can be placed only in the middle of a scenario.
    
-   Scenarios can contain an unlimited number of iterators.
    

### Examples:

-   **[Email](https://www.make.com/en/help/apps/communication/email--legacy-.html "Email (legacy)") > Retrieve attachments** breaks an array of attachments into separate bundles.