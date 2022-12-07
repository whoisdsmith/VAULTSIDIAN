# Parsing URL Query String

A definite guide through one of the most common & asked web development operation

![](https://miro.medium.com/max/1400/1*Nrsa5hiyeq31G3BIuV4wSA.png)

*Query String* is one of the most classical and used ways to share data between *environments* and *applications.*

Historically used as a *single-line text* placed inside the `<isindex>` HTML element and sent to the server as a query string addition to the GET request URL, so the web server could respond with a list of pages that matched the keywords.

With the arrival of [*Web Forms*](https://developer.mozilla.org/en-US/docs/Learn/Forms), query strings was then recycled to contain the form fields (*name* + *values*) and thus, gained the shape we know today:

- *Key-value* pair based.
- Within each pair, the *key* and *value* are separated by an equal sign `=`.
- The *key-value* sequences are separated by the ampersand `&` or semicolon sign `;`.
- Some chars cannot be part of the URL and therefore, must be [*encoded*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) through its [UTF-8](https://developer.mozilla.org/en-US/docs/Glossary/UTF-8) representation. E.g. `#`, `SPACE`, so on.

Since then things are pretty much the same, with exception of its use cases, that have grown.

Before we get more depth on the subject, let’s take a look on the URL anatomy to really understand what are we dealing with.

# URL Anatomy

![](https://miro.medium.com/max/1400/1*Z2e-lfNpwspnFbzlvg0IGQ.png)

[Node.js URL anatomy overview](https://nodejs.org/api/url.html)

# URL Encoding

For this process, there are 2 methods available in the Browser’s API:

- `encodeURI()`
- `encodeURIComponent()`

# `encodeURI` vs `encodeURIComponent`

Both methods encodes a URI by replacing the some especial chars with its UTF-8 representation.

The difference is the *character exception list* of each method and given URI assumption.

## encodeURI

Assumes that the given URI is **complete** and will not encode anything between URI `protocol` and `host`.

```
Exception listA-Z a-z 0-9 ; , / ? : @ & = + $ - _ . ! ~ * ' ( ) #
```

## `encodeURIComponent`

Will encode every char that is not in the exception list.

```
Exception listA-Z a-z 0-9 - _ . ! ~ * ' ( )
```

**Example**

```
encodeURI("http://domain.com/?search=foo&page=1&sortBy=desc");// outputs "http://domain.com/?search=foo&page=1&sortBy=desc"encodeURIComponent("http://domain.com/?search=foo&page=1&sortBy=desc")// outputs "http%3A%2F%2Fdomain.com%2F%3Fsearch%3Dfoo%26page%3D1%26sortBy%3Ddesc"
```

# Accessing URL Query String

Retrieving the URL Query String is a fairly simple operation, it is available under the `search` property from the `[window.location](https://developer.mozilla.org/en-US/docs/Web/API/Location/search)` API.

## Example

Assuming that you’re under the following URL, you will get:

> [http://domain.com/?search=foo&page=1&sortBy=desc](http://domain.com/?search=foo&page=1&sortBy=desc)

```
window.location.search// outputs "?search=foo&page=1&sortBy=desc"
```

Alright! We got all the foundation clear, so it’s time to go *straight to the point*.

# Formulas

## ES6

<iframe src="https://medium.com/media/ae658d55ab550faaeb65f0f5c6fd177a" allowfullscreen="" frameborder="0" height="435" width="692" title="Parsing Browser's Query String into Object" class="fo aq as ag ce" scrolling="auto"></iframe>

## Typescript

<iframe src="https://medium.com/media/0de1787e692c25717f5ee9c5b0f170ff" allowfullscreen="" frameborder="0" height="457" width="692" title="Parsing Browser's Query String into Object" class="fo aq as ag ce" scrolling="auto"></iframe>
