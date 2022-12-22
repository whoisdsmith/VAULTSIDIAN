# Backups

---

The bookmarks and files you save to your Raindrop.io are stored on Raindrop.io's servers. In other words, they’re stored "in the cloud”.

This means that your collection will be available on any computer or mobile device (phone or tablet) that is connected to your Raindrop.io account.

<details><summary>  

## Automatic / Manual Backups {#automatic}

</summary>

Never worry about losing your collections, bookmarks, tags and highlights.

Anytime you can create a new backup and store up to 30 last on your account.
If you’re a [Pro user](premium-features.md), Raindrop creates backup files for you automatically.

You can easily [restore data](home-mthrfckr/dev-docs/raindrop-io/help-docs/import.md).

:::note
[Automatic backups](https://app.raindrop.io/settings/backups) are created once a day on days you made any changes.
:::

In addition you can enable backups to your `Dropbox` and `Google Drive` account:

1. Visit [settings page](https://app.raindrop.io/settings/backups)
2. Turn on/off particular account in `Cloud backup` section
3. Shortly after first backup will be made

### Backup to Dropbox

You can find your backup in `/Apps/Raindrop.io` folder

### Backup to Google Drive

Backup will be saved to `Raindrop.io-Export.html` and `Raindrop.io-Export.csv` file

</details>

<details><summary>

## Permanent Library {#permanent-library}

</summary>

Raindrop.io automatically creates copies of all web-pages and files in your collection. That way, even if an item changes or is taken offline, you will be able to open the version that you have saved in Raindrop.io.

![](using/backups/copy.jpg)

:::info
Only available in [Pro plan](premium-features.md)
:::

Web-pages are saved entirely with styles, fonts and images.
Permanent copy is fully portable (single file), static and doesn't have any external data source dependencies or scripts. All ads and tracking scripts are stripped away!

Content of web-pages and PDF's is fully searchable as described in [full-text search documentation](HOME-MTHRFCKR/DEV-DOCS/raindrop-io/help-docs/search.md).

Space for your copies is unlimited. Link to your copy is private and can't be made public.
When PRO subscription is expired, permanent copies become unaccessible and could be removed in future.

### How long it takes to copy all of my bookmarks?

It's depends on count of your bookmarks and global queue. Usually 1000 bookmarks will be copied in half an hour. If it takes a lot longer, <a onClick={()=>Beacon('open')} target="_self">let us know</a>.
:::note
Be sure that after upgrade to PRO, copies will not appear immediately. We need some time to copy each of your bookmarks, as described above.
:::

### How to access permanent copy? {#open-permanent-copy}

:::note Web app, desktop app or browser extension
Right click on a bookmark and select "Open permanent copy"
:::

:::note Mobile app
Tap "..." next to bookmark, then tap "Open permanent copy"
:::

### How to download a permanent copy?

[Open permanent copy](#open-permanent-copy), then click `Download` and follow the intructions

### Limitations

Some bookmarks or files can't be saved by several reasons described below.
When this happen you will see a special icon <img src={require('./icon.png').default} style={{maxHeight:20}} />

#### Known limitations

- Bookmarks in "Trash" are ignored and not saved
- Some websites block automated bots, we can't save such webpages yet
- Maximum size of entire web-page/file is limited by 70 Mb
- Video, audio and iframes included in web-page could not be saved
- Web-pages with fancy animations based on scroll position could not be saved correctly
- Links that require login or not publicly accessible could not be saved
- Small amount can't be saved due to script failure, those will be automatically retried
- If you found bookmark that marked as "failed to copy" by mistake, <a onClick={()=>Beacon('open')} target="_self">please send</a> this link

</details>

<details><summary>

## Export to File

</summary>

Because your data is stored in the cloud, you do not need to create any special backups of your saved Raindrop.io items.
However, If you wish to download your bookmarks for other uses you can use our export tool which creates a downloadable `HTML` & `CSV` file.

To access our export tool, visit [settings page](https://app.raindrop.io/settings/backups) and click **Create new**.
You will receive an email shortly.

`HTML` & `CSV` file will contain: Collections, Links, Tags & Highlights

</details>
