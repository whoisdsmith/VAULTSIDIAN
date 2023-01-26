---
created: 2022-08-09T17:02:24 (UTC -04:00)
tags: []
source: https://dashy.to/docs/
author: 
---

# Keyboard Shortcuts | Dashy

---
## Searching[#](https://dashy.to/docs/#searching "Direct link to heading")

One of the primary purposes of Dashy is to allow you to quickly find and launch a given app. To make this as quick as possible, there is no need to touch the mouse, or press a certain key to begin searching - just start typing. Results will be filtered in real-time. No need to worry about case, special characters or small typos, these are taken care of, and your results should appear.

## Navigating[#](https://dashy.to/docs/#navigating "Direct link to heading")

You can navigate through your items or search results using the keyboard. You can use Tab to cycle through results, and Shift + Tab to go backwards. Or use the arrow keys, ↑, →, ↓ and ←.

## Launching Apps[#](https://dashy.to/docs/#launching-apps "Direct link to heading")

You can launch a elected app by hitting Enter. This will open the app using your default opening method, specified in `target` (either `newtab`, `sametab`, `modal`, `top` or `workspace`). You can also use Alt + Enter to open the app in a pop-up modal, or Ctrl + Enter to open it in a new tab. For all available opening methods, just right-click on an item, to bring up the context menu.

## Tags[#](https://dashy.to/docs/#tags "Direct link to heading")

By default, items are filtered by the `title` attribute, as well as the hostname (extracted from `url`), the `provider` and `description`. If you need to find results based on text which isn't included in these attributes, then you can add `tags` to a given item.

```
  items:  - title: Plex    description: Media library    icon: favicon    url: https://plex.lab.local    tags: [ movies, videos, music ]  - title: FreshRSS    description: RSS Reader    icon: favicon    url: https://freshrss.lab.local    tags: [ news, updates, blogs ]
```

In the above example, Plex will be visible when searching for 'movies', and FreshRSS with 'news'

## Custom Hotkeys[#](https://dashy.to/docs/#custom-hotkeys "Direct link to heading")

For apps that you use regularly, you can set a custom keybinding. Use the `hotkey` parameter on a certain item to specify a numeric key, between `0 - 9`. You can then launch that app, by just pressing that key, which is much quicker than searching for it, if it's an app you use frequently.

```
- title: Bookstack  icon: far fa-books  url: https://bookstack.lab.local/  hotkey: 2- title: Git Tea  icon: fab fa-git  url: https://git.lab.local/  target: workspace  hotkey: 3
```

In the above example, pressing 2 will launch Bookstack. Or hitting 3 will open Git in the workspace view.

## Web Search[#](https://dashy.to/docs/#web-search "Direct link to heading")

It's possible to search the web directly from Dashy, which might be useful if you're using Dashy as your start page. This can be done by typing your query as normal, and then pressing ⏎. Web search options are configured under `appConfig.webSearch`.

### Setting Search Engine[#](https://dashy.to/docs/#setting-search-engine "Direct link to heading")

Set your default search engine using the `webSearch.searchEngine` property. This defaults to DuckDuckGo. Search engine must be referenced by their key, the following providers are supported:

-   [`duckduckgo`](https://duckduckgo.com/), [`google`](https://google.com/), [`whoogle`](https://whoogle.sdf.org/), [`qwant`](https://www.qwant.com/), [`startpage`](https://www.startpage.com/), [`searx-bar`](https://searx.bar/), [`searx-info`](https://searx.info/)
-   [`searx-tiekoetter`](https://searx.tiekoetter.com/), [`searx-bissisoft`](https://searx.bissisoft.com/), [`ecosia`](https://www.ecosia.org/), [`metager`](https://metager.org/meta), [`swisscows`](https://swisscows.com/), [`mojeek`](https://www.mojeek.com/)
-   [`wikipedia`](https://en.wikipedia.org/), [`wolframalpha`](https://www.wolframalpha.com/), [`stackoverflow`](https://stackoverflow.com/), [`github`](https://github.com/), [`reddit`](https://www.reddit.com/), [`youtube`](https://youtube.com/), [`bbc`](https://www.bbc.co.uk/)

### Using Custom Search Engine[#](https://dashy.to/docs/#using-custom-search-engine "Direct link to heading")

You can also use a custom search engine, that isn't included in the above list (like a self-hosted instance of [Whoogle](https://github.com/benbusby/whoogle-search) or [Searx](https://searx.github.io/searx/)). Set `searchEngine: custom`, and then specify the URL (plus query params) to you're search engine under `customSearchEngine`.

For example:

```
appConfig:  webSearch:    searchEngine: custom    customSearchEngine: 'https://searx.local/search?q='
```

### Setting Opening Method[#](https://dashy.to/docs/#setting-opening-method "Direct link to heading")

In a similar way to opening apps, you can specify where you would like search results to be opened. This is done under the `openingMethod` attribute, and can be set to either `newtab`, `sametab` or `workspace`. By default results are opened in a new tab.

### Using Bangs[#](https://dashy.to/docs/#using-bangs "Direct link to heading")

An insanely useful feature of DDG is [Bangs](https://duckduckgo.com/bang), where you type a specific character combination at the start of your search query, and it will be redirected the that website, such as '!w Docker' will display the Docker wikipedia page. Dashy has a similar feature, enabling you to define your own custom bangs to redirect search results to a specific app, website or search engine.

This is done under the `searchBangs` property, with a list of key value pairs. The key is what you will type, and the value is the destination, either as an identifier or a URL with query parameters.

For example:

```
appConfig:  webSearch:    searchEngine: 'duckduckgo'    openingMethod: 'newtab'    searchBangs:      /r: reddit      /w: wikipedia      /s: https://whoogle.local/search?q=      /a: https://www.amazon.co.uk/s?k=      ':wolf': wolframalpha      ':so': stackoverflow      ':git': github
```

Note that bangs begging with `!` or `:` must be surrounded them in quotes

### Disabling Web Search[#](https://dashy.to/docs/#disabling-web-search "Direct link to heading")

Web search can be disabled, by setting `disableWebSearch`, for example:

```
appConfig:  webSearch: { disableWebSearch: true }
```

## Clearing Search[#](https://dashy.to/docs/#clearing-search "Direct link to heading")

You can clear your search term at any time, resting the UI to it's initial state, by pressing Esc. This can also be used to close any open pop-up modals.
