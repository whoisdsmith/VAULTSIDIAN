-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Modules](https://www.make.com/en/help/modules.html)
-   Upgrading Gmail and Email App Versions Using Make DevTool

This article describes the upgrading of the [Gmail](https://www.make.com/en/help/apps/communication/gmail.html "Gmail") app to the latest version using Make DevTool. The same upgrade process can be applied to the Email app.

### Warning

Do not use Make DevTool's Swap App tool unless you know what you are doing!

**Prerequisites:**

Existing legacy Gmail or Email app versions in your scenario.

**Upgrading Gmail Modules to the Latest Version:**

1.  Open the scenario that contains the legacy Gmail app version.
    
2.  Press Control+Shift+I or F12 (Windows) or Command+Option+I (Mac) on your keyboard to open Chrome Developer Tools.
    
3.  Open the Make tab.
    
4.  Go to Tools > Swap App.
    
5.  In the tool's pane fill the fields as follows:
    
    <table><tbody><tr><td><p><span><strong>App to be Replaced</strong></span></p></td><td><p>Select the legacy Gmail app you want to replace.</p></td></tr><tr><td><p><span><strong>Version</strong></span></p></td><td><p>Select the legacy version of the Gmail app you want to replace.</p></td></tr><tr><td><p><span><strong>Replace with</strong></span></p></td><td><p>Select the Gmail app you want to replace the legacy modules with.</p></td></tr><tr><td><p><span><strong>Version</strong></span></p></td><td><p>Select the latest version of the Gmail app you want to upgrade the app's modules to.</p></td></tr></tbody></table>
    
6.  When the source and target app versions are specified, click the Run button ![2020-07-24-10_54_28-integration-google-sheets_-google-calendar-_-integromat.png](https://www.make.com/en/help/image/1621f615be8be8.png) in the Swap App tool's pane to perform the Swap App action.
    

All modules of the legacy Gmail app version in your scenario are now upgraded to the desired version.