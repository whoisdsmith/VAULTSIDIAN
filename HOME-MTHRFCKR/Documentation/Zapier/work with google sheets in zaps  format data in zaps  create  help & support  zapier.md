If you’re building a Zap that uses Google Sheets—such as triggering from new rows in a sheet, or adding data to a sheet—there are a few things you will need to do to get that sheet ready to work with Zapier. These steps are necessary to ensure we can interact with your sheet effectively.

Before you read on, we recommend following these guides on how to set up your [trigger](https://zapier.com/help/create/basics/set-up-your-zap-trigger) and [action](https://zapier.com/help/create/basics/set-up-your-zap-action).

## [1\. Make sure the first row is a header row with column names](https://zapier.com/help/create/format/work-with-google-sheets-in-zaps#make-sure-the-first-row-is-a-header-row-with-column-names)

We recommend all your columns have text in the header row, but you _must_ have text in the first column header, especially if you are using the Create Spreadsheet Row action. Without any text there, the Zap will send your data to the top of the sheet rather than to the bottom.

[![Example of how to set headers in your spreadsheet](https://zappy.zapier.com/7FFC8975-A1FA-4A25-84C5-5E3D03F35B79.png)](https://zappy.zapier.com/7FFC8975-A1FA-4A25-84C5-5E3D03F35B79.png)

Zaps are intended to only add rows to the end of the spreadsheet and not any other row.

___

## [2\. Don’t include headers for separate sections but do remove blank rows](https://zapier.com/help/create/format/work-with-google-sheets-in-zaps#dont-include-headers-for-separate-sections-but-do-remove-blank-rows)

Your spreadsheet should have no blank rows in between rows with content.

[![Example: Do not include blank rows like you see here in rows 4, 5 and 6.](https://zappy.zapier.com/C76E5C8E-3939-42EA-B3D5-92334424FA5C.png)](https://zappy.zapier.com/C76E5C8E-3939-42EA-B3D5-92334424FA5C.png)

And it should not have any headers for separate sections in the same column.

[![Example: Do not include separate headers, like the “Clothing”, “Size”, and “Quantity” headers here.](https://zappy.zapier.com/03D6DC01-B4AA-424F-8396-8371F898E68A.png)](https://zappy.zapier.com/03D6DC01-B4AA-424F-8396-8371F898E68A.png)

___

## [3\. Don’t delete rows](https://zapier.com/help/create/format/work-with-google-sheets-in-zaps#dont-delete-rows)

Do not delete rows in your spreadsheet while your Zap is on, and don't add rows in the middle of data your Zap has already recognized. This can cause errors with your Zap. If you need to delete any rows, ensure the Zap is turned off as you make your amendments. Once you've finished deleting your rows, you can then turn your Zap back on.

___

## [4\. Don’t include punctuation in your Sheet name](https://zapier.com/help/create/format/work-with-google-sheets-in-zaps#dont-include-punctuation-in-your-sheet-name)

If you include punctuation of any sort, it can make it harder for Zapier to find the right sheet in Google Sheets. This is especially true for colons, which will break your Zap.

[![Example: Do not include colons in your sheet name like “Refunds:complete”](https://zappy.zapier.com/F2666006-A696-44CF-B158-B00A22631626.png)](https://zappy.zapier.com/F2666006-A696-44CF-B158-B00A22631626.png)

___

## [5\. Turn your Zap off before making changes to your sheet](https://zapier.com/help/create/format/work-with-google-sheets-in-zaps#turn-your-zap-off-before-making-changes-to-your-sheet)

The following changes to a sheet while a Zap is switched on can cause a disconnect with your Zap:

If you need to make any of those types of changes to your Google Sheet, you will need to turn your Zap off while you make the change, and then turn it back on again after.

If you rename your Sheet and/or worksheet(s) within the Sheet, you'll need to reselect them in the Zap Editor to update to the new names.

Once you’ve set your sheet up you’re ready to continue setting up the rest of your Zap, whether that’s setting up your [action](https://zapier.com/help/create/basics/set-up-your-zap-action), or adding a [search](https://zapier.com/help/create/basics/search-for-existing-data-in-zaps) step.