# Help Google choose the right canonical URL for your duplicate pages

bookmark_border Stay organized with collections Save and categorize content based on your preferences.

If you have a single page that's accessible by multiple URLs, or different pages with similar content (for example, a page with both a mobile and a desktop version), Google sees these as duplicate versions of the same page. Google will choose one URL as the *canonical* version and crawl that, and all other URLs will be considered *duplicate* URLs and crawled less often.

If you don't explicitly tell Google which URL is canonical, Google will make the choice for you, or might consider them both of equal weight, which might lead to unwanted behavior, as explained in [Reasons to choose a canonical URL](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls#why-it-matters).

## What is a canonical URL?

A *canonical URL* is the URL of the page that Google thinks is most representative from a set of duplicate pages on your site. For example, if you have URLs for the same page (`example.com?dress=1234` and `example.com/dresses/1234`), Google chooses one as canonical.

The pages don't need to be absolutely identical; minor changes in sorting or filtering of list pages don't make the page unique (for example, sorting by price or filtering by item color). The canonical URL can be in a different domain than a duplicate URL.

## How Google indexes and chooses the canonical URL

<iframe frameborder="0" allowfullscreen="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" title="Canonical URLs: How Does Google Pick the One? #AskGoogleWebmasters" width="640" height="360" src="https://www.youtube.com/embed/8j_hxBw5B4E?origin=https%3A%2F%2Fdevelopers.google.com&amp;video-id=8j_hxBw5B4E&amp;enablejsapi=1&amp;widgetid=1" sandbox="allow-same-origin allow-scripts allow-forms allow-popups allow-popups-to-escape-sandbox" id="widget2"></iframe>

When Google indexes a site, it tries to determine the primary content of each page. If Google finds multiple pages on the same site that seem to be the same, it chooses the page that it thinks is the most complete and useful, and marks it as canonical. The canonical page will be crawled most regularly; duplicates are crawled less frequently in order to reduce the crawling load on your site.

Google chooses the canonical page based on a number of factors (or *signals*), such as whether the page is served via HTTP or HTTPS, page quality, presence of the URL in a sitemap, and any `rel=canonical` labeling. You can [indicate your preference to Google](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls#define-canonical) using these techniques, but Google may choose a different page as canonical than you do, for various reasons.

Different language versions of a single page are considered duplicates only if the main content is in the same language (that is, if only the header, footer, and other non-critical text is translated, but the body remains the same, then the pages are considered to be duplicates).

Google uses the canonical pages as the main sources to evaluate content and quality. A Google Search result usually points to the canonical page, unless one of the duplicates is explicitly better suited for a user. For example, the search result will probably point to the mobile page if the user is on a mobile device, even if the desktop page is marked as canonical.

## Reasons for having similar or duplicate pages

There are valid reasons why your site might have different URLs that point to the same page, or have duplicate or very similar pages at different URLs. Here are the most common reasons:

-   To support **multiple device types:**
    
    ```
    https://example.com/news/koala-rampage
    https://m.example.com/news/koala-rampage
    https://amp.example.com/news/koala-rampage
    ```
    
-   To enable **dynamic URLs** for things like search parameters or session IDs:
    
    ```
    https://www.example.com/products?category=dresses&color=green
    https://example.com/dresses/cocktail?gclid=ABCD
    https://www.example.com/dresses/green/greendress.html
    ```
    
-   If your blog system automatically saves **multiple URLs** as you position the same post under multiple sections.
    
    ```
    https://blog.example.com/dresses/green-dresses-are-awesome/
    https://blog.example.com/green-things/green-dresses-are-awesome/
    ```
    
-   If your server is configured to serve the **same content for www/non-www http/https and protocol port variants**:
    
    ```
    https://example.com/green-dresses
    https://example.com/green-dresses
    https://www.example.com/green-dresses
    https://example.com:80/green-dresses
    https://example.com:443/green-dresses
    ```
    
-   If content you provide on a blog for **syndication** to other sites is replicated in part or in full on those domains:  
    `https://news.example.com/green-dresses-for-every-day-155672.html` (syndicated post) `https://blog.example.com/dresses/green-dresses-are-awesome/3245/` (original post)

## Reasons to choose a canonical URL

<iframe frameborder="0" allowfullscreen="1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" title="Canonicalization: SEO Mythbusting" width="640" height="360" src="https://www.youtube.com/embed/gEWkYTPSEjs?origin=https%3A%2F%2Fdevelopers.google.com&amp;video-id=gEWkYTPSEjs&amp;enablejsapi=1&amp;widgetid=3" sandbox="allow-same-origin allow-scripts allow-forms allow-popups allow-popups-to-escape-sandbox" id="widget4"></iframe>

There are a number of reasons why you would want to explicitly choose a canonical page in a set of duplicate or similar pages:

-   **To specify which URL that you want people to see in search results.** You might prefer people reach your green dresses product page via `https://www.example.com/dresses/green/greendress.html` rather than `https://example.com/dresses/cocktail?gclid=ABCD`.
-   **To consolidate link signals for similar or duplicate pages**. It helps search engines to be able to consolidate the information they have for the individual URLs (such as links to them) into a single, preferred URL. This means that links from other sites to `https://example.com/dresses/cocktail?gclid=ABCD` get consolidated with links to `https://www.example.com/dresses/green/greendress.html`.
-   **To simplify tracking metrics for a single product or topic**. With a variety of URLs, it's more challenging to get consolidated metrics for a specific piece of content.
-   **To manage syndicated content.** If you syndicate your content for publication on other domains, you want to ensure that your preferred URL appears in search results.
-   **To avoid spending crawling time on duplicate pages**. You want Googlebot to get the most out of your site, so it's better for it to spend time crawling new (or updated) pages on your site, rather than crawling the desktop and mobile versions of the same pages.

## Learn which page Google considers canonical

Use the [URL Inspection tool](https://support.google.com/webmasters/answer/9012289#google-selected-canonical) to learn which page Google considers canonical. Even if you explicitly designate a canonical page, Google might choose a different canonical for various reasons, such as performance or content.

## Specify a canonical page

To specify a canonical URL for duplicate URLs or similar pages, choose one of the following methods. While we encourage you to use any of these methods, none of them are required. If you don't indicate a canonical URL, we'll identify what we think is the best version or URL. Be sure to follow the [general guidelines](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls#best-practices).

**If you use a CMS, such as Wix or Blogger**, you might not be able to edit your HTML directly. Instead, your CMS might have a search engine settings page or some other mechanism to tell search engines about the canonical URL. Search for instructions about modifying the `<head>` of your page on your CMS (for example, search for "wix set the canonical tag").

| Method and description |
| --- |
| [`rel=canonical <link>` tag](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls#rel-canonical-link-method) | 
Add a `<link>` tag in the code for all duplicate pages, pointing to the canonical page.

<table><tbody><tr><td width="50%"><span class="compare-yes" aria-hidden="true"></span><b>Pros:</b><ul><li>Can map an infinite number of duplicate pages.</li></ul></td><td width="50%"><p><span class="compare-no" aria-hidden="true"></span><b>Cons:</b></p><ul><li>Can add to the size of the page.</li><li>Can be complex to maintain the mapping on larger sites, or sites where the URLs change often.</li><li>Only works for HTML pages, not for files such as PDF. In such cases, you can use the <code translate="no" dir="ltr">rel=canonical</code> HTTP header.</li></ul></td></tr></tbody></table>



 |
| [`rel=canonical` HTTP header](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls#rel-canonical-header-method) | 

Send a `rel=canonical` header in your page response.

<table><tbody><tr><td width="50%"><p><span class="compare-yes" aria-hidden="true"></span><b>Pros:</b></p><ul><li>Doesn't increase page size.</li><li>Can map an infinite number of duplicate pages.</li></ul></td><td width="50%"><p><span class="compare-no" aria-hidden="true"></span><b>Cons:</b></p><ul><li>Can be complex to maintain the mapping on larger sites, or sites where the URLs change often.</li></ul></td></tr></tbody></table>



 |
| [Sitemap](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls#sitemap-method) | 

Specify your canonical pages in a sitemap.

<table><tbody><tr><td width="50%"><p><span class="compare-yes" aria-hidden="true"></span><b>Pros:</b></p><ul><li>Easy to do and maintain, especially on large sites.</li></ul></td><td width="50%"><p><span class="compare-no" aria-hidden="true"></span><b>Cons:</b></p><ul><li>Google must still determine the associated duplicate for any canonicals that you declare in the sitemap.</li><li>Less powerful signal to Google than the <code translate="no" dir="ltr">rel=canonical</code> mapping technique.</li></ul></td></tr></tbody></table>



 |
| [`301` redirect](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls#redirects-method) | Use `301` redirects to tell Googlebot that a redirected URL is a better version than a given URL. Use this only when deprecating a duplicate page. |
| [AMP variant](https://developers.google.com/search/docs/crawling-indexing/amp) | If one of your variants is an AMP page, follow the AMP guidelines to indicate the canonical page and AMP variant. |

### General guidelines

For all canonicalization methods, follow these general guidelines:

-   **Don't** use the robots.txt file for canonicalization purposes.
-   **Don't** use the URL removal tool for canonicalization. It removes *all* versions of a URL from Search.
-   **Don't** specify different URLs as canonical for the same page using the same or different canonicalization techniques (for example, don't specify one URL in a sitemap but a different URL for that same page using `rel="canonical"`).
-   **Don't** use [`noindex`](https://developers.google.com/search/docs/crawling-indexing/block-indexing) as a means to prevent selection of a canonical page. This directive is intended to exclude the page from the index, not to manage the choice of a canonical page.
-   Specify a canonical page when using [hreflang tags](https://developers.google.com/search/docs/specialty/international/localized-versions). Specify a canonical page in same language, or the best possible substitute language if a canonical doesn't exist for the same language.
    
-   Link to the canonical URL rather than a duplicate URL, when linking within your site. Linking consistently to the URL that you consider to be canonical helps Google understand your preference.
    

#### Prefer HTTPS over HTTP for canonical URLs

Google prefers HTTPS pages over equivalent HTTP pages as canonical, except when there are issues or conflicting signals such as the following:

-   The HTTPS page has an invalid SSL certificate.
-   The HTTPS page contains insecure dependencies (other than images).
-   The HTTPS page redirects users to or through an HTTP page.
-   The HTTPS page has a `rel="canonical"` `link` to the HTTP page.

Although our systems prefer HTTPS pages over HTTP pages by default, you can ensure this behavior by taking any of the following actions:

-   Add redirects from the HTTP page to the HTTPS page.
-   Add a `rel="canonical"` `link` from the HTTP page to the HTTPS page.
-   Implement [HSTS](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security).

To prevent Google from incorrectly making the HTTP page canonical, **avoid** the following practices:

-   Avoid bad TLS/SSL certificates and HTTPS-to-HTTP redirects because they cause Google to prefer HTTP very strongly. Implementing HSTS cannot override this strong preference.
-   Avoid including the HTTP page in your sitemap or [hreflang entries](https://developers.google.com/search/docs/specialty/international/localized-versions) rather than the HTTPS version.
-   Avoid implementing your SSL/TLS certificate for the wrong host-variant. For example, example.com serving the certificate for www.example.com. The certificate must match your complete site URL, or be a wildcard certificate that can be used for multiple subdomains on a domain.

### Use a `rel="canonical"` `link` tag

To indicate when a page is a duplicate of another page, you can use a `<link>` tag in the `head` section of your HTML.

Suppose you want `https://example.com/dresses/green-dresses` to be the canonical URL, even though a variety of URLs can access this content. Indicate this URL as canonical with these steps:

1.  Mark all duplicate pages with a `rel="canonical"` link tag.
    
    Add a ``<`link`>`` element with the attribute `rel="canonical"` to the `<head>` section of duplicate pages, pointing to the canonical page. For example:
    
    ```
    <link rel="canonical" href="https://example.com/dresses/green-dresses" />
    ```
    
2.  If the canonical page has a mobile variant, add a `rel="alternate"` `link` to it, pointing to the mobile version of the page:
    
    ```
    <link rel="alternate" media="only screen and (max-width: 640px)"  href="https://m.example.com/dresses/green-dresses">
    ```
    
3.  Add any [hreflang](https://developers.google.com/search/docs/specialty/international/localized-versions) or other redirects that are appropriate for the page.

Use absolute paths rather than relative paths with the `rel="canonical"` `link` tag.

**Recommended**: `https://www.example.com/dresses/green/greendress.html`

**Not recommended**: `/dresses/green/greendress.html`

If you use JavaScript to add the `rel="canonical"` link tag, make sure to [inject the canonical link tag properly](https://developers.google.com/search/docs/crawling-indexing/javascript/javascript-seo-basics#properly-inject-canonical-links).

### Use a `rel="canonical"` HTTP header

If you can configure your server, you can use a `rel="canonical"` [HTTP header](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields) (rather than an HTML tag) to indicate the canonical URL for a document supported by Search, including non-HTML documents such as PDF files.

Google currently supports this method for web search results only.

If you expose a PDF file through multiple URLs, you can return a `rel="canonical"` HTTP header to tell Googlebot what is the canonical URL for the PDF file:

```
Link: <https://www.example.com/downloads/white-paper.pdf>; rel="canonical"
```

The recommendations for the `rel="canonical"` HTTP header are the same as `rel="canonical"` `link` tag. As per [RFC2616](https://www.rfc-editor.org/rfc/rfc2616.html), use only double quotes in the `rel="canonical"` HTTP header.

### Use a sitemap

Pick a canonical URL for each of your pages and submit them in a [sitemap](https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview). All pages listed in a sitemap are suggested as canonicals; Google will decide which pages (if any) pages are duplicates, based on similarity of content.

We don't *guarantee* that we'll consider the sitemap URLs to be canonical, but it is a simple way of defining canonicals for a large site, and sitemaps are a useful way to tell Google which pages you consider most important on your site.

**Don't** include non-canonical pages in a sitemap. If you're using a sitemap, specify only canonical URLs in the sitemap.

### Use `301` redirects for retired URLs

Use this method when you want to get rid of existing duplicate pages, but need to ensure a smooth transition before you retire the old URLs.

Suppose your page can be reached in multiple ways:

-   `https://example.com/home`
-   `https://home.example.com`
-   `https://www.example.com`

Pick one of those URLs as your canonical URL, and use `301` redirects to send traffic from the other URLs to your preferred URL. A server-side `301` redirect is the best way to ensure that users and search engines are directed to the correct page. The `301` status code means that a page has permanently moved to a new location.

If you are on a website hosting service, do a search for their documentation on setting up `301` redirects.

## Troubleshooting

If a canonical URL is in a property that you don't own, you won't be able to see any of the traffic for your duplicate page. Here are some common reasons that a canonical can exist in a separate property:

-   **Incorrectly marked language variants:** If you have multiple websites that serve substantially the same content localized to different users around the world, be sure to [follow our guidelines for localized sites](https://developers.google.com/search/docs/specialty/international).
-   **Incorrect canonical tags:** Some content management systems (CMS) or CMS plugins can make incorrect use of canonicalization techniques to point to URLs on external websites. Check your content to see if this is the case. If your site is indicating an unexpected canonical URL preference, perhaps through incorrect use of `rel="canonical"` or a `301` redirect, fix that issue directly.
-   **Misconfigured servers:** Some hosting misconfigurations may cause unexpected cross-domain URL selection. For example:
    -   A server may be misconfigured to return content from a.com in response to a request for a URL on b.com
    -   Two unrelated web servers may return identical [`soft 404` pages](https://developers.google.com/search/docs/crawling-indexing/http-network-errors#soft-404-errors) that Google fails to identify as error pages.
-   **Malicious hacking:** Some attacks on websites introduce code that returns an HTTP [301 redirect](https://developers.google.com/search/docs/crawling-indexing/301-redirects) or inserts a cross-domain `rel="canonical"` link tag into the HTML `<head>` or HTTP header, usually pointing to a URL hosting malicious or spammy content. In these cases our algorithms may select the malicious or spammy URL instead of the URL on the compromised website.
-   **A copycat website:** In rare situations, our algorithm may select a URL from an external site that is hosting your content without your permission. If you believe that another site is duplicating your content in violation of copyright law, you may contact the site's host to request removal. In addition, you can request that Google remove the infringing page from our search results by [filing a request under the Digital Millennium Copyright Act](https://support.google.com/legal/answer/1120734).