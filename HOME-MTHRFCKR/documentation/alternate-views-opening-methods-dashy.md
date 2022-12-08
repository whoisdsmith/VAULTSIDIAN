---
created: 2022-08-09T17:02:33 (UTC -04:00)
tags: []
source: https://dashy.to/docs/
author: 
---

# Alternate Views & Opening Methods | Dashy

---
## Views[#](https://dashy.to/docs/#views "Direct link to heading")

Dashy has three different views:

-   Default View - This is the main homepage with sections in a grid layout
-   Workspace View - Items displayed on the side, and are launched within Dashy
-   Minimal View - A clean + simple tabbed view

You can switch between views using the dropdown in the top-right corner. Set your chosen Starting View with `appConfig.startingView`. Click the page title at any time to go back to your selected starting view.

### Default[#](https://dashy.to/docs/#default "Direct link to heading")

This is the main page that you will land on when you first launch the application. Here all of your sections (with items + widgets) are visible in a grid layout.

**Example of Default View**  
![Demo](https://i.ibb.co/L8YbNNc/dashy-demo2.gif)

### Workspace[#](https://dashy.to/docs/#workspace "Direct link to heading")

The workspace view displays your links in a sidebar on the left-hand side, and apps are launched inside an iframe without having to leave Dashy. This enables you to use all of your self-hosted apps from one place, and makes multi-tasking easy.

You can specify a default app to be opened when you land on the workspace, by setting `appConfig.workspaceLandingUrl: https://app-to-open/`. If this app exists within your sections.items, then the corresponding section will also be expanded.

You can also opt to keep previously opened websites/ apps open in the background, by setting `appConfig.enableMultiTasking: true`. This comes at the cost of performance, but does mean that your session with each app is preserved, enabling you to quickly switch between them.

**Example of Workspace View**  
![Workspace view demo](https://raw.githubusercontent.com/Lissy93/dashy/master/docs/assets/workspace-demo.gif)

### Minimal View[#](https://dashy.to/docs/#minimal-view "Direct link to heading")

The minimal view aims to be super fast and simple, and can be used as a browser startpage. Items are grouped into a tab view, and the last opened tab will be remembered. Similar to the main view, you can search and launch items just by typing, and right-clicking will show more options (like open in modal, workspace or new tab).

**Example of Minimal View**  
![Workspace view demo](https://raw.githubusercontent.com/Lissy93/dashy/master/docs/assets/minimal-view-demo.gif)

## Opening Methods[#](https://dashy.to/docs/#opening-methods "Direct link to heading")

Dashy supports several different ways to launch your apps. The primary opening method for each app can be specified using the `target` attribute, with a value of one of the following:

-   `sametab` - The app will be launched in the current tab
-   `newtab` - The app will be launched in a new tab
-   `top` - Opens in the top-most browsing context, useful if your accessing Dashy through an iframe
-   `modal` - Launch app in a resizable/ movable popup modal on the current page
-   `workspace` - Changes to Workspace view, and launches app

You can also set a default opening method, which will be applied to all items that don't have a specified target, using `appConfig.defaultOpeningMethod`, to one of the above values.

Even if the target is not set (or is set to `sametab`), you can still launch any given app in an alternative method. Either right-click to see all options, or use one of the keyboard shortcuts: Alt + Click will open the modal, and Ctrl + Click will open in a new tab.

![](https://i.ibb.co/vmZdSRt/dashy-context-menu-2.png)

If you don't like the custom context menu, it can be disabled by setting `appConfig.disableContextMenu: true`.

If you get a 'Refused to Connect' error in the modal or workspace views, then the target app has it's X-Frame-Options HTTP set to block requests from embedded content. You can easily fix this by setting this header to ALLOW, for instructions on how to do so, see the [Troubleshooting Docs](https://dashy.to/docs/troubleshooting#refused-to-connect-in-modal-or-workspace-view).
