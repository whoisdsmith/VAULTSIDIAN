
# Highlights

---

Highlighting while reading has enormous benefits.
It helps you engage more deeply with the text, comprehend dense subjects, and easily revisit key passages in the future.

![](using/highlights/intro.png)

You can create highlights in Raindrop.io [Browser extension](HOME-MTHRFCKR/DEV-DOCS/raindrop-io/help-docs/getting-started/install-extension/index.md), [Desktop](https://raindrop.io/download), [Web](https://app.raindrop.io) and [Mobile](https://raindrop.io/download) app.

:::note
Highlighting is available for all users. There's no limit on total number of pages and highlights.  
But annotations (notes) is [premium feature](premium-features.md).

PDF files not supported yet.
:::

## Create highlight {#add}

Creating a highlight is as simple as selecting text.
When you highlight a passage, the text background will turn yellow so it stands out from the rest of the page.

<details><summary>

### Browser extension {#add-extension}

</summary>

1. Click & drag your mouse across the text that you would like to highlight
2. Press `Ctrl+Shift+S` (or `Cmd+Shift+S` on a Mac) or select `Save highlight` from context menu
3. *Only once*: Accept permission request. [Why?](#extension-permission)

<p><img src={require('./extension.png').default} style={{maxHeight: 155}} /></p>

:::caution Very important!
In Safari (macOS) be sure to click **Always Allow on Every Website** when it ask for permission

<img src={require('./safari-macos-permissions.jpg').default} style={{maxHeight: 312}} />
:::

</details>

<details><summary>

### Safari iOS extension {#add-extension-safari-ios}

</summary>

Select the text you would like to highlight, then tap the color button

<p><img src={require('./safari-ios-select.png').default} style={{maxHeight: 180}} /></p>

----

#### Only once

1. Tap `Puzzle` icon, then `Manage extensions` and enable `Raindrop.io`
2. Tap `Puzzle` icon, tap `Raindrop.io` and go to `Highlights`
3. Give asked permissions

<p><img src={require('./safari-ios.png').default} style={{maxHeight: 355}} /></p>

Be sure to tap **Always Allow on Every Website** when it ask for permission
<p><img src={require('./safari-ios-permissions.jpg').default} style={{maxHeight: 292}} /></p>

</details>

<details><summary>

### iOS & Android app {#add-mobile}

</summary>

1. Tap on a bookmark
2. Select the text you would like to highlight, then tap the color button

:::note
On iOS you can add highlights in Safari browser. [**Learn more**](#add-extension-safari-ios)
:::

:::note
Unfortunately Chrome on Android doesn't support such functionality yet
:::

</details>

<details><summary>

### Web & Desktop app {#add-web}

</summary>

1. Click on a bookmark, then go to `Web` or `Preview` tab
2. Click & drag your mouse across the text that you would like to highlight
3. Select desired highlight color and/or add annotation

<img src={require('./web.png').default} style={{maxHeight: 417}} />

</details>

## Change Color, Annotate, Copy or Delete Highlight {#edit}

When you click (or tap) on a highlight, it takes you to the additional actions. From here, you can take further action on your highlighted passages, including:

- **Change color**
- **Annotate (add note)**: leave your instant thoughts on your highlight, Markdown is supported
- **Copy** to clipboard
- **Delete**: Remove the highlight from the page

<img src={require('./edit.png').default} style={{maxHeight: 224}} />

## View and Manage Highlights {#manage}

You can see all of your highlights of particular page in one place

<details><summary>

### Browser extension {#manage-extension}

</summary>

1. Click Raindrop.io extension icon in a browser toolbar
2. Click `Highlights` button

</details>

<details><summary>

### iOS & Android app {#manage-mobile}

</summary>

1. Go to edit bookmark screen
2. Tap `Highlights`

</details>

<details><summary>

### Web & Desktop app {#manage-web}

</summary>

1. Click on a bookmark
2. Click `Highlights` button in the bottom of the page

<img src={require('./manage.png').default} style={{maxHeight: 583}} />

</details>

## Export Highlights {#export}

You can export highlights of particular page as `text` or `CSV` file

<details><summary>

### Browser extension {#export-extension}

</summary>

1. Click Raindrop.io extension icon in a browser toolbar
2. Click `Highlights` button
3. Click `Export` icon

</details>

<details><summary>

### iOS & Android app {#export-mobile}

</summary>

Not implemented yet

</details>

<details><summary>

### Web & Desktop app {#export-web}

</summary>

1. Click on a bookmark
2. Click `Highlights` button in the bottom of the page
3. Click `Export` icon

</details>

## Search Highlighs {#search}

You can apply the `Highlights` filter to see all of your highlights across all of your bookmarks in one place.

<img src={require('./web-filter.png').default} style={{maxHeight: 174}} />

## Sync {#sync}

<details><summary>

### Readwise {#sync-readwise}

</summary>

[Connect your Raindrop account](https://readwise.io/welcome/sync#raindrop)

</details>

## FAQ

### Why you need additional browser extension permission? {#extension-permission}

To be able to see highlights next time you visit same page we need additional permission called `Access data on websites`.
Don't worry we not track you or send data to third-parties. We just check URL of a page and then load your saved highlights.

Many extensions have this permission by default. But not ours. We decided to ask you explicitly.
