-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Tools](https://www.make.com/en/help/tools.html)
-   JSON

## Getting started with JSON

The JSON app provides modules to process data in JSON format so that Make can further work with the data content, or create new JSON content.

## Parse JSON

### Data structure

The [Data structure](https://www.make.com/en/help/tools/data-structures.html "Data structures") describes how the JSON data is organized and enables the mapping of individual JSON items to other modules in your scenario. If you don't provide the Data structure, you may manually execute the module and Make will build the structure from the provided JSON:

1.  Fill the _JSON_ String field in the **Parse JSON** module.
    
2.  Do not yet connect other following modules. Because Makedoes not know the structure of the JSON data, it will not be possible to map data from the **Parse JSON** module to other modules in your scenario.
    
3.  Manually run the scenario. The **Parse JSON** module will identify the JSON structure from the JSON you have provided.
    
4.  You can now connect the following modules. The items from the **Parse JSON** module will be now available for mapping.
    

### Collection vs. Array

JSON string field can contain a collection

`{ ... }`

`{ "name" : "Peter", "ID" : 1}`

In which case, the output will be a single bundle containing the items of the collection:

Or it can contain an array

`[ ... ]`

`:`

`[ { "name" : "Peter", "ID" : 1 }, { "name" : "Mike", "ID" : 2 }]`

In which case the output will be a series of bundles, each bundle containing one array's item:

## Transforming data records to JSON

Let us assume that the data records you wish to transform to JSON format reside in a Google spreadsheet. Here is the procedure on how to transform the data records to JSON format described in ten steps:

-   \[1\] Place the **Google Sheets > Select rows** module in your scenario to fetch the data. Setup the module to retrieve rows from your Google spreadsheet and set the _Maximum number of returned rows_ to a small number, but larger than one for testing purposes (e.g. three). Execute the **Google Sheets** module (right-click it and choose "Run this module only") and verify the output of the module.
    
-   \[2\] Connect the **Array Aggregator** module after the **Google Sheets** module. In the module's setup choose the **Google Sheets** module in the _Source node_ field. Leave the other fields as they are for the moment.
    
-   \[3\] Connect **JSON > Create JSON** module after the **Array Aggregator** module. The module's setup requires a [Data structure](https://www.make.com/en/help/tools/data-structures.html "Data structures") that describes the JSON format. Click the Add button to open the Data structure setup. The easiest way to create this Data structure is to generate it automatically from a JSON sample. Click the Generator button and paste your JSON sample to the _Sample data_ field:
    
    `{ "books": [ { "id": "ID", "title": "Title", "author": "Author" } ]}`
    
-   \[4\] Click Save. The _Specification field_ in the Data structure setup should now contain the generated structure.
    
-   \[5\] Change the name of your Data structure to something more specific (e.g. "Books") and click Save. If everything goes well, a field corresponding to the root array attribute should appear as a mappable field in the **JSON** module's setup.
    
-   \[6\] Click the Map button next to the field and map the
    
    `Array[]`
    
    item outputted from the **Array aggregator** module to it:
    
-   \[7\] Click OK to close the **JSON** module's setup.
    
-   \[8\] Open the setup of the **Array Aggregator** module. Change the _Target structure_ from Custom to the **JSON** module's field corresponding to the root array attribute. Map items outputted from the **Google Sheets** module to the appropriate fields:
    
-   \[9\] Click OK to close the **Array Aggregator** module's setup.
    
-   \[10\] Run the scenario. If everything goes well, the **JSON** module should output the correct JSON format. Open the setup of the **Google Sheets** module and _increase the Maximum number of returned rows_ number to be larger than the number of rows in your spreadsheet to process all the data. The resulting JSON can be then used as a body of an HTTP request, returned as a Webhook's response, etc.
    

## Simulating module output using Parse JSON

Make allows you to mock the data from the existing module and perform testing for your scenario. You can execute this operation using the Parse JSON tool from the Apps section.

1.  Execute the module whose output data you want to mock using the Parse JSON.
    
2.  Click the resulting output above the module.
    
3.  Click **Download output bundles** from the dropdown menu.
    
    A window containing the original module's output bundles in JSON format pops up.
    
4.  Copy the window's content and click **Close**.
    
5.  Insert the **Tools > Parse JSON** module after the original module, open its configuration and paste the copied JSON data in step 4 into the **JSON string** field.
    
6.  Unlink the original module from the scenario.
    
    Do not delete the original module.
    
7.  Execute the mock-up JSON module and use its output in your scenario instead of the original module's output.
    
8.  Build and test your scenario.
    

Once you are done with the testing, change the mapping from the mock-up module to the original module across the whole scenario with the DevTool's **Remap Source tool**. See [MakeDevTool](https://www.make.com/en/help/scenarios/integromat-devtool.html "Make DevTool").

Put back the original module before the mock-up JSON module and remove the JSON module.

In the _Remap Source_ section, it is not necessary to fill the _Module to Edit_ field unless you do not want to remap all values from the original module in the whole scenario.

## Troubleshooting

Cannot map data from the Parse JSON module

Make sure that the JSON content is properly mapped into the Parse JSON module and that the data structure is correctly defined. See the above section, JSON processing for more details.