-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Modules](https://www.make.com/en/help/modules.html)
-   Replacing Google Sheets legacy Modules with New Modules

**A majority of Make apps rely on external services, particularly on their APIs (Application Programming Interfaces). As the services evolve, so do their APIs. New API versions are being regularly released and legacy versions are getting deprecated and eventually shut down.**

We closely follow releases of new API versions and implement new app versions based on the latest APIs.

To keep your scenarios running even after the shutdown of a legacy API, make sure to replace all the **legacy (old) modules** with **new modules**.

Here is a step by step guide:

1.  Choose one of your **legacy scenarios** that is using **legacy modules**, and clone it as a **new scenario.**
    
    1.  Go to the _Scenario diagram_.
        
    2.  Open the _Options_ drop-down menu in the top-right corner and select the _Clone_ option.
        
    3.  Change the name to distinguish between the legacy scenario and the new scenario and click the _Clone_ button.
        
    4.  The new scenario (still with the legacy modules) is created.
        
    
2.  Have the **legacy scenario** and the **new scenario** open in two web browser tabs/windows to easily switch between them.
    
    This step will make your copy-paste job faster and easier.
    
    1.  Open Scenarios in a new browser tab.
        
    2.  Open your **legacy scenario.**
        
    
    For Google Sheets: adding new Google Sheets modules to the scenario **(Step 3, Step 4, Step 5**) can be easily performed using **Make DevTool**.
    
3.  In the **new scenario,** choose the **legacy module** and click on the "upgrade" arrows.
    
4.  Choose the corresponding **new module** from the list of modules.
    
    The new module is placed in the scenario (not connected).
    
    For Google Sheets, check this table to find a new counterpart of your legacy module:
    
    | 
    Legacy Module
    
     | 
    
    New Module
    
     |
    | --- | --- |
    | 
    
    Add a Row
    
     | 
    
    Add a Row
    
     |
    | 
    
    Update a Row
    
     | 
    
    Update a Row
    
     |
    | 
    
    Delete a Row
    
     | 
    
    Delete a Row
    
     |
    | 
    
    Select Rows
    
     | 
    
    Search Rows
    
     |
    | 
    
    Update a Cell
    
     | 
    
    Update a Cell
    
     |
    | 
    
    Add a Worksheet
    
     | 
    
    Add a Sheet
    
     |
    | 
    
    Get a Cell
    
     | 
    
    Get a Cell
    
     |
    | 
    
    Watch a Worksheet
    
     | 
    
    Watch Rows
    
     |
    | 
    
    List Worksheets
    
     | 
    
    List Sheets
    
     |
    | 
    
    Delete a Worksheet
    
     | 
    
    Delete a Sheet
    
     |
    
5.  Drag and drop the **new module** and connect it _after_ the **legacy module**.
    
    For triggers:
    
    1.  Set the new module values in the same way as the legacy module values.
        
    2.  Replace the legacy module with the new module.
        
    
6.  Copy and paste the module's values from the legacy module to the new one.
    
    1.  Open the configuration of the **new module**.
        
    2.  Switch to the tab with the **legacy scenario** and open the configuration of the **legacy module**.
        
    3.  Copy and paste the content of each field from the **legacy module** to the **new module** by switching between the **legacy scenario** and the **new scenario.** If any items are missing in the mapping panel, please see [Mapping](https://www.make.com/en/help/mapping/mapping.html "Mapping").
        
    
    Repeat for every **legacy module** in the **new scenario.**
    
7.  Replace items that are mapped from the legacy module
    
    1.  In the **new scenario,** choose a module that uses the output from a **legacy module** and open its configuration.
        
    2.  For the fields of the proceeding module, replace the **legacy items** outputted from the **legacy module** with corresponding **new items** outputted from the corresponding **new module**.
        
    
    Repeat for every module that uses the output from the **legacy module**.
    
8.  Replace items that are mapped from legacy modules in **filters**.
    
    1.  In the **new scenario,** choose a filter that uses the output from a **legacy module** and open its configuration.
        
    2.  For the conditions of the proceeding filter, replace the **legacy items** outputted from the **legacy module** with the corresponding **new items** outputted from the corresponding **new module**.
        
    
    Repeat for every filter that uses the output from a **legacy module**.
    
    Remove all the **legacy modules** from your scenario.
    
    **Repeat for every scenario using legacy modules.**
    

Adding New Google Sheets Modules to a Google Sheets Scenario with the Make DevTool

1.  Add the Make DevTool extension to your Chrome browser.
    
2.  Open your **Google Sheets (legacy**) scenario.
    
3.  Press Control+Shift+I (Windows) or Command+Option+I (Mac) on your keyboard to open _Chrome Developer Tools_.
    
4.  Go to the Make tab.
    
5.  Open Tools.
    
6.  Click on the Migrate GS tile.
    
7.  Click the Run button.
    

New Google Sheets modules are placed in your scenario. Proceed to enter the values from the legacy modules to the new modules as described in [steps above](https://www.make.com/en/help/modules/replacing-google-sheets-legacy-modules-with-new-modules.html#UUID-93d73896-2b73-7f6f-55d6-a27c7ad0d5ae_N1641222644758 "Step 6").