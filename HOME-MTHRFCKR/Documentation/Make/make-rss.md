# RSS 

The RSS modules enable you to monitor and import items from an RSS feed/Atom export of any website.

## Getting Started With RSS

Prerequisites

-   A URL of the RSS feed/Atom export
    

In order to use RSS with Make, it is necessary to retrieve a feed URL. Please refer to the [How to retrieve the website's feed URL](https://www.make.com/en/help/apps/lifestyle/rss.html#how-to-retrieve-the-website-s-feed-url "How to Retrieve the Website's Feed URL") article.

### Note

The module dialog fields that are displayed in **bold** (in the Make scenario, **not** in this documentation article) are mandatory!

## How to Retrieve the Website's Feed URL

If you don't know the RSS/Atom feed URL of the website you want to retrieve a feed from, you can try adding a common RSS feed URL part after the website URL.

Common feed URLs can be in the following formats: `www.website.com/feed` or `www.website.com/rss`.

For example, `https://www.make.com/en/blog/feed` or `https://www.theguardian.com/uk/technology/rss`.

You can retrieve the RSS feed URL using one of the third-party browser extensions. For example, [RSS Subscription Extension](https://chrome.google.com/webstore/detail/rss-subscription-extensio/nlbjncdgjeocebhnmkbbbdekmmmcbfjd) (Chrome) or [Feedbro](https://addons.mozilla.org/en-US/firefox/addon/feedbroreader/) (Firefox).

You can also find the RSS feed URL manually in the website's source code:

1\. Open the website you want to retrieve a feed from.

2\. Press Ctrl+U (Windows) or Command+Option+U (Mac) on your keyboard to view the page source code.

3\. Press Ctrl+F (Windows) or Command+F (Mac) on your keyboard to search the page source code.

4\. Search for "_rss_", "_feed_", or "_atom_" to find the RSS feed URL.

5\. Copy the URL.

## Triggers

### Watch RSS Feed Items

Returns feed item details when a feed item is posted.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>URL</strong></span></p></td><td><p><a href="https://www.make.com/en/help/apps/lifestyle/rss.html#how-to-retrieve-the-website-s-feed-url" title="How to Retrieve the Website's Feed URL">Enter a URL of the RSS or Atom feed</a>.</p></td></tr><tr><td><p><span><strong>Maximum number of returned items</strong></span></p></td><td><p>Set the maximum number of feed items <span>Make</span> will return during one execution cycle.</p><div dir="ltr"><h3>Caution</h3><p>If the value is set too high, the connection may be interrupted on the side of the given third-party service (timeout). <span>Make</span> has no influence on this. We recommend you set a lower value, and either define a higher value for the maximum number of cycles or run the <span>scenario</span> more frequently. For more information, please see the <span>scenario</span> cycles and phases online <a href="https://www.make.com/en/help/scenarios/scenario-execution,-cycles-and-phases.html" title="Scenario execution, cycles, and phases">help page</a>.</p></div></td></tr><tr><td><p><span><strong>User name</strong></span></p></td><td><p>Enter the user name if the feed is password-protected.</p></td></tr><tr><td><p><span><strong>Password</strong></span></p></td><td><p>Enter the password if the feed is password-protected.</p></td></tr><tr><td><p><span><strong>Process RSS fields</strong></span></p></td><td><p>Enable the <span><em>Google Merchant Center</em></span> option to process fields from the Google Merchant Center feed.</p></td></tr><tr><td><p><span><strong>Request compressed content</strong></span></p></td><td><p>Enable this option to request a compressed version of the website.</p></td></tr></tbody></table>

## Actions

### Retrieve RSS Feed Items

Retrieves feed items from the specified URL.

<table><colgroup><col><col></colgroup><tbody><tr><td><p><span><strong>Process RSS fields</strong></span></p></td><td><p>Enable the <span><em>Google Merchant Center</em></span> option to process fields from the Google Merchant Center feed.</p></td></tr><tr><td><p><span><strong>URL</strong></span></p></td><td><p><a href="https://www.make.com/en/help/apps/lifestyle/rss.html#how-to-retrieve-the-website-s-feed-url" title="How to Retrieve the Website's Feed URL">Enter a URL of the RSS or Atom feed</a>.</p></td></tr><tr><td><p><span><strong>User name</strong></span></p></td><td><p>Enter the user name if the feed is password-protected.</p></td></tr><tr><td><p><span><strong>Password</strong></span></p></td><td><p>Enter the password if the feed is password-protected.</p></td></tr><tr><td><p><span><strong>Date from</strong></span></p></td><td><p>Enter a date you want to filter returned RSS feed items from. <span>Make</span> will process all items that are more recent than the specified date.</p></td></tr><tr><td><p><span><strong>Date to</strong></span></p></td><td><p>Enter a date up to which you want to filter returned RSS feed items. <span>Make</span> will process all items dated on or before the specified date.</p></td></tr><tr><td><p><span><strong>Maximum number of returned items</strong></span></p></td><td><p>Set the maximum number of feed items <span>Make</span> will return during one execution cycle.</p><div dir="ltr" id="UUID-15993c56-c2a3-7931-30f3-b7d12e0ac97d_caution-idm173284336086056"><h3>Caution</h3><p>If the value is set too high, the connection may be interrupted on the side of the given third-party service (timeout). <span>Make</span> has no influence on this. We recommend you set a lower value, and either define a higher value for the maximum number of cycles or run the <span>scenario</span> more frequently. For more information, please see the <span>scenario</span> cycles and phases online <a href="https://www.make.com/en/help/scenarios/scenario-execution,-cycles-and-phases.html" title="Scenario execution, cycles, and phases">help page</a>.</p></div></td></tr><tr><td><p><span><strong>Request compressed content</strong></span></p></td><td><p>Enable this option to request a compressed version of the website.</p></td></tr></tbody></table>

## Common Problems With the Watch RSS Feed Items Trigger

### Trigger Execution Failed

There are several situations when a trigger execution can terminate with an error.

-   The URL you have entered does not exist or does not contain a valid RSS feed/Atom export. If this happens, the scenario will be stopped, and you will need to enter the correct address.
    
-   The RSS/Atom file size exceeds the allowed limit. If this happens, the import will be stopped. For more information, please refer to the [Working with files](https://www.make.com/en/help/mapping/working-with-files.html "Working with files") section.
    

### Trigger Did Not Process RSS Feed Items

With websites that frequently update their RSS feed/Atom export, it can happen that some RSS feed items do not get processed.

Here is an example: A news portal publishes 40 articles every day, but it only includes the last 20 articles in its RSS/Atom export feed. If the interval for processing is set to one day, then Make sees only the last 20 articles. Make does not have access to the previous 20 articles, and therefore, it cannot process them.

If this is the case, you'll need to set a shorter interval for processing the articles, like every 12 hours.

If this is not the case, and the article still has not been processed, it may be that the trigger has not yet reached the given article when being executed.