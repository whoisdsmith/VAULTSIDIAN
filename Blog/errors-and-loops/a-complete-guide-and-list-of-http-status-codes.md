# A Complete Guide and List of HTTP Status Codes

![list of http status codes](https://kinsta.com/wp-content/uploads/2020/02/http-status-codes-1024x512.png)



HTTP status codes are like short notes from a server that get tacked onto a web page. They’re not actually part of the [site’s content](https://kinsta.com/blog/evergreen-content/). Instead, they’re messages from the server letting you know how things went when it received the request to view a certain page.

These kinds of messages are returned every time your browser interacts with a server, even if you don’t see them. If you’re a website owner or [developer](https://kinsta.com/blog/hire-wordpress-developer/), understanding **HT****TP status codes **is critical. When they do show up, HTTP status codes are an invaluable tool for diagnosing and fixing website configuration errors.

This article introduces several server status and error codes, and explains what they reveal about what’s happening on the server behind the scenes.

Let’s dive in!

### Table of Contents

  1. What Are HTTP Status Codes?
  2. Understanding HTTP Status Code Classes
  3. Why HTTP Status Codes and Errors Matter for Search Engine Optimization (SEO)
  4. A Complete Guide and List of HTTP Status Codes
  5. Where to Learn More About HTTP Status Codes

### Prefer to watch the [video version](https://www.youtube.com/watch?v=jTo8U2WeQl8)?

## What Are HTTP Status Codes?

Every time you click on a link or type in a URL and press **Enter**, your browser sends a request to the [webserver](https://kinsta.com/blog/nginx-vs-apache/) for the site you’re trying to access. The server receives and processes the request, and then sends back the relevant resources along with an HTTP header.

HTTP status codes are delivered to your browser in the HTTP header. While status codes are returned every single time your browser requests a web page or resource, most of the time you don’t see them.

It’s usually only when something goes wrong that you might see one displayed in your browser. This is the server’s way of saying: “Something isn’t right. Here’s a code that explains what went wrong.”

![google 404 http status codes](https://kinsta.com/wp-content/uploads/2016/08/google-404-1-1.png)Google 404 HTTP status code

If you want to see the status codes that your browser doesn’t normally show you, there are many different tools that make it easy. Browser extensions are available for developer-friendly platforms such as Chrome and Firefox, and there are many web-based header fetching tools like [Web Sniffer](http://web-sniffer.net/).

To see HTTP status codes with one of these tools, look for the line appearing near the top of the report that says “Status: HTTP/1.1”. This will be followed by the status code that was returned by the server.  

## Understanding HTTP Status Code Classes

HTTP status codes are divided into 5 “classes”. These are groupings of responses that have similar or related meanings. Knowing what they are can help you quickly determine the general substance of a status code _before_ you go about looking up its specific meaning.

The five classes include:

  * **100s:** Informational codes indicating that the request initiated by the browser is continuing.
  * **200s:** Success codes returned when browser request was received, understood, and processed by the server.
  * **300s:** [Redirection codes](https://kinsta.com/blog/wordpress-redirect/) returned when a new resource has been substituted for the requested resource.
  * **400s:** Client error codes indicating that there was a [problem with the request](https://kinsta.com/knowledgebase/400-bad-request/).
  * **500s:** Server error codes indicating that the request was accepted, but that [an error on the server](https://kinsta.com/blog/500-internal-server-error/) prevented the fulfillment of the request.

Within each of these classes, a variety of server codes exist and may be returned by the server. Each individual code has a specific and unique meaning, which we’ll cover in the more comprehensive list below.

## Why HTTP Status Codes and Errors Matter for Search Engine Optimization (SEO)

Search engine bots see HTTP status codes while they’re [crawling your site](https://kinsta.com/blog/wordpress-sitemap/). In some cases, these messages can influence if and how your pages get indexed, as well as how [search engines](https://kinsta.com/blog/alternative-search-engines/) perceive the health of your site.

Generally speaking, 100- and 200-level HTTP status codes won’t have much impact on your [SEO](https://kinsta.com/blog/what-does-seo-stand-for/). They signal that everything is working as it should on your site, and enable search engine bots to continue on their way. However, they aren’t going to boost your rankings either.


For the most part, it’s the higher-level codes that matter for SEO. 400- and 500-level responses [can prevent bots from crawling and indexing your pages](https://kinsta.com/blog/wordpress-robots-txt/). Too many of these errors can also indicate that your site isn’t of high quality, possibly lowering your rankings.

300-level codes have a bit more complicated relationship with SEO. The main thing you need to know to understand their impact is the difference between permanent and temporary redirects, which we’ll cover in more detail in the relevant section below.

In a nutshell, however, permanent redirects share link equity from backlinks, but temporary ones do not. In other words, when you use temporary redirects for pages that have moved, you lose the SEO advantage of all the link building you’ve done.

### Checking for HTTP Status Codes in Google Search Console

One way to monitor how Google perceives the HTTP status codes on your site is to use [Google Search Console](https://kinsta.com/blog/google-search-console/). You can view 300-, 400-, and 500-level status codes in the **Coverage** report:

![search console coverage](https://kinsta.com/wp-content/uploads/2020/02/search-console-coverage-1.png)Google Search Console’s Coverage report

This area of your dashboard shows four types of content on your site:

  * Pages that return errors.
  * Valid pages that have warnings.
  * Resources that are valid.
  * Content excluded from the index.

You may find pages with 300-, 400-, and 500-level HTTP status codes under the **Excluded**, **Error**, or **Valid with warnings** sections, depending on the type of code. For instance, 301 redirects may be listed under **Excluded** as **Page with redirect**:

![search console redirect](https://kinsta.com/wp-content/uploads/2020/02/search-console-redirect-1.png)A page with a redirect in Google Search Console’s Coverage report.

400- and 500-level status codes will likely turn up under **Error**.

Another way to view HTTP status codes is by using the **URL Inspection** tool. If Google is unable to index a specific page due to an error, you’ll see that here:

![search console 404](https://kinsta.com/wp-content/uploads/2020/02/search-console-404-1.png)A [404 error](https://kinsta.com/blog/error-404-not-found/) in Google Search Console’s URL Inspection tool

For more tips on using Google Search Console, check out our [comprehensive guide to the platform](https://kinsta.com/blog/google-search-console/).

## A Complete Guide and List of HTTP Status Codes

While there are over [40 different server status codes](https://tools.ietf.org/html/rfc7231#section-6.1), you’ll likely encounter fewer than a dozen on a regular basis. Below, we’ve covered the more common ones, as well as a few of the more obscure codes you may still run across.

### 100 Status Codes

A 100-level status code tells you that the request you’ve made to the server is still in progress for some reason. This isn’t necessarily a problem, it’s just extra information to let you know what’s going on.

  * **100: **“Continue.” This means that the server in question has received your browser’s request headers, and is now ready for the request body to be sent as well. This makes the request process more efficient since it prevents the browser from sending a body request even though the headers have been rejected.
  * **101: **“Switching protocols.” Your browser has asked the server to change protocols, and the server has complied.
  * **103: **“Early hints.” This returns some response headers before the rest of the server’s response is ready.

### 200 Status Codes

This is the best kind of HTTP status code to receive. A 200-level response means that everything is working exactly as it should.

  * **200:** “Everything is OK.” This is the code that is delivered when a web page or resource acts exactly the way it’s expected to.
  * **201:** “Created.” The server has fulfilled the browser’s request, and as a result, has created a new resource.
  * **202:** “Accepted.” The server has accepted your browser’s request but is still processing it. The request ultimately may or may not result in a completed response.
  * **203: **“Non-Authoritative Information.” This status code may appear when a proxy is in use. It means that the proxy server received a 200 “Everything is OK” status code from the origin server, but has modified the response before passing it on to your browser.
  * **204: **“No Content.”** **This code means that the server has successfully processed the request, but is not going to return any content.
  * **205: **“Reset Content.” Like a 204 code, this means that how server has processed the request but is not going to return any content. However, it also requires that your browser resets the document view.
  * **206:** “Partial Content.” You may see this status code if your HTTP client (also known as your browser) uses ‘range headers’. This enables your browser to resume paused downloads, as well as to split a download into multiple streams. A 206 code is sent when a range header causes the server to send only part of the requested resource.

### 300 Status Codes

[Redirection](https://kinsta.com/help/redirect-rules/) is the process used to communicate that a resource has been moved to a new location. There are several HTTP status codes that accompany redirections, in order to provide visitors with information about where to find the content they’re looking for.

  * **300: **“Multiple Choices.” Sometimes, there may be multiple possible resources the server can respond with to fulfill your browser’s request. A 300 status code means that your browser now needs to choose between them. This may occur when there are multiple file type extensions available, or if the server is experiencing word sense disambiguation.
  * **301:** “The requested resource has been moved permanently.” This code is delivered when a web page or resource has been permanently replaced with a different resource. It is used for permanent [URL redirection](https://kinsta.com/help/redirect-rules/).
  * **302:** “[The requested resource has moved, but was found](https://kinsta.com/blog/http-302/).” This code is used to indicate that the requested resource was found, just not at the location where it was expected. It is used for temporary URL redirection.
  * **303:** “See Other.” Understanding a 303 status code requires that you know the difference between the four primary [HTTP request methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods). Essentially, a 303 code tells your browser that it found the resource your browser requested via POST, PUT, or DELETE. However, to retrieve it using GET, you need to make the appropriate request to a different URL than the one you previously used.
  * **304:** “[The requested resource has not been modified since the last time you accessed it](https://kinsta.com/knowledgebase/http-304/).” This code tells the browser that the resources stored in the browser cache haven’t changed. It’s used to speed up web page delivery by reusing previously-downloaded resources.
  * **307:** “[Temporary Redirect](https://kinsta.com/knowledgebase/307-redirect/).” This status code has replaced 302 “Found” as the appropriate action when a resource has been temporarily moved to a different URL. Unlike the 302 status code, it does not allow the HTTP method to change.
  * **308:** “Permanent Redirect.” The 308 status code is the successor to the 301 “Moved Permanently” code. It does not allow the HTTP method to change and indicates that the requested resource is now permanently located at a new URL.

### 400 Status Codes

At the 400 level, HTTP status codes start to become problematic. These are error codes specifying that there’s a fault with your browser and/or request.

  * **400: **“Bad Request.” The server can’t return a response due to an error on the client’s end. See our guide for [resolving this error](https://kinsta.com/knowledgebase/400-bad-request/).
  * **401:** “[Unauthorized](https://kinsta.com/knowledgebase/401-error/)” or “Authorization Required.” This is returned by the server when the target resource lacks valid authentication credentials. You might see this if you’ve set up basic HTTP authentication using [htpasswd](https://kinsta.com/help/htpasswd/).
![Nginx 401 authorization required error in Chrome](https://kinsta.com/wp-content/uploads/2019/08/nginx-401-authorization-required-chrome-1.png)Nginx 401 authorization required error in Chrome

  * **402: **“Payment Required.” Originally, this code was created for use as part of a digital cash system. However, that plan never followed through. Instead, it’s used by a variety of platforms to indicate that a request cannot be fulfilled, usually due to a lack of required funds. Common instances include: 
    * You’ve reached your daily request limit to the [Google Developers API](https://developers.google.com/products/develop).
    * You haven’t paid your [Shopify](https://kinsta.com/blog/woocommerce-vs-shopify/) fees and your store has been temporarily deactivated.
    * Your payment via [Stripe](https://kinsta.com/blog/stripe-vs-paypal/) has failed, or Stripe is trying to [prevent a fraudulent payment](https://kinsta.com/blog/credit-card-fraud-stripe/).
  * **403:** “Access to that resource is forbidden.” This code is returned when a user attempts to access something that they don’t have permission to view. For example, trying to reach password-protected content without logging in might produce a [403 error](https://kinsta.com/blog/403-forbidden-error/).
  * **404:** “The requested resource was not found.” This is the most common error message of them all. This code means that the [requested resource does not exist](https://kinsta.com/blog/error-404-not-found/), and the server does not know if it ever existed.
  * **405:** “[Method not allowed](https://kinsta.com/blog/405-method-not-allowed-error/).” This is generated when the hosting server (origin server) supports the method received, but the target resource doesn’t.
  * **406:** “[Not acceptable response](https://kinsta.com/blog/406-error/).” The requested resource is capable of generating only content that is not acceptable according to the accept headers sent in the request.
  * **407: **“Proxy Authentication Required.” A proxy server is in use and requires your browser to authenticate itself before continuing.
  * **408:** “The server timed out waiting for the rest of the request from the browser.” This code is generated when a server times out while waiting for the complete request from the browser. In other words, the server didn’t get the full request that was sent by the browser. One possible cause could be net congestion resulting in the loss of data packets between the browser and the server.
  * **409: **“Conflict.” A 409 status code means that the server couldn’t process your browser’s request because there’s a conflict with the relevant resource. This sometimes occurs due to multiple simultaneous edits.
  * **410:** “The requested resource is gone and won’t be coming back.” This is similar to a 404 “Not Found” code, except a 410 indicates that the condition is expected and permanent.
  * **411:** “Length Required.” This means that the requested resource requires that the client specify a certain length and that it did not.
  * **412:** “Precondition Failed.” Your browser included certain conditions in its request headers, and the server did not meet those specifications.
  * **413:** “Payload Too Large” or “[Request Entity Too Large](https://kinsta.com/knowledgebase/413-request-entity-too-large-error/).” Your request is larger than the server is willing or able to process.
  * **414:** “[URI Too Long](https://kinsta.com/knowledgebase/414-request-uri-too-large/).” This is usually the result of a GET request that has been encoded as a query string that is too large for the server to process.
  * **415:** “Unsupported Media Type.” The request includes a media type that the server or resource doesn’t support.
  * **416:** “Range Not Satisfiable.” Your request was for a portion of a resource that the server is unable to return.
  * **417:** “Expectation Failed.” The server is unable to meet the requirements specified in the request’s expect header field.
  * **418:** “I’m a teapot.” This code is returned by teapots that receive requests to brew coffee. It’s also an [April Fool’s Joke from 1998](https://tools.ietf.org/html/rfc2324).
![im a teapot http status code](https://kinsta.com/wp-content/uploads/2020/02/im-a-teapot-1.png)418 “I’m a teapot” status code

  * **422:** “Unprocessable Entity.” The client request contains semantic errors, and the server can’t process it.
  * **425:** “Too Early.” This code is sent when the server is unwilling to process a request because it may be replayed.
  * **426:** “Upgrade Required.” Due to the contents of the request’s upgrade header field, the client should switch to a different protocol.
  * **428:** “Precondition Required.” The server requires conditions to be specified before processing the request.
  * **429:** “Too many requests.” This is generated by the server when the user has sent too many requests in a given amount of time (rate-limiting). This can sometimes occur due to bots or scripts attempting to access your site. In this case, you might want to try [changing your WordPress login URL](https://kinsta.com/blog/wordpress-login-url/#change-login-page). You can also check out our guide to [fixing a 429 “Too Many Requests” error](https://kinsta.com/knowledgebase/429-too-many-requests/).
![429 too many requests](https://kinsta.com/wp-content/uploads/2016/08/429-too-many-requests-1-1.png)429 too many requests

  * **431:** “Request Header Fields Too Large.” The server can’t process the request because the header fields are too large. This may indicate a problem with a single header field, or all of them collectively.
  * **451: **“Unavailable for Legal Reasons.” The operator of the server has received a demand to prohibit access to the resource you’ve requested (or a set of resources including the one you’ve requested). Fun fact: This code is a reference to Ray Bradbury’s novel _[Fahrenheit 451](https://www.arts.gov/national-initiatives/nea-big-read/fahrenheit-451)__._
  * **499:** “Client closed request.” This is returned by NGINX when the client closes the request while [Nginx](https://kinsta.com/knowledgebase/what-is-nginx/) is still processing it.

### 500 Status Codes

500-level status codes are also considered errors. However, they denote that the problem is on the server’s end. This can make them more difficult to resolve.

  * **500:** “There was an error on the server and the request could not be completed.” This is generic code that simply means “internal server error”. Something went wrong on the server and the requested resource was not delivered. This code is typically generated by third-party plugins, faulty PHP, or even the connection to the database breaking. Check out our tutorials on how to [fix the error establishing a database connection](https://kinsta.com/blog/error-establishing-a-database-connection/) and other ways to resolve a [500 internal server error](https://kinsta.com/blog/500-internal-server-error/).
![error establishing a database connection](https://kinsta.com/wp-content/uploads/2016/08/browser-error-establishing-a-database-connection-e1502738213406-1.png)Error establishing a database connection

  * **501:** “Not Implemented.” This error indicates that the server does not support the functionality required to fulfill the request. This is almost always a problem on the web server itself, and usually must be resolved by the host. Check out our recommendations on how to resolve a [501 not implemented error](https://kinsta.com/knowledgebase/501-not-implemented-error/).
  * **502:** “Bad Gateway.” This error code typically means that one server has received an invalid response from another, such as when a proxy server is in use. Other times a query or request will take too long, and so it is canceled or killed by the server and the connection to the database breaks. For more details, see our in-depth tutorial on how to fix the [502 Bad Gateway error](https://kinsta.com/blog/502-bad-gateway/).
  * **503:** “The server is unavailable to handle this request right now.” The request cannot be completed at this point in time. This code may be returned by an overloaded server that is unable to handle additional requests. We have a full guide on how to fix the [503 Service Unavailable Error](https://kinsta.com/blog/http-error-503/).
  * **504:** “The server, acting as a gateway, timed out waiting for another server to respond.” This is the code returned when there are two servers involved in processing a request, and the first server times out waiting for the second server to respond. You can read more about [how to fix 504 errors](https://kinsta.com/blog/504-gateway-timeout/) in our dedicated guide.
  * **505: **“HTTP Version Not Supported.” The server doesn’t support the HTTP version the client used to make the request.
  * **508**: “Resource Limit Is Reached” limits on resources set by your web host have been reached. Check out our tutorial on how to resolve “[508 Resource Limit Is Reached](https://kinsta.com/blog/resource-limit-is-reached/)” error.
  * **511: **“Network Authentication Required.” This status code is sent when the network you’re trying to use requires some form of authentication before sending your request to the server. For instance, you may need to agree to the Terms and Conditions of a public Wi-Fi hotspot.
  * **521:** “Web server is down.” [Error 521 is a Cloudflare-specific error message](https://kinsta.com/knowledgebase/error-521/). It means that your web browser was able to successfully connect to Cloudflare, but Cloudflare was not able to connect to the origin web server.
  * **525**: “[SSL Handshake Failed](https://kinsta.com/knowledgebase/ssl-handshake-failed/)“. Error 525 means that the SSL handshake between a domain using Cloudflare and the origin web server failed. If you are experiencing issues there are five methods you can try to easily [fix error 525](https://kinsta.com/knowledgebase/ssl-handshake-failed/#understanding-what-causes-ssl-handshake-failures).

## Where to Learn More About HTTP Status Codes

In addition to the HTTP status codes we’ve covered in this list, there are some more obscure ones you may want to learn about. There are several resources you can consult to read up on these rarer codes, including:

  * This [comprehensive list of HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) from Wikipedia.
  * [Status code definitions](https://tools.ietf.org/html/rfc7231#section-6) from the Internet Engineering Task Force (IETF).
  * [RFC 7231](https://tools.ietf.org/html/rfc7231#page-63).

Knowing these status codes may help you resolve some unique issues while maintaining your own website, or even when you encounter them on other sites.

[They might seem intimidating at first, but HTTP status codes are important to understand what's happening on your site. Here's a thorough list of those you should get familiar with! 📟🌐Click to Tweet](https://twitter.com/intent/tweet?url=https%3A%2F%2Fkinsta.com%2Fblog%2Fhttp-status-codes%2F&via=kinsta&text=They+might+seem+intimidating+at+first%2C+but+HTTP+status+codes+are+important+to+understand+what%27s+happening+on+your+site.+Here%27s+a+thorough+list+of+those+you+should+get+familiar+with%21+%F0%9F%93%9F%F0%9F%8C%90&hashtags=server%2Cwebdev)

## Summary

While they may seem confusing or intimidating on the surface, HTTP status codes are actually very informative. By learning some of the common ones, you can troubleshoot problems on your site more quickly.

In this post, we’ve defined 40+ HTTP status codes that you may encounter. From the milder 100- and 200-level codes to the trickier 400- and 500-level errors, making sense of these messages is crucial for [maintaining your website](https://kinsta.com/blog/wordpress-maintenance/) and making sure it’s accessible to users. 

* * *



___

#article #Error 