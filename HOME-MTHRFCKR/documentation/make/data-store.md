-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Tools](https://www.make.com/en/help/tools.html)
-   Data store

Data stores allow you to store data from scenario or transfer data between individual scenarios or scenario runs. You can use data stores to store data from apps during scenario execution. Data stores are similar to a simple database.

The data store app's modules allow you to add, replace, update, retrieve, delete, search, or count records in your Make data store.

You can view and manage your data stores and the data they contain in the data stores section of Make.

### Note

The various examples of use can be found [here](https://www.make.com/en/integrations/datastore).

## Getting started with data stores

Prerequisites

-   A data store created
    

In order to use the data store modules, it is necessary to create a data store in your Make account.

### Caution

The module dialog fields that are displayed in bold (in the Make scenario, not in this documentation article) are mandatory!

## Creating a data store in Make

1.  Click _Data stores_ in the left menu.
    
2.  Click _Add data store_.
    
3.  Enter settings for the new data store.
    

<table><tbody><tr><td><p><span><strong>Data store name</strong></span></p></td><td><p>Enter the name for the data store. E.g. <span><em>Contacts</em></span></p></td></tr><tr><td><p><span><strong>Data Structure</strong></span></p></td><td><p>A data structure, is a list of the columns for a table, that indicates the column name and data type.</p><p>You have three options:</p><div><ul><li><p><span><strong>Select the data structure that has been already created</strong></span></p></li><li><p><span><strong>Leave the field empty</strong></span></p><p>If you don't select a data structure, the database will only contain the primary key. Such a database type is useful if you only want to save keys and are only interested in knowing whether or not a specific key exists in the database.</p></li><li><p><span><strong>Add a new data structure</strong></span></p><p>Click the <span><em>Add</em></span> button to create a new data structure.</p></li></ul></div><p>Please see the <a href="https://www.make.com/en/help/tools/data-store.html#setting-up-the-data-structure" title="Setting up the data structure">Setting Up the Data Structure</a> section of this article.</p></td></tr><tr><td><p><span><strong>Data storage size in MB</strong></span></p></td><td><p>Allocate the size for the data store from your total <span><em>Internal data</em></span> storage.</p><div dir="ltr"><h3>Note</h3><p>The reserved amount can be changed at any time later on.</p></div><p>The total internal data storage capacity depends on the <a href="http://www.make.com/en/pricing" target="_blank" rel="noopener">plan you have purchased</a>.</p></td></tr></tbody></table>

## Setting up the data structure

To set up the data structure, open the _Add data structure_ dialog.

You can access this dialog by clicking the Add button when creating or editing the data store:

<table><tbody><tr><td><p><span><strong>Data structure name</strong></span></p></td><td><p>Enter the name for the data structure you are going to create.</p></td></tr><tr><td><p><span><strong>Specification</strong></span></p></td><td><p>There are two options for how you can specify the data store columns.</p><div><ul><li><p>Click the <span><em>Add item</em></span> button to specify the properties of one column manually.</p><p>Enter the <span><em>Name and Type</em></span> for the data store column and define corresponding properties.</p></li><li><p>Use the <span><em>Generator button</em></span> to determine the columns from the sample data you provide.</p><p>For example, the following JSON sample data:</p><pre>{

 <span>"name"</span>:<span>"John"</span>,

 <span>"age"</span>:<span>30</span>,

 <span>"phone number"</span>: {

 <span>"mobile"</span>:<span>"987654321"</span>,

 <span>"landline"</span>:<span>"123456789"</span>

 }

 }</pre><p>creates three columns (<span><em>name</em></span>, <span><em>age</em></span>, <span><em>phone number</em></span>) with phone number as a collection of <span><em>mobile</em></span> and <span><em>landline</em></span>.</p></li></ul></div><p>The empty columns in the data store view:</p><p>You can then add values to the data store manually or using the <span>Make</span> <span><em>data store</em></span> modules.</p></td></tr><tr><td><p><span><strong>Strict</strong></span></p></td><td><p>If enabled, the data structure will be compared to the structure of the payload and if the payload contains extra items not specified in the data structure, the payload will be rejected.</p></td></tr></tbody></table>

## Actions

Adds or replaces a record in the data store.

### Warning

The module throws an error when you try to add the record which is already in the data store under the same name and the _Overwrite an existing record_ option is disabled.

<table><tbody><tr><td><p><span><strong>Data store</strong></span></p></td><td><p>Select or <a href="https://www.make.com/en/help/tools/data-store.html#creating-a-data-store-in-make" title="Creating a data store in Make">add the data store</a> where you want to create a record.</p></td></tr><tr><td><p><span><strong>Key</strong></span></p></td><td><p>Enter the unique key. The key can be used later to retrieve the record. If you leave this field blank, the key will be generated.</p></td></tr><tr><td><p><span><strong>Overwrite an existing record</strong></span></p></td><td><p>Enable this option to overwrite the record. The record you want to overwrite must be specified in the <span><em>Key</em></span> field above.</p></td></tr><tr><td><p><span><strong>Record</strong></span></p></td><td><p>Enter the desired values to the record's fields.</p><div dir="ltr"><h3>Caution</h3><p>The maximum size of the record in data store is 15 MB!</p></div></td></tr></tbody></table>

Updates a record in the selected data store.

<table><tbody><tr><td><p><span><strong>Data store</strong></span></p></td><td><p>Select or <a href="https://www.make.com/en/help/tools/data-store.html#creating-a-data-store-in-make" title="Creating a data store in Make">add the data store</a> where you want to create a record.</p></td></tr><tr><td><p><span><strong>Key</strong></span></p></td><td><p>Enter the unique key of the record you want to update.</p></td></tr><tr><td><p><span><strong>Insert missing record</strong></span></p></td><td><p>Enable this option to create a new record if the record with the specified key doesn't already exist.</p></td></tr><tr><td><p><span><strong>Record</strong></span></p></td><td><p>Enter the desired values to the record's fields that you want to update.</p><div dir="ltr"><h3>Caution</h3><p>The maximum size of the record in data store is 15 MB!</p></div></td></tr></tbody></table>

Retrieves a record from the selected data store.

<table><tbody><tr><td><p><span><strong>Data store</strong></span></p></td><td><p>Select the data store you want to retrieve a record from.</p></td></tr><tr><td><p><span><strong>Key</strong></span></p></td><td><p>Enter the unique key of the record you want to retrieve.</p></td></tr></tbody></table>

Returns the value `true` if the record exists in the specified data store or `false` if the record doesn't exist in the data store.

<table><tbody><tr><td><p><span><strong>Data store</strong></span></p></td><td><p>Select the data store you want to check for the record existence.</p></td></tr><tr><td><p><span><strong>Key</strong></span></p></td><td><p>Enter the key of the record you want to check for existence</p></td></tr></tbody></table>

Deletes a specified record from the selected data store.

<table><tbody><tr><td><p><span><strong>Data store</strong></span></p></td><td><p>Select the data store you want to check for the record existence.</p></td></tr><tr><td><p><span><strong>Key</strong></span></p></td><td><p>Enter the <span><em>key</em></span> of the record you want to delete.</p></td></tr></tbody></table>

Deletes all records from the selected data store.

<table><tbody><tr><td><p><span><strong>Data store</strong></span></p></td><td><p>Select the data store you want to delete all records from.</p></td></tr></tbody></table>

Performs a search for records based on filter settings.

<table><tbody><tr><td><p><span><strong>Data store</strong></span></p></td><td><p>Select the data store you want to check for the record's existence.</p></td></tr><tr><td><p><span><strong>Filter</strong></span></p></td><td><p>Set the filter for the search.</p><p>Select the <span><em>column</em></span>, <span><em>operator</em></span> and required <span><em>value</em></span> (<span><em>search term</em></span>) for the search.</p></td></tr><tr><td><p><span><strong>Sort</strong></span></p></td><td><div><table><tbody><tr><td><p><span><strong>Key</strong></span></p></td><td><p>Select the column name you want to sort the results by.</p></td></tr><tr><td><p><span><strong>Order</strong></span></p></td><td><p>Select whether you want to sort results in the <span><em>ascending</em></span> or <span><em>descending</em></span> order.</p></td></tr></tbody></table></div></td></tr><tr><td><p><span><strong>Limit</strong></span></p></td><td><p>Set the maximum number of search results <span>Make</span> will return during one execution cycle.</p></td></tr><tr><td><p><span><strong>Continue the execution of the route even if the module returns no results</strong></span></p></td><td><p>If enabled, the <span>scenario</span> will not be stopped by this module.</p></td></tr></tbody></table>

Returns the number of records in the selected data store.

<table><tbody><tr><td><p><span><strong>Data store</strong></span></p></td><td><p>Select the data store whose records you want to count.</p></td></tr></tbody></table>

## Managing records in data stores

Make allows you to view, update, and delete the records in your data store.

To manage records in your data store, click _Data stores_ in the left menu, then click _Browse_ next to your data store.

This shows the editing interface for data store records.

Click _Add_ to add new records to the data store. You can add multiple records by clicking _Add multiple times_. Newly inserted records are highlighted in green.

Click an existing field to change it. Changed records are highlighted in yellow.

Click _Save_ to save all your changes to the data store. Click _Discard changes_ to throw away any changes you have made, including added records and edited records.

### Note

You cannot use _Discard changes_ to get back records that you have deleted.

To delete records from your data store, first select the records you want to delete by selecting the check boxes next to the records. Then, click the _Delete_ icon.

### Note

You cannot roll back deleted records.

## Troubleshooting

At the current moment of writing this, there is no tool which can automate this, making it difficult to obtain lost data. However, the long method of recovering data in your data store is to go through all execution logs of scenarios where items were inserted to the data store, then get data manually and insert them again.

The reason you are getting a message that states that you are out of space is because you currently have a datastore that has already been assigned your allocated datastore storage.

Please edit any of your existing data stores to free up space. 

1.  Click **Edit**.
    
2.  Reduce the data storage size.
    

You can now add a new data store.

### Caution

Make sure that while creating a new data store you do not assign all of your space to only one record unless you need it.