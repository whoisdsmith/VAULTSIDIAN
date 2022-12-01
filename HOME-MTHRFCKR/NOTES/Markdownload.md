# Markdownload Extension

---

## Custom text ℹ️

For the title, as well as the front- and back-matter custom text, you can use the following text replacement values. Please note that not all websites will provide all values

-   `{title}` - Article Title
-   `{pageTitle}` - Title of the actual page
-   `{length}` - Length of the article, in characters
-   `{excerpt}` - Article description or short excerpt from the content
-   `{byline}` - Author metadata
-   `{dir}` - Content direction
-   `{date:FORMAT}` - The current date and time. Check the [format reference](https://momentjs.com/docs/#/displaying/format/)
-   `{keywords}` - Meta keywords (if present). Comma separated by default.
-   `{keywords:SEPARATOR}` - Meta keywords (if present) separated by SEPARATOR. For example, to separate by space, use `{keywords: }`

There is also support for all meta tags not mentioned above, should the page you are clipping support them. For example, try `{og:image}` or any other widely supported meta tags

URL information:

-   `{baseURI}` - The url of the article
-   `{origin}` - The origin of the URL, that is its scheme, its domain and its port.
-   `{host}` - The domain (that is the _hostname_) followed by (if a port was specified) a `':'` and the _port_ of the URL.
-   `{hostname}` - The domain of the URL.
-   `{port}` - The port number of the URL.
-   `{protocol}` - The protocol scheme of the URL, including the final `':'`.
-   `{pathname}` - An initial `'/'` followed by the path of the URL, not including the query string or fragment.
-   `{search}` - The URL's parameter string; if any parameters are provided, this string includes all of them, beginning with the leading `?` character.
-   `{hash}` - A '#' followed by the fragment identifier of the URL.

Additionally, you can 'parameterize' any of the text variables (other than date and keywords) by using the following syntax:

-   `{variable:pascal}` - PascalCase: Every word capital
-   `{variable:camel}` - camelCase: every word capital except the first word
-   `{variable:kebab}` - kebab-case: hyphens between words, all lowercase
-   `{variable:snake}` - snake_case: underscores between words, all lowercase

---

