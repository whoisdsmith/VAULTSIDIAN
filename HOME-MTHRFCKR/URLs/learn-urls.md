# Learn URLs

----

TL;DR – URL stands for a Uniform Resource Locator – an address of an Internet resource.

## Contents

-   [1. What Is a URL and Where Is It Located?](https://www.bitdegree.org/learn/uniform-resource-locator#what-is-a-url-and-where-is-it-located)
-   [2. Parts of a URL](https://www.bitdegree.org/learn/uniform-resource-locator#parts-of-a-url)
-   [3. Uniform Resource Locator: Useful Tips](https://www.bitdegree.org/learn/uniform-resource-locator#uniform-resource-locator-useful-tips)

## What Is a URL and Where Is It Located?

A uniform resource locator (URL) is basically what you would call the **website address**. It's a text string that refers the user to a location of a web page or another resource (such as a program or a graphic document). Surfing the web, you can always see the URL of the currently opened page in the browser's **address bar**.

The need for uniform resource locators arose in the 1990s with the appearance and increasing popularity of **world wide web**. To open a file placed not in our own computers but **remote** ones (e.g., servers), we needed to provide browsers the information on how to find and access them.

## Parts of a URL

To better understand a simple uniform resource locator, let's break one down and review all **parts** of the URL separately. To make it easier, we'll use the address to this very tutorial:

**https://www.bitdegree.org/learn/uniform-resource-locator**

| Part | Component | Definition |
| --- | --- | --- |
| https:// | Scheme | Defines the **protocol** for accessing the document or file |
| www. | Prefix | Defines the content as **world wide web** |
| bitdegree | Domain | Defines the **host** or **server** to target |
| .org | Suffix | Defines website's **type** or **location** |
| /learn/uniform-resource-locator | Path | Directs to the **exact resource**. If not defined, the user will be directed to the **main page** of the website. |

You can see these parts in nearly every web address. However, there are a few more that are **optional** and get used less, but you might still encounter them:

| Part | Definition | Placement |
| --- | --- | --- |
| Port | Sets the **port number** of the host (e.g., **:80**). | After the suffix |
| Query string | Defines **specific content** to return (e.g., **?string="a great example"**. URLs with query strings are often called dynamic URLs. | After the path |
| Filename | Defines the name of a **document** (e.g., **valuable-example.jpeg**) | End of an URL |
| Anchor | Directs to an **exact part** of the page (e.g., **#incredible-example)** | End of an URL |

## Uniform Resource Locator: Useful Tips

-   To improve user experience, make your URLs easy to type: avoid **case sensitivity**, skip **non-ASCII** characters and choose **hyphens** over underscores.
-   When you're adding an URL to [HTML links](https://www.bitdegree.org/learn/html-link) you don't neccessarily need to include it whole – a [relative or root relative URL](https://www.bitdegree.org/learn/html-link#absolute-relative-and-root-relative-html-links) is often enough.
-   The **prefix** part of an URL can also represent a **subdomain** (e.g., **best.example.com**).