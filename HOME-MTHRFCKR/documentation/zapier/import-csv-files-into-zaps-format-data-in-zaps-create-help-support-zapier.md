**I don't see my full CSV file when I run a test step**

The test step is limited to 1,000 characters of text and 50 line items. When the Zap runs, it will import the full CSV file.

**Error: CSV Import only supports file sizes < 150K**

The Import CSV File utility only supports importing files that are 150 KB or less in size (around 1,000 rows of a 10 column CSV file). You'll need to split the CSV file into multiple files if it's too large.

**Error: Could not determine delimiter**

The CSV file you're trying to import doesn't use a recognized delimiter (commas, semi-colons, tabs), or the delimiter wasn’t recognized. If you know your delimiter or you have a One Column CSV, you can select it in the _Type of CSV File_ option.

**Error: utf8 codec can't decode byte xxx in position yyyy: invalid continuation byte**

The Import CSV File utility only supports ASCII and UTF-8 encoding. You'll need to re-encode your CSV in order to import it into your Zap.

**My action app does not support line items**

You can use Formatter to [convert line items into text strings](https://zapier.com/help/create/format/convert-line-items-into-text-strings).