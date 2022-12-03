-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Modules](https://www.make.com/en/help/modules.html)
-   Iterator

Iterator is a special type of module that converts an array into a series of bundles. Each array item will output as a separate bundle.

## Setting up an iterator

Setting up an iterator is done in the same way as [setting any other module](https://www.make.com/en/help/modules/module-settings.html "Module settings"). The Array field contains the array to be converted/split into separate bundles.

### Examples:

#### Save email attachments to Google Drive

The scenario below shows how to retrieve emails with attachments and save the attachments as single files in a selected [Google Drive](https://www.make.com/en/help/apps/file-and-document-management/google-drive.html "Google Drive") folder.

Emails can contain an array of attachments. The **Iterator** module inserted after the first module enables you to handle each attachment separately. The **Iterator** splits the array of attachments into single bundles, each bundle with one attachment will then save one at a time in a selected Google Drive folder. The **Iterator** module set up is shown above - the Array field should contain the `Attachments[]` array.

#### Specialized iterators

For your convenience, many Make apps offer specialized iterator modules with a simplified setup. For example, the **[Email](https://www.make.com/en/help/apps/communication/email--legacy-.html "Email (legacy)")** app contains the special iterator **Email > Iterate attachments** that will produce the same results as the general **Iterator** without having to specify the array, just the source module.

## Learn when to use an Iterator in your scenarios

The video below is module 1 of the 3 part lesson titled **Iterator and Array Aggregator**. It explains the purpose of the Iterator and the Array Aggregator and with the help of a sample scenario, explains when to use an Iterator and what to do with the output.

### Troubleshooting: Mapping panel does not display mappable items under the Iterator module

When an **Iterator** does not have information about the structure of the array's items, the mapping panel in the modules following the **Iterator** will display only two items under the **Iterator**: `Total number of bundles` and `Bundle order position`:

The reason for this is that in Make each module is responsible for providing information about items it outputs so these items can be properly displayed in the mapping panel in the following modules. However, there are several modules that might be unable to provide this information in some cases, e.g. **[JSON](https://www.make.com/en/help/tools/json.html "JSON") > Parse JSON** or **[Webhooks](https://www.make.com/en/help/tools/webhooks.html "Webhooks") > Custom Webhook** modules with missing [data structure](https://www.make.com/en/help/tools/data-structures.html "Data structures").

The solution is to manually execute the scenario to make the module learn about the items it outputs so it can provide the information to the following modules.

For example, if you have a **JSON > Parse JSON** module without a data structure as below:

And then if you connect an **Iterator** module to it, you will not be able to map the output of the module to the _Array_ field in the setup panel of the **Iterator**:

To resolve this, just manually start the scenario in the Scenario editor. You can un-link the modules after the **JSON > Parse JSON** module to prevent the flow from proceeding further or right-click the **JSON > Parse JSON** module and choose "Run this module only" from the context menu to execute only the **JSON > Parse JSON** module.

Once the **JSON > Parse JSON** has been executed, it learns about the items it outputs and provides this information to all the following modules including the **Iterator**. The mapping panel in the **Iterator's** setup will then display the items:

Moreover, the mapping panel in the modules connected after the **Iterator** will display the items contained in the array's items:

**In summary:** if you cannot see some items in a module's mapping panel, simply run the scenario once so all the modules can learn about the items they output and provide this information to the following modules.