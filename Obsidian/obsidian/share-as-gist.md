---
created: 2022-08-07T22:00:52 (UTC -04:00)
tags: []
source: chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html
author: 
---

# Share as Gist

---
# "Share as Gist" Obsidian plugin

This plugin for Obsidian ([https://obsidian.md](https://obsidian.md)) allows you to share your notes as [GitHub Gists](https://gist.github.com/).

You can share your notes privately (i.e. only people with the link can see the note) or publicly (i.e. the note is visible on your profile).

Once you've create a gist, if you make changes to your note (for example responding to feedback), you can update your existing gist straight from Obsidian.

## [](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#usage)Usage

1.  Install the plugin. (For now, you'll have to add it to your Obsidian vault manually, but it should soon be available in the Community Plugins directory.)
2.  [Create a GitHub personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) with the `gist` scope, and copy it to your clipboard.

[![Screenshot 2022-06-09 at 09 47 43](https://user-images.githubusercontent.com/116134/172805660-4e563a93-a042-4aa7-8b48-db0c501aac14.png)](https://user-images.githubusercontent.com/116134/172805660-4e563a93-a042-4aa7-8b48-db0c501aac14.png)

3.  Open "Settings" in Obsidian, then go to "Share as Gist" under "Plugin Options".

[![Screenshot 2022-07-21 at 09 10 52](https://user-images.githubusercontent.com/116134/180163869-4a072203-00e6-4510-81e8-456dd71c5443.png)](https://user-images.githubusercontent.com/116134/180163869-4a072203-00e6-4510-81e8-456dd71c5443.png)

4.  Paste your access token into the "GitHub.com access token" box, then close "Settings".
    
5.  To share a note, open the Command Palette and type "gist". You'll see commands for creating a public and private link. Pick the one you want and hit enter. Your gist will be created, and the URL for sharing will be added to your clipboard.
    

[![Screenshot 2022-07-21 at 09 12 16](https://user-images.githubusercontent.com/116134/180164154-02817121-e88a-419d-9528-9be58212ed9c.png)](https://user-images.githubusercontent.com/116134/180164154-02817121-e88a-419d-9528-9be58212ed9c.png)

6.  Make a change to your note, and then follow step 5 again. You will be asked if you want to update the existing note or create a new one.

[![Screenshot 2022-06-09 at 09 49 00](https://user-images.githubusercontent.com/116134/172805957-dbbe8223-8056-4685-aad4-4fd54338c85f.png)](https://user-images.githubusercontent.com/116134/172805957-dbbe8223-8056-4685-aad4-4fd54338c85f.png)

To enable existing gists to be updated, by default, extra YAML front matter is added to your notes. You can turn this off by disabling the "Enable updating gists after creation" setting.

By default, any YAML front matter will not be included in your gists when they are shared. You can change that by toggling the "Include front matter in gists" setting.

## [](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#securing-your-github-personal-access-token)Securing your GitHub personal access token

Your GitHub access token will be stored in Obsidian's `localStorage`.

This means that it will not be stored in a file and will not be backed up or synced with the rest of your Vault. But it is theoretically possible for other Obsidian plugins to access it.

For your security, you should make sure that you give your personal access token the lowest possible permissions - just the `gist` scope is enough. This will mean that your token will not have access to your code or other sensitive data.
