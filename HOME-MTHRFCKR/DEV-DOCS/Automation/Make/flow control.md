-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Tools](https://www.make.com/en/help/tools.html)
-   Flow control

## Repeater

**Repeater** is used in cases where you wish to repeat a task a given number of times. Let us assume you would like to send five emails with subjects "Hello 1", "Hello 2", ... "Hello 5". This could be accomplished with connecting **Email > Send me an email** module after the **Repeater** module:

With modules configured as follows:

You can imagine the Repeater module as a generator of bundles outputting one bundle after another. Each bundle contains one item named `i` of type Number. The initial value of the `i` item is specified in the Initial value field. The number of repetitions (= number of outputted bundles) is specified in the Repeats field. The value of the `i` item is increased in each repetition by the value specified in the Step field, which is 1 by default (tick the Show advanced settings checkbox to reveal it).

## Iterator

Iterator is a special type of module that converts an array into a series of bundles. Each array item will output as a separate bundle.

### Setting up an iterator

Setting up an iterator is done in the same way as [setting any other module](https://www.make.com/en/help/modules/module-settings.html "Module settings"). The Array field contains the array to be converted/split into separate bundles.

#### Examples:

##### Save email attachments to Google Drive

The scenario below shows how to retrieve emails with attachments and save the attachments as single files in a selected [Google Drive](https://www.make.com/en/help/apps/file-and-document-management/google-drive.html "Google Drive") folder.

Emails can contain an array of attachments. The **Iterator** module inserted after the first module enables you to handle each attachment separately. The **Iterator** splits the array of attachments into single bundles, each bundle with one attachment will then save one at a time in a selected Google Drive folder. The **Iterator** module set up is shown above - the Array field should contain the `Attachments[]` array.

##### Specialized iterators

For your convenience, many Make apps offer specialized iterator modules with a simplified setup. For example, the **[Email](https://www.make.com/en/help/apps/communication/email--legacy-.html "Email (legacy)")** app contains the special iterator **Email > Iterate attachments** that will produce the same results as the general **Iterator** without having to specify the array, just the source module.

### Learn when to use an Iterator in your scenarios

The video below is module 1 of the 3 part lesson titled **Iterator and Array Aggregator**. It explains the purpose of the Iterator and the Array Aggregator and with the help of a sample scenario, explains when to use an Iterator and what to do with the output.

#### Troubleshooting: Mapping panel does not display mappable items under the Iterator module

When an **Iterator** does not have information about the structure of the array's items, the mapping panel in the modules following the **Iterator** will display only two items under the **Iterator**: `Total number of bundles` and `Bundle order position`:

The reason for this is that in Make each module is responsible for providing information about items it outputs so these items can be properly displayed in the mapping panel in the following modules. However, there are several modules that might be unable to provide this information in some cases, e.g. **[JSON](https://www.make.com/en/help/tools/json.html "JSON") > Parse JSON** or **[[[Webhooks]]](https://www.make.com/en/help/tools/webhooks.html "[[Webhooks|[[Webhoo]]ks|[[Webhoo]]ks|[[Webhoo]]ks]]") > Custom Webhook** modules with missing [data structure](https://www.make.com/en/help/tools/data-structures.html "Data structures").

The solution is to manually execute the scenario to make the module learn about the items it outputs so it can provide the information to the following modules.

For example, if you have a **JSON > Parse JSON** module without a data structure as below:

And then if you connect an **Iterator** module to it, you will not be able to map the output of the module to the _Array_ field in the setup panel of the **Iterator**:

To resolve this, just manually start the scenario in the Scenario editor. You can un-link the modules after the **JSON > Parse JSON** module to prevent the flow from proceeding further or right-click the **JSON > Parse JSON** module and choose "Run this module only" from the context menu to execute only the **JSON > Parse JSON** module.

Once the **JSON > Parse JSON** has been executed, it learns about the items it outputs and provides this information to all the following modules including the **Iterator**. The mapping panel in the **Iterator's** setup will then display the items:

Moreover, the mapping panel in the modules connected after the **Iterator** will display the items contained in the array's items:

**In summary:** if you cannot see some items in a module's mapping panel, simply run the scenario once so all the modules can learn about the items they output and provide this information to the following modules.

## Array aggregator

_Array aggregator_ is an aggregator module, which allows to merge several bundles into one single bundle. The following image shows a typical setup of the **Array aggregator** module.

<table><tbody><tr><td><p><span><strong>Source Module</strong></span></p></td><td><p>The module from which the bundle aggregation will start. The source module is usually an <a href="https://www.make.com/en/help/tools/flow-control.html#iterator-935250" title="Iterator">iterator</a> or a <a href="https://www.make.com/en/help/modules/types-of-modules.html#searches-935210" title="Searches">search</a> module that outputs a series of bundles. Once you setup the aggregator's <span><strong>Source Module</strong></span> (and close the aggregator's setup), the route between the source module and the aggregator will be wrapped in a grey area to visualize the start and the end of the aggregation.</p></td></tr><tr><td><p><span><strong>Target structure type</strong></span></p></td><td><p>The target structure into which the data shall be aggregated. The default option is Custom that enables you to choose items that should be aggregated into the Array aggregator's output bundle's <code>Array</code> item:</p><p>Once you connect more modules after the <span><strong>Array aggregator</strong></span> module and get back to the module's setup, the <span><strong>Target structure type</strong></span> dropdown will contain all the following modules and their fields that are of type Array of Collections, like e.g. <span><strong>Attachments</strong></span> field of the <span><strong>Slack &gt; Create a Message</strong></span> module:</p><p>The video below explains how the modules connected after an <span><strong>Array aggregator</strong></span> affects the content of Target structure type dropdown:</p></td></tr><tr><td><p><span><strong>Group by</strong></span></p></td><td><p>The aggregator's output can be split into several groups with the help of the<span><strong> Group by field</strong></span>. The <span><strong>Group by field</strong></span> can contain a formula that is evaluated for each aggregator's input bundle. The aggregator then outputs one bundle per each distinct formula's value. Each bundle contains two items:</p><div><ul><li><p><code>Key</code> contains the distinct value.</p></li><li><p><code>Array</code> contains the aggregated data from the bundles for which the formula evaluated to the <code>Key</code> value.</p></li></ul></div></td></tr><tr><td><p><span><strong>Stop processing after an empty aggregation</strong></span></p></td><td><p>By default, the aggregator outputs the result of the aggregation even in case no bundles reached the aggregator (e.g. because they have been all filtered out on their way). If the <span><strong>Stop processing after an empty aggregation</strong></span> option is enabled, the aggregator will not produce any output bundle in this case and the flow will stop.</p></td></tr></tbody></table>

### Caution

Bundles outputted from the source module and any other modules between the source module and the aggregator module are not outputted by the aggregator and thus items in these bundles are not accessible by the modules in the flow after the aggregator.

If you need to access items from bundles outputted from the source module and any other modules between the source module and the aggregator module, make sure to include them in the **Aggregated fields** field in the setup of the **Array aggregator** module.

If items are nested (i.e. contained in a collection item) they currently cannot be easily selected in the **Array aggregator**'s **Aggregated fields** field. For example, if bundles contain collection item `User` with two items `Name` and `Email`:

Then only the `User` collection item can be selected:

This setup will produce the following output:

### Customizing the output

If you wish to fully customize the **Array aggregator**'s output structure, proceed as follows:

1.  Insert the **JSON > Create JSON** module after the **Array aggregator** module:
    
2.  Open the **JSON > Create JSON** module's setup.
    
3.  Setup a Data structure for the items you want to be outputted from the **Array aggregator**. The Data structure should be an array of collections and the collections should contain the items you want to include in the output. Here is a sample Data structure with two text items `Name` and `Email`:
    
4.  Open the **Array aggregator** module's setup.
    
5.  In the **Target structure type** field, choose the **JSON > Create JSON** module's array field:
    
6.  Fields corresponding to the Data structure created in step 3 will appear in the setup of the **Array aggregator** module. Map any items into the fields as you see fit. You can now easily map nested items using the mapping panel and even use formulas:
    
7.  The **Array aggregator** module's output will now look like this:
    

If you wish to save the operation performed by the dummy **JSON > Create JSON** module, just put it on a disabled route after a **Router**:

If you wish to conditionally omit an item from the module's output, use a formula that evaluates to `ignore` keyword:

If the `4. User: Email` is empty then the `Email` item will be completely omitted from the output:

### Learn when to use an Array Aggregator in your scenarios

The video below is module 2 of the 3 part lesson titled **Iterator and Array Aggregator**. It is a continuation of [module 1 (video link)](https://youtu.be/mWZBA2xSvB4) and using a sample scenario, explains when to use an Array aggregator and what to do with the output.