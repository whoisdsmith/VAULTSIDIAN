---
created: 2022-08-09T17:00:19 (UTC -04:00)
tags: []
source: https://dashy.to/docs/
author: 
---

# Icons | Dashy

---
Both sections and items can have an icon, which is specified using the `icon` attribute. Using icons improves the aesthetics of your UI and makes the app more intuitive to use. Dashy supports multiple different icon providers, usage instructions for which are explained here.

-   [Auto-Fetched Favicons](https://dashy.to/docs/#favicons)
-   [Font Awesome Icons](https://dashy.to/docs/#font-awesome)
-   [Simple Icons](https://dashy.to/docs/#simple-icons)
-   [Generative Icons](https://dashy.to/docs/#generative-icons)
-   [Emoji Icons](https://dashy.to/docs/#emoji-icons)
-   [Home-Lab Icons](https://dashy.to/docs/#home-lab-icons)
-   [Material Icons](https://dashy.to/docs/#material-design-icons)
-   [Icons by URL](https://dashy.to/docs/#icons-by-url)
-   [Local Icons](https://dashy.to/docs/#local-icons)
-   [No Icon](https://dashy.to/docs/#no-icon)

![](https://i.ibb.co/GTVmZnc/dashy-example-icons.png)

___

## Favicons[#](https://dashy.to/docs/#favicons "Direct link to heading")

Dashy can auto-fetch an icon for a given service, using it's favicon. Just set `icon: favicon` to use this feature.

![](https://i.ibb.co/k6wyhnB/favicon-icons.png)

Since different websites host their favicons at different paths, for the best results Dashy can use an API to resolve a websites icon.

The default favicon API is [allesedv.com](https://favicon.allesedv.com/), but you can change this under `appConfig.faviconApi`. If you'd prefer not to use an API, just set this value to `local`. You can also use different APIs for individual items, by setting `icon: favicon-[api]`, e.g. `favicon-clearbit`.

The following favicon APIs are supported:

-   `allesedv` - [allesedv.com](https://favicon.allesedv.com/) is a highly efficient IPv6-enabled service
-   `iconhorse` - [Icon.Horse](https://icon.horse/) returns quality icons for any site, with caching for speed and fallbacks for sites without an icon
-   `clearbit` - [Clearbit](https://clearbit.com/logo) returns high-quality square logos from mainstream websites
-   `faviconkit` - [faviconkit.com](https://faviconkit.com/) good quality icons and most sites supported (Note: down as of Nov '21)
-   `besticon` - [BestIcon](https://github.com/mat/besticon) fetches websites icons from manifest
-   `mcapi` - [MC-API](https://eu.mc-api.net/) fetches default website favicon, originally a Minecraft util
-   `duckduckgo` - Returns decent quality website icons, from DuckDuckGo search
-   `google` - Official Google favicon API service, good support for all sites, but poor quality
-   `yandex` - Lower quality icons, but useful in some regions where other services are blocked
-   `local` - Set to local to fetch the default icon at /favicon.ico instead of using an API

If for a given service none of the APIs work in your situation, and nor does local, then the best option is to find the path of the services logo or favicon, and set the icon to the URL of the raw image. For example, `icon: https://monitoring.local/faviconx128.png`- you can find this path using the browser dev tools.

___

## Font Awesome[#](https://dashy.to/docs/#font-awesome "Direct link to heading")

You can use any [Font Awesome Icon](https://fontawesome.com/icons) simply by specifying it's identifier. This is in the format of `[category] [name]` and can be found on the page for that icon on the Font Awesome site. For example: `fas fa-rocket`, `fab fa-monero` or `fas fa-unicorn`.

Font-Awesome has a wide variety of free icons, but you can also use their pro icons if you have a membership. To do so, you need to specify your license key under: `appConfig.fontAwesomeKey`. This is usually a 10-digit string, for example `13014ae648`.

![](https://i.ibb.co/tMtwNYZ/fontawesome-icons3.png)

___

## Simple Icons[#](https://dashy.to/docs/#simple-icons "Direct link to heading")

[SimpleIcons.org](https://simpleicons.org/) is a collection of 2000+ high quality, free and open source brand and logo SVG icons. Usage of which is very similar to font-awesome icons. First find the glyph you want to use on the [website](https://simpleicons.org/), then just set your icon the the simple icon slug, prefixed with `si-`.

![](https://i.ibb.co/MVhkXfC/simple-icons-example.png)

For example:

```
sections:- name: Simple Icons Example  items:  - title: Portainer    icon: si-portainer  - title: FreeNAS    icon: si-freenas  - title: NextCloud    icon: si-nextcloud  - title: Home Assistant    icon: si-homeassistant
```

___

## Generative Icons[#](https://dashy.to/docs/#generative-icons "Direct link to heading")

To uses a unique and programmatically generated icon for a given service just set `icon: generative`. This is particularly useful when you have a lot of similar services with a different IP or port, and no specific icon. These icons are generated with [DiceBear](https://avatars.dicebear.com/) (or [Evatar](https://evatar.io/) for fallback), and use a hash of the services domain/ ip for entropy, so each domain will have a unique icon.

![](https://i.ibb.co/b2pC2CL/generative-icons-2.png)

___

## Emoji Icons[#](https://dashy.to/docs/#emoji-icons "Direct link to heading")

You can use almost any emoji as an icon for items or sections. You can specify the emoji either by pasting it directly, using it's unicode ( e.g. `'U+1F680'`) or shortcode (e.g. `':rocket:'`). You can find these codes for any emoji using [Emojipedia](https://emojipedia.org/) (near the bottom of emoji each page), or for a quick reference to emoji shortcodes, check out [emojis.ninja](https://emojis.ninja/) by @nomanoff.

![](https://i.ibb.co/YLwgTf9/emoji-icons-1.png)

For example, these will all render the same rocket (🚀) emoji: `icon: ':rocket:'` or `icon: 'U+1F680'` or `icon: 🚀`

___

## Home-Lab Icons[#](https://dashy.to/docs/#home-lab-icons "Direct link to heading")

The [dashboard-icons](https://github.com/WalkxHub/dashboard-icons) repo by [@WalkxCode](https://github.com/WalkxCode) provides a comprehensive collection of 360+ high-quality PNG icons for commonly self-hosted services. Dashy natively supports these icons, and you can use them just by specifying the icon name (without extension) preceded by `hl-`. See [here](https://github.com/WalkxCode/dashboard-icons/tree/master/png) for a full list of all available icons. Note that these are fetched and cached strait from GitHub, so if you require offline access, the [Local Icons](https://dashy.to/docs/#local-icons) method may be a better option for you.

For example:

```
sections:- name: Home Lab Icons Example  items:  - title: AdGuard Home    icon: hl-adguardhome  - title: Long Horn    icon: hl-longhorn  - title: Nagios    icon: hl-nagios  - title: Whoogle Search    icon: hl-whooglesearch
```

![](https://i.ibb.co/PQzYHmD/homelab-icons-2.png)

___

## Material Design Icons[#](https://dashy.to/docs/#material-design-icons "Direct link to heading")

Dashy also supports 5000+ [material-design-icons](https://github.com/Templarian/MaterialDesign). To use these, first find the name/ slug for your icon [here](https://dev.materialdesignicons.com/icons), and then prefix is with `mdi-`.

For example:

```
sections:- name: Material Design Icons Example  items:  - title: Alien Icon    icon: mdi-alien   - title: Fire Icon    icon: mdi-fire   - title: Dino Icon    icon: mdi-google-downasaur 
```

![](https://i.ibb.co/fC9B4mq/icons-mdi-example.png)

___

## Icons by URL[#](https://dashy.to/docs/#icons-by-url "Direct link to heading")

You can also set an icon by passing in a valid URL pointing to the icons location. For example `icon: https://i.ibb.co/710B3Yc/space-invader-x256.png`, this can be in .png, .jpg or .svg format, and hosted anywhere (local or remote) - so long as it's accessible from where you are hosting Dashy. The icon will be automatically scaled to fit, however loading in a lot of large icons may have a negative impact on performance, especially if you visit Dashy from new devices often.

___

## Local Icons[#](https://dashy.to/docs/#local-icons "Direct link to heading")

You may also want to store your icons locally, bundled within Dashy so that there is no reliance on outside services. This can be done by putting the icons within Dashy's `./public/item-icons/` directory. If you are using Docker, then the easiest option is to map a volume from your host system, for example: `-v /local/image/directory:/app/public/item-icons/`. To reference an icon stored locally, just specify it's name and extension. For example, if my icon was stored in `/app/public/item-icons/maltrail.png`, then I would just set `icon: maltrail.png`.

You can also use sub-folders within the `item-icons` directory to keep things organized. You would then specify an icon with it's folder name slash image name. For example: `networking/monit.png`

___

## No Icon[#](https://dashy.to/docs/#no-icon "Direct link to heading")

If you don't wish for a given item or section to have an icon, just leave out the `icon` attribute.

___

## Icon Collections and Resources[#](https://dashy.to/docs/#icon-collections-and-resources "Direct link to heading")

The following websites provide good-quality, free icon sets. To use any of these icons, either copy the link to the raw icon (it should end in `.svg` or `.png`) and paste it as your `icon`, or download and save the icons in `/public/item-icons` / mapped Docker volume. Full credit to the authors, please see the licenses for each service for usage and copyright information.

-   [Icons for Self-Hosted Apps](https://thehomelab.wiki/books/helpful-tools-resources/page/icons-for-self-hosted-dashboards) - 350+ high-quality icons for commonly self-hosted services
-   [SVG Box](https://svgbox.net/iconsets/) - Cryptocurrency, social media apps and flag icons
-   [Simple Icons](https://simpleicons.org/) - Free SVG brand icons, with easy API access
-   [Material Design Icons](https://github.com/google/material-design-icons/) - Hundreds of Open source PNG + SVG icons by Google
-   [Icons8](https://icons8.com/icons) - Thousands of icons, all with free versions at 64x64
-   [Flat Icon](https://www.flaticon.com/) - Wide variety of icon sets, most of which are free to use
-   [SVG Repo](https://www.svgrepo.com/) - 300,000+ Vector Icons

If you are a student, then you can get free access to premium icons on [Icon Scout](https://education.github.com/pack/redeem/iconscout-student) or [Icons8](https://icons8.com/github-students) using the [GitHub Student Pack](https://education.github.com/pack).

___

## Notes[#](https://dashy.to/docs/#notes "Direct link to heading")

If you are using icons from an external source, these will be fetched on initial page load automatically, if and when needed. But combining icons from multiple services may have a negative impact on performance.

You can improve load speeds, by downloading your required icons, and serving them locally. Scaling icons to the minimum required dimensions (e.g. 128x128 or 64x64) will also greatly improve application load times.

For icons from external sources, please see the Privacy Policies and Licenses for that provider.
