-   [Make Help Center](https://www.make.com/en/help/index-en.html)
-   [Tools](https://www.make.com/en/help/tools.html)
-   Text Parser

## Getting Started with Text Parser

### Transformers

### Caution

The module's dialog field names that are displayed in **bold** (in the Make scenario, **not** in this documentation article) are mandatory!

#### Get Elements from HTML

Retrieves the desired elements from an HTML code.

<table><tbody><tr><td><p><span><strong>Continue the execution of the route even if the module returns no results</strong></span></p></td><td><p>If enabled, the <span>scenario</span> will not be stopped by this module.</p></td></tr><tr><td><p><span><strong>Element type</strong></span></p></td><td><p>Select the type of element you want to retrieve from the HTML code such as image,&nbsp;link, or&nbsp;iframe&nbsp;element(s).</p></td></tr><tr><td><p><span><strong>HTML</strong></span></p></td><td><p>Enter the HTML code you want to retrieve the specified element types from.</p></td></tr></tbody></table>

#### Match Pattern

The **Match pattern** module enables you to find and extract string elements matching a search pattern from a given text. The search pattern is a [regular expression](https://en.wikipedia.org/wiki/Regular_expression) (aka regex or regexp), which is a sequence of characters in which each character is either a metacharacter, having a special meaning, or a regular character that has a literal meaning.

-   The complete list of metacharacters can be found on the [MDN web docs website](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions).
    
-   For a tutorial on how to create regular expressions, we recommend the [RegexOne website](https://regexone.com/).
    
-   For an easy, quick regex generator, try the [Regular Expressions generator](https://regex-generator.olafneumann.org/).
    
-   For experimenting with regular expressions, we recommend the [regular expressions 101 website.](https://regex101.com/) Just make sure to tick the ECMAScript (JavaScript) FLAVOR in the left panel:
    

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Pattern</strong></span></p></td><td><p>Enter the regular expression pattern. For example, <code>[+-]?(\d+(\.\d+)?|\.\d+)([eE][+-]?\d+)?</code> extracts all numerals in the provided text.</p><div dir="ltr"><h3>Note</h3><p>The pattern will contain at least one capture group in parenthesis <code>()</code> for the output bundle to contain some items. If the&nbsp;pattern does not contain any capture groups, the output bundle will be empty:</p><div><p><img src="https://www.make.com/en/help/image/1621f615e35979.png" alt="mceclip0-16.png"></p></div></div></td></tr><tr><td><p><span><em><span><strong>Global match</strong></span></em></span></p></td><td><p>If enabled, then the module retrieves all matches in the text. If disabled, then the module retrieves only the first entry.</p></td></tr><tr><td><p><span><em><span><strong>Case sensitive</strong></span></em></span></p></td><td><p>You can disable the case sensitivity by disabling this option (default=case sensitive).</p></td></tr><tr><td><p><span><em><span><strong>Multiline</strong></span></em></span></p></td><td><p>If checked, <span><strong>beginning</strong></span> and end <span><strong>metacharacters</strong></span> (<code>^</code> and <code>$</code>) will match the beginning or end of each line, not just the very beginning or end of the whole input string.</p></td></tr><tr><td><p><span><em><span><strong>Continue the execution of the route even if the module returns no results</strong></span></em></span></p></td><td><p>If enabled, the <span>scenario</span> will not be stopped by this module.</p></td></tr><tr><td><p><span><strong>Text</strong></span></p></td><td><p>Enter the text you want to match the pattern.</p></td></tr></tbody></table>

#### Replace

Searches the entered text for a specified value or regular expression, and replaces the result with the new value.

<table><tbody><tr><td><p><span><strong>Pattern</strong></span></p></td><td><p>Enter the search term. You can also use a regular expression. For more details about the regular expression, refer to the <a href="https://www.make.com/en/help/tools/text-parser.html#match-pattern" title="Match Pattern">Match Pattern</a> module.</p></td></tr><tr><td><p><span><strong>New value</strong></span></p></td><td><p>Enter a value that will replace the search term.</p></td></tr><tr><td><p><span><strong>Global Match</strong></span></p></td><td><p>If this option is enabled, the module will find all matches rather than stopping after the first match. Each match will be output in a separate bundle.</p></td></tr><tr><td><p><span><strong>Case sensitive</strong></span></p></td><td><p>If this option is enabled, the search will be case sensitive.</p></td></tr><tr><td><p><span><strong>Multiline</strong></span></p></td><td><p>If checked, the beginning and end metacharacters (<code>^</code> and <code>$</code>) will match the beginning or end of each line, not just the very beginning or end of the whole input string.</p></td></tr><tr><td><p><span><strong>Text</strong></span></p></td><td><p>Enter the text to be searched.</p></td></tr></tbody></table>

## Data Scraping

_Data scraping_, sometimes called web scraping, data extraction, or web harvesting is simply the process of collecting data from websites and storing it in your local database or spreadsheets. If you wish to scrape data from a website and you are not familiar with regular expressions, you may use a data scraping tool:

-   [**Apify**](https://apify.com/) is an excellent tool, and we already have it integrated
    
-   [**Best Data Scraping Tools for 2021**](https://www.octoparse.com/blog/best-data-scraping-tools-for-2019-top-10-reviews)
    
-   [**Web Data Extractors 2022**](http://whitepapers.virtualprivatelibrary.net/Web%20Data%20Extractors.pdf)
    

If the data scraping tool provides a REST API, you can connect to it via our universal **[HTTP](https://www.make.com/en/help/tools/http.html "HTTP")** and [Webhooks](https://www.make.com/en/help/tools/webhooks.html "Webhooks") modules. You can also implement an app on your own using the [Make App SDK](https://docs.integromat.com/apps/).