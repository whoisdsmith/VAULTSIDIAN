-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Tools](https://www.make.com/en/help/tools.html)
-   XML

## Getting started with XML

The **XML** app enables you to:

-   parse an XML formatted text via the **XML > Parse XML**module and convert it to a bundle to make the data available to other modules
    
-   convert a bundle to an XML formatted text via the **XML > Create XML** module
    

## Parsing XML

The **XML > Parse XML** module parses an XML formatted text and outputs a single bundle containing all the information extracted from the XML.

<table><tbody><tr><td><p><span><strong>Data structure</strong></span></p></td><td><p>The&nbsp;<a href="https://www.make.com/en/help/tools/data-structures.html" title="Data structures">Data structure</a>&nbsp;describes the structure of the XML to make the output of the module available in the mapping panel for the following modules.</p><p>If you have a sample of the XML you would like to parse, you can use it to generate the Data structure:</p><div><ol type="1"><li><p>Click on <span><strong>Add</strong></span></p></li><li><p>Click on <span><strong>Generator</strong></span></p></li><li><p>Copy and paste the XML sample into the&nbsp;<span><strong>Sample data</strong></span>&nbsp;field.</p></li><li><p>Click on <span><strong>Save</strong></span></p></li><li><p>Verify that the Data structure has been successfully generated.</p></li><li><p>Click on <span><strong>Save</strong></span> to save the Data structure.</p></li></ol></div><div dir="ltr"><h3>Note</h3><p>You may skip the steps 2-5 to supply an empty Data structure. This way the output of the module will not be available in the mapping panel until the module has been executed at least once to process an XML input.</p></div></td></tr><tr><td><p><span><strong>XML</strong></span></p></td><td><p>The XML formatted text you would like to parse.</p><div dir="ltr"><h3>Caution</h3><p>If you use a formula, make sure its result value type is (or can be automatically&nbsp;coerced&nbsp;to)&nbsp;Text&nbsp;type. If the result value type is&nbsp;Buffer (binary data)&nbsp;then use <code>toString()</code> function to convert it to the&nbsp;Text&nbsp;type.</p></div></td></tr></tbody></table>

### Example

A typical use case is to download an XML file from a URL and parse its content. Here is a step by step guide how to achieve this:

1.  Create a new scenario
    
2.  Insert **HTTP > Get a file** module
    
3.  Open the module's configuration and configure it as follows:
    
    <table><tbody><tr><td><p><span><strong>URL</strong></span></p></td><td><p>URL of the XML file (e.g.<code>https://siftrss.com/f/rqLy05ayMBJ</code>)</p></td></tr></tbody></table>
    
4.  Close the module's configuration.
    
5.  Add **XML > Parse XML** module, connect it after the **HTTP > Get a file** module and configure it as follows:
    
    <table><tbody><tr><td><p><span><strong>Data structure</strong></span></p></td><td><div id="UUID-af87d31a-22de-99f6-1e0b-998efaeebd0d_procedure-idm45601673608208328314600592"><ol type="1"><li><p>Click on <span><strong>Add</strong></span>.</p></li><li><p>Click on <span><strong>Generator</strong></span></p></li><li><p>In your web browser, open a new tab/window.</p></li><li><p>Put the URL you used in the third step in the address bar and fetch the XML file.</p></li><li><p>Select all the XML text and copy it into the clipboard.</p></li><li><p>Close the tab/window and get back to your <span>scenario</span></p></li><li><p>Paste the copied XML text into the&nbsp;<span><strong>Sample data</strong></span>&nbsp;field.</p></li><li><p>Click on <span><strong>Save</strong></span>.</p></li><li><p>Verify that the Data structure has been successfully generated.</p></li><li><p>Click on <span><strong>Save</strong></span> to save the Data structure.</p></li></ol></div><div dir="ltr"><h3>Note</h3><p>You may skip the steps 2-9 to supply an empty data structure. This way the output of the module will not be available in the mapping panel until the module has been executed at least once to process an XML input.</p></div></td></tr><tr><td><p><span><strong>XML</strong></span></p></td><td><p>Map the <code>Data</code> item from the output of the&nbsp;<span><strong>HTTP &gt; Get a file</strong></span>&nbsp;into the field. Use the <code>toString()</code> function to convert its value from&nbsp;Buffer (binary data)&nbsp;type to&nbsp;Text&nbsp;type.</p><p>You may copy and paste the formula's code into the field: <code>{{toString(1.data)}}</code></p></td></tr></tbody></table>
    

### Parsing XML attributes

By default, the  **XML > Parse XML** module will put attributes in a special collection `_attributes` as a child of the node, that has these attributes. If the node is a text node and it has attributes, then two special properties will be added: `_attributes` for attributes and `_value` for the text content of the node.

#### Example

This XML:

```
<root attr="1">
    <node attr="ABC">Hello, World</node>
</root>
```

will be converted into this bundle:

## Creating XML

The **XML > Create XML** module converts a bundle to an XML formatted text.

<table><tbody><tr><td><p><span><strong>Data structure</strong></span></p></td><td><p>The&nbsp;Data structure&nbsp;describes the structure of the resulting XML. If you have a sample of the XML you would like to create, you can use it to generate the Data structure:</p><div><ol type="1"><li><p>Click on <span><strong>Add</strong></span>.</p></li><li><p>Clink on <span><strong>Generator</strong></span>.</p></li><li><p>Copy and paste the XML sample into the&nbsp;<span><strong>Sample data</strong></span> field.</p></li><li><p>Click on <span><strong>Save</strong></span>.</p></li><li><p>Verify that the Data structure has been successfully generated.</p></li><li><p>Click on <span><strong>Save</strong></span> to save the Data structure.</p></li></ol></div></td></tr></tbody></table>

### Example

A typical use case is to transform data from a Google spreadsheet into XML. Here is the procedure on how to transform the data to an XML file in ten steps:

1.  Place the **Google Sheets > Select row**s module in your scenario to fetch the data. Setup the module to retrieve rows from your Google spreadsheet and set the Maximum number of returned rows to a small number, but larger than one for testing purposes (e.g. three). Execute the **Google Sheets** module (right-click it and choose "Run this module only") and verify the output of the module.
    
2.  Connect the **Array Aggregator** module after the Google Sheets module. In the module's setup choose the **Google Sheets** module in the Source node field. Leave the other fields as they are for the moment.
    
3.  Connect **XML > Create XML** module after the **Array Aggregato**r module. The module's setup requires a Data structure that describes the structure of the XML output. Click on **Add** to open the Data structure setup. The easiest way to create this Data structure is to generate it automatically from an XML sample. Click on **Generator** and paste your XML sample to the Sample data field:
    
4.  Click on **Save**. The specification field in the Data structure setup should now contain the generated structure.
    
5.  Change the name of your Data structure to something more specific (e.g. "My XML data structure") and click on the **Save**. If everything goes well, a field corresponding to the root XML element should appear as a mappable field in the XML module's setup.
    
6.  Click on **Map** next to the field and map the `Array[]` item outputted from the **Array aggregator** module to it:
    
7.  Click on **OK** to close the XML module's setup.
    
8.  Open the setup of the **Array Aggregator** module. Change the **target structure** from **Custom** to a **XML** module's field corresponding to the parent XML element. Map items outputted from the Google Sheets module to appropriate fields:
    
9.  Click on the **OK** to close the **Array Aggregator** module's setup.
    
10.  Run the scenario. If everything goes well, the **XML** module should output the correct XML file. Open the setup of the **Google Sheets** module and increase the **Maximum number of returned rows** number to be larger than the number of rows in your spreadsheet to process all the data. The resulting XML can be then saved to Dropbox, sent as an attachment via email, uploaded via FTP to a server, etc.
    

### Adding XML attributes

If you want to add attributes to a complex node (a node, that will contain other nodes), you have to add a collection with the name `_attributes` for this node in your custom Data structure, and this collection will be mapped to node attributes

If you want to add attributes to a text node (example: `<node attr="1">abc</node>`), you have to add a collection `_attributes` for attributes and a text property `_value` for the node value for this node in your custom Data structure.

#### Example

```
{
    "name": "node",
    "type": "collection",
    "spec": [
        {
            "name": "_attributes",
            "type": "collection"
            "spec": [
                 {
                     "name": "attr1",
                     "type": "text"
                 }
            ]
        },
        {
            "name": "_value",
            "type": "text"
        }
    ]
}
```

## Troubleshooting

### Cannot map data from the **Parse XML** module

Make sure the Data structure is defined correctly. Alternatively you may use an empty data structure and execute the module at least once to process an XML input.