-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Modules](https://www.make.com/en/help/modules.html)
-   Aggregator

An **aggregator** is a [type of module](https://www.make.com/en/help/modules/types-of-modules.html "Types of modules") designed to merge several bundles of data into a single bundle.

When an aggregator is executed, it:

1.  accumulates all the bundles it receives (during a single source module's operation)
    
2.  outputs a single bundle with an array containing one item per each accumulated bundle. The content of the array's items depends on particular aggregator module and its setup.
    

A typical example of an aggregator module is the [Array aggregator](https://www.make.com/en/help/tools/flow-control.html#array-aggregator "Array aggregator") module. Aggregators usually feature the following fields:

<table><tbody><tr><td><p><span><strong>Source Module</strong></span></p></td><td><p>The module from which the bundle aggregation will start. The source module is usually an <a href="https://www.make.com/en/help/tools/flow-control.html#iterator-935250" title="Iterator">iterator</a> or a <a href="https://www.make.com/en/help/modules/types-of-modules.html#searches-935210" title="Searches">search</a> module that outputs a series of bundles. Once you setup the aggregator's Source Module (and close the aggregator's setup), the route between the source module and the aggregator will be wrapped in a grey area to visualize the start and the end of the aggregation.</p></td></tr><tr><td><p><span><strong>Group by</strong></span></p></td><td><p>The aggregator's output can be split into several groups with the help of the <span><em>Group by</em></span> field. The <span><em>Group by</em></span> field can contain a formula that is evaluated for each aggregator's input bundle. The aggregator then outputs one bundle per each distinct formula's value. Each bundle contains two items:</p><div><ul><li><p><code>Key</code> contains the distinct value.</p></li><li><p><code>Array</code> contains the aggregated data from the bundles for which the formula evaluated to the <code>Key</code> value.</p></li></ul></div></td></tr><tr><td><p><span><strong>Stop processing after an empty aggregation</strong></span></p></td><td><p>By default, the aggregator outputs the result of the aggregation even in case no bundles reached the aggregator (e.g. because they have been all filtered out on their way). If the <span><em>Stop processing after an empty aggregation</em></span> option is enabled, the aggregator will not produce any output bundle in this case and the flow will stop.</p></td></tr></tbody></table>

### Note

Bundles outputted from the source module and any other modules between the source module and the aggregator module are not outputted by the aggregator and thus items in these bundles are not accessible by the modules in the flow after the aggregator.

If you need to access items from bundles outputted from the source module and any other modules between the source module and the aggregator module, make sure to include them in the aggregator's setup, e.g. in the _Aggregated fields_ field in the setup of the **Array aggregator** module.

## Example

### Use case: Zipping all email attachments and uploading the ZIP file to Dropbox

The scenario below shows how to:

1.  Watch a mailbox for incoming emails: **[Email > Watch emails](https://www.make.com/en/help/tools/email.html#triggers-935249 "Triggers")** trigger will output a bundle with item `Attachments[]` , which is an array containing all the email's attachments.
    
2.  Iterate the email's attachments: **[Email > Iterate attachments](https://www.make.com/en/help/tools/email.html#iterators-935249 "Iterators")** iterator takes the items from the `Attachments[]` array one by one and sends them further as separate bundles.
    
3.  Aggregate the bundles outputted by the **[Email > Iterate attachments](https://www.make.com/en/help/tools/email.html#iterators-935249 "Iterators")** module: **[Archive > Create an archive](https://www.make.com/en/help/apps/built-in-apps/archive.html#create-an-archive-973677 "Create an archive")**aggregator accumulates all the bundles it receives and outputs a single bundle containing the ZIP file
    
4.  Upload the resulting ZIP file to Dropbox: **[Dropbox > Upload a file](https://www.make.com/en/help/apps/file-and-document-management/dropbox.html#upload-a-file-968222 "Upload a File")** obtains the ZIP file from the **[Archive > Create an archive](https://www.make.com/en/help/apps/built-in-apps/archive.html#create-an-archive-973677 "Create an archive")** module and uploads it to Dropbox.
    

Below is a sample setup of the **Archive > Create an archive** aggregator: