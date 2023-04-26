# Search

---

Raindrop can search by bookmark details, URL, tag, type, date or [entire content](#full-text-search) of web-page or PDF (no OCR).
Best in class support for 16 languages. Find precisely by crafting advanced searches with our [super power operators](#operators).

![](using/search/intro.png)

## Recent Searches {#recent}

Raindrop will remember your ten most recent searches so you can easily return to the list of results.
Plus, these recent searches will sync across your apps so you can continue a search on another device or computer.

## Full-Text Search {#full-text-search}

Raindrop can search through the entire content of every bookmark and PDF (no OCR) you’ve saved, making it extremely easy to find what you’re looking for. It's like your personal Google!

Your bookmarks are indexed automatically, no need to do anything. Usually only meaningful content of web-page is indexed. Ads, navigation, comments and so on are stripped if possible.

<!------------------------------>
<details><summary>

### How to use?

</summary>

1. Be sure you have a [Pro plan](premium-features.md)
2. Focus on a search field, type your request and press Enter
3. Found parts will be highlighted in search results along with other details:

<p><img src={require('./full1.png').default} style={{maxHeight:313}} /></p>

:::note
Be sure that newly added bookmark will not appear in search results immediately. We need some time as described in [this article](HOME-MTHRFCKR/DEV-DOCS/raindrop-io/help-docs/backups.md#how-long-it-takes-to-copy-all-of-my-bookmarks) to copy and index each bookmark.
:::

</details>

<!------------------------------>
<details><summary>

### Turn off

</summary>

If you want to temporarly disable full-text search please select `In title/description` filter from suggestions.

Or type `info:` before your search query.

![](using/search/filters.png)

</details>

## Advanced Search Operators {#operators}

To find precisely you can craft advanced searches using Boolean operators.

![](using/search/operators.png)

Listed below are the search operators we support, with quick examples showing how they may be used.
No need to remember everything listed below, our smart search suggestions will show them for you.

Mix-and-match to find exactly what you're looking for.

Operator | Example | Explanation

- | - | -
`apple iphone`          | apple iphone              | Find items that contains such words in title, description, domain or in web page content
`"sample"`              | "superman vs. batman"     | Find items that contains exact phrase in title, description, domain or in web page content
`-sample`               | -superman <br/> -#coffee  | Requires that the search results do not include this word or condition
`#tag`                  | #coffee                   | Find items that have a certain tag
`#"one tag"`            | #"coffee beans"           | Find items that have a certain multi-word tag
`match:OR`              | superman batman match:OR  | Find items with either search term
`created:YYYY-MM-DD` <br/> `created:YYYY-MM` <br/> `created:YYYY` | created:2021-07-15 <br/> created:2021-07 <br/> created:2021 <br /> created:>2021-07-15 <br /> created:<2021-07-15 | Search for items created in specific date. <br/> Put < or > in front of a date to find before or after specific date respectively
`lastUpdate:YYYY-MM-DD` | lastUpdate:2021-07-15     | Search for items updated in specific date
`link:sample`           | link:drop <br/> link:"crunch base" | Find items with a certain word (or words) in the URL
`❤️`                     | ❤️                         | Find all favorites
`type:sample`           | type:link <br/> type:article <br/> type:image <br/> type:video <br/> type:document <br/> type:audio | Find by type
`file:true`             | file:true                 | Find files
`notag:true`            | notag:true                | Find items without tags
`cache.status:sample`   | cache.status:ready <br/> -cache.status:ready | Find items that have (or not) a [permanent copy](HOME-MTHRFCKR/DEV-DOCS/raindrop-io/help-docs/backups.md#permanent-library)

## Broken links

Raindrop.io can periodically check all your bookmarks for availability.
If any URL hit dead you will notice a special 'ghost' icon next to bookmark domain name.

![](using/search/brokens.png)

<!------------------------------>
<details><summary>

### Find all broken links {#find-broken}

</summary>

Select `Broken links` filter from search field suggestions.

:::info
Only available in [Pro plan](premium-features.md)
:::

![](using/search/filters.png)

</details>

<!------------------------------>
<details><summary>

### Remove broken links

</summary>

1. [Find broken links](#find-broken) you want to remove
2. Highlight the items you want to remove by hovering over the items until the tick appears in the left corner, and then click on the tick.
3. Highlight as many items as you like, then click Remove in the menu bar at the top.

</details>

<!------------------------------>
<details><summary>

### Troubleshooting

</summary>

Check [this article](False-Broken-Links.md) if you have any problems with broken links checker.

</details>

## Duplicates

Have you ever bookmarked a page more than once?

Duplicate bookmarks take up space and needlessly add to a surplus of saved pages.
Raindrop.io can help you locate and remove duplicates bookmarks.

<!------------------------------>
<details><summary>

### Find all duplicates {#find-duplicates}

</summary>

Select `Duplicates` filter from search field suggestions.

:::info
Only available in [Pro plan](premium-features.md)
:::

:::tip
When you click on `Duplicates` filter you will see **only** duplicate bookmarks.
This list not includes **originals**. So it's safe to remove them all.
:::

![](using/search/filters.png)

</details>

<!------------------------------>
<details><summary>

### Remove duplicates

</summary>

1. [Find duplicates](#find-duplicates) you want to remove
2. Highlight the items you want to remove by hovering over the items until the tick appears in the left corner, and then click on the tick.
3. Highlight as many items as you like, then click Remove in the menu bar at the top.

</details>

<!------------------------------>
<details><summary>

### How it works internally?

</summary>

Bookmark considered as duplicate only if it URL is exactly the same to previously saved bookmark.

All garbage from URL like different protocol, WWW, trailing slashes, useless query parameters (like referral id or advert source) and hash strings are ignored.

![](using/search/duplicates-how.jpg)

</details>

## Limitations

- Full-text search
  - Indexing is happen with slight delay, usually few minutes
  - We can index up to 300,000 characters in one document/page
  - Bookmark should have a [permanent copy](HOME-MTHRFCKR/DEV-DOCS/raindrop-io/help-docs/backups.md#permanent-library) to support full-text search
