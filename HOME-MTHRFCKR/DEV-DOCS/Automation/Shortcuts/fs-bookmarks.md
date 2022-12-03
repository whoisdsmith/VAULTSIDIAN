#webclip

# 2022-02-26

- [FS Bookmarks: A Shortcut to Reopen Files and Folders Directly in the Files App](https://www.macstories.net/ios/fs-bookmarks-a-shortcut-to-reopen-files-and-folders-directly-in-the-files-app/)
	- author: By Federico Viticci

---

![](https://cdn.macstories.net/2019-10-31-18-02-42-1637680114324.png)

The Shortcuts Corner is a regular section of our MacStories Weekly newsletter, exclusive to [Club MacStories members](https://club.macstories.net/?utm_source=ms&utm_medium=ShortcutsCornerSite), where I share advanced shortcuts and respond to readers’ requests for automation. In this post, you’ll find some free shortcuts and a preview of an exclusive one available with a [Club MacStories](https://club.macstories.net/?utm_source=ms&utm_medium=ShortcutsCornerSite) subscription.

A couple weeks ago on our iPad-focused podcast Adapt, [Ryan challenged me](https://www.relay.fm/adapt/11) to figure out a way to turn the iPad’s Home screen into a desktop-like environment with icons to reopen files and folders directly in the Files app. At first, I thought it couldn’t be done: unlike the Mac’s Finder, Files doesn’t let you create [aliases](https://en.m.wikipedia.org/wiki/Alias_\(Mac_OS\)) to folders or place files on the Home screen; the Shortcuts app can create [Home screen icons](https://www.macstories.net/news/introducing-macstories-shortcuts-icons-300-custom-home-screen-icons-for-your-shortcuts/), but it doesn’t have access to documents located outside Shortcuts’ iCloud Drive container.

As I detailed [on Adapt yesterday](https://www.relay.fm/adapt/12), I’m happy to introduce **FS Bookmarks**, a shortcut that lets you create **direct launchers for files and folders stored in the Files app**. FS Bookmarks is a hybrid Shortcuts-[Scriptable](https://itunes.apple.com/us/app/id1405459188?at=10l6nh&ct=ms_inline) tool that takes advantage of a native Files API (which I will call “[bookmarks](https://www.macstories.net/stories/beyond-the-tablet/3/#open-in-place-and-file-bookmarks)”) to expose the filesystem path of any file or folder stored in the Files app.

With the launchers created via FS Bookmarks, you’ll be able to reopen any _document_ in the Files app (in Quick Look preview mode) or navigate to any _folder_ you want to quickly access. Best of all, you don’t need to know or even see Scriptable’s JavaScript code at all: FS Bookmarks takes care of installing the necessary scripts for you; you just need to pick the files and folders you want to create launchers for, and that’s it. FS Bookmarks was designed to abstract the complexity involved with retrieving the filesystem paths used by the Files app.

Creating a folder launcher with FS Bookmarks, which can be run from the Home screen.Replay

In addition to serving as a response to Ryan’s challenge, FS Bookmarks provides a solution to a longstanding problem of the iPad Home screen: the inability to turn it into a Mac-like environment with shortcuts to **frequently used files and folders**. There are some fascinating technical details involved with the creation of FS Bookmarks and how it all works behind the scenes that I’d like to explain, so let’s dig in.

## Behind the Scenes: FileSystem Paths and the Files App

At a high level, FS Bookmarks was made possible by a recent discovery: if you combine the base URL scheme of the Files app with the native filesystem path of a file or folder, you’ll be able to reopen that item directly in the Files app.

Here’s how it works: under the hood on both iOS and iPadOS, files and folders stored in the Files app have paths such as this one:

`/private/var/mobile/Library/Mobile Documents/27N4MQEA55~pro~writer/Documents/Image Assets`

That’s one ugly file path, but it’s how the [system](https://www.theiphonewiki.com/wiki//private/var/mobile/Library) points to an app’s folder. In this case, the file path above is pointing to a folder called ‘Image Assets’ located under iCloud Drive/iA Writer. Similarly, a PDF document named ‘Expenses.pdf’ stored in your iCloud Drive Downloads folder should have this kind of filesystem path:

`/private/var/mobile/Library/Mobile Documents/com~apple~CloudDocs/Downloads/Expenses.pdf`

By themselves, these paths are useless as you cannot launch them in any way. However, I’ve recently discovered that if you combine the Files app’s `shareddocuments://` URL scheme with an encoded version of the filesystem path, the file or folder can be reopened directly in the Files app. The launcher URL looks something like this:

`shareddocuments:///private/var/mobile/Library/Mobile%20Documents/com~apple~CloudDocs/Downloads/Expenses.pdf`

This is interesting and all, but there were at least two problems: Shortcuts cannot fetch filesystem paths for files and folders by itself; perhaps most importantly, I didn’t want anyone to have to edit these URL schemes by hand.

The first problem could be easily solved: as [I explained back in May](https://www.macstories.net/stories/beyond-the-tablet/9/#file-bookmarks), Scriptable can fetch the native filesystem paths of files and folders using the native bookmarks API. Getting the unique path of a document or folder is a simple matter of bookmarking it in Scriptable first, then running a script to retrieve its path.

The real challenge was that I didn’t want anyone to worry about this stuff – installing scripts, programming them, and switching back and forth between Scriptable and Shortcuts. So I created the FS Bookmarks shortcut as an end-to-end solution that abstracts as much complexity from the experience as possible, allowing you to create file and folder launchers in just a couple of taps, without having to know _anything_ about how it all works behind the scenes.

## The Shortcut: FS Bookmarks

The first time you run FS Bookmarks, you’ll be presented with a guided setup process that installs two scripts in the Scriptable app for you. Once again, the Scriptable app is necessary to create file and folder bookmarks – a native Files functionality that, for some reason, Apple is still not using in Shortcuts. The two scripts (one to create new file bookmarks, the other to retrieve existing bookmarks) will run natively in Shortcuts thanks to parameters in iOS 13.

![FS Bookmarks' guided setup process can install scripts in Scriptable for you.](https://cdn.macstories.net/2019-10-31-17-29-44-1637680116502.jpeg)

FS Bookmarks’ guided setup process can install scripts in Scriptable for you.

Unlike other shortcuts you may have seen that integrate with Scriptable, FS Bookmarks can install scripts in the app for you – no need to download them manually. During the setup process, FS Bookmarks will provide you with step-by-step instructions: as long as you have the Scriptable app installed, it’ll take you 30 seconds to complete the setup, which you only need to do once. After that, FS Bookmarks will be ready to use.

FS Bookmarks can perform two types of tasks: it can either **create a new file bookmark** without opening Scriptable, or it can **retrieve the filesystem path of any bookmark** you previously created in Scriptable. Unfortunately, due to a limitation of the Shortcuts app, FS Bookmarks cannot create new folder bookmarks – you’ll have to create those in the Scriptable app.

So let’s go over the typical creation flow of a new bookmark. For files, all you need to do is run FS Bookmarks, select ‘Create New File Bookmark’ and pick a file from the Files picker. You can pick any file from any file provider of the Files app – iCloud Drive, local storage, and third-party file providers are all supported. Once a file has been selected, wait a few seconds for the bookmark to be created in the background by Scriptable, and you’ll have the filesystem path to the file in your clipboard, ready to be used in a new launcher. The resulting URL is a persistent link that points directly to a file stored in the Files app.

![Creating a new file bookmark and retrieving its path with FS Bookmarks.](https://cdn.macstories.net/2019-10-31-17-32-41-1637680119126.png)

Creating a new file bookmark and retrieving its path with FS Bookmarks.

The process is a bit different if you want to create new bookmarks for _folders_. To do so, you have to use Scriptable – Shortcuts doesn’t offer a ‘Get Folder’ action yet. Creating folder bookmarks in Scriptable is extremely easy:

  * Open the in-app settings in Scriptable;
  * Select File Bookmarks;
  * Hit the + button and select ‘Pick Folder’;
  * Pick a folder from Files and save it as a bookmark.
![Creating new bookmarks in Scriptable.](https://cdn.macstories.net/2019-10-31-17-36-20-1637680121754.png)

Creating new bookmarks in Scriptable.

You can repeat these steps to create new bookmarks for any file or folder inside Scriptable. As far as FS Bookmarks is concerned, there is no functional difference between creating a file bookmark from Shortcuts or Scriptable: both methods give you the filesystem path at the end, which is all you need.

A note on picking folders in Scriptable: you can pick any folder of any modern file provider of the Files app – where by “modern” I mean file providers that support the open-in-place Files APIs introduced with iOS 11 in 2017. I tested folder bookmarks with file providers such as [Working Copy](https://itunes.apple.com/us/app/id896694807?at=10l6nh&ct=ms_inline) and [Secure ShellFish](https://itunes.apple.com/us/app/id1336634154?at=10l6nh&ct=ms_inline), and they worked great. Unfortunately, Dropbox is among the companies shipping file providers that still do not support the open-in-place technology of the Files app for folders.1

Once you’ve created file/folder bookmarks in Scriptable, run FS Bookmarks and select ‘Get Existing File or Folder Bookmark’. Enter the exact name of your bookmark, wait a couple seconds for Shortcuts to launch Scriptable and come back2, and you’ll have a path to a bookmark in your clipboard, ready to be used.

![Retrieving existing bookmarks for files or folders with FS Bookmarks.](https://cdn.macstories.net/2019-10-31-17-39-03-1637680124299.png)

Retrieving existing bookmarks for files or folders with FS Bookmarks.

Whether you create a new file bookmark from Shortcuts or retrieve an existing bookmark from Scriptable, FS Bookmarks always ends the same way – with an alert informing you that the filesystem path has been generated, and that a launcher is ready to be created.

![At the end, FS Bookmarks will give you a file/folder launcher you can use in a shortcut.](https://cdn.macstories.net/2019-10-31-17-41-27-1637680127219.png)

At the end, FS Bookmarks will give you a file/folder launcher you can use in a shortcut.

At this point, you have two options: if you’re a [Club MacStories member](https://club.macstories.net/?utm_source=ms&utm_medium=ShortcutsCornerSite), you can let FS Bookmarks run SLC (it stands for “Shortcuts Launcher Creator”), an advanced shortcut I shared in today’s issue of MacStories Weekly. SLC is a **shortcut that creates new shortcuts** on your behalf: in this case, SLC will create a new shortcut in your library with the filesystem path already filled-in. You can take a look at the process in action in the video below:

With SLC, a new shortcut launcher will be created for you with the necessary URL already filled in.Replay

SLC is based on an advanced technique that creates new shortcuts programmatically – all you need to do is install them. SLC can create launchers for all kinds of URLs, including Safari webpages, Apple Music content, and arbitrary URL schemes. You can read more details and download SLC in [Issue 198 of MacStories Weekly](https://club.macstories.net/?utm_source=ms&utm_medium=ShortcutsCornerSite).

If you don’t want to use SLC, you can turn the filesystem path into a shortcut launcher manually. When FS Bookmarks finishes running, create a new shortcut, drag in the ‘Open URLs’ action, and paste the URL generated by FS Bookmarks. With this shortcut, you’ll be able to launch the previously-bookmarked file or folder directly in the Files app.

![Using a filesystem path in a launcher requires a single 'Open URLs' action.](https://cdn.macstories.net/2019-10-31-17-44-09-1637680129351.jpeg)

Using a filesystem path in a launcher requires a single ‘Open URLs’ action.

* * *

I’ve always wanted to be able to save frequently used iCloud Drive files and folders to my iPhone and iPad Home screens. With FS Bookmarks, I finally have a solution that’s fast, reliable, and easy enough to set up. In my tests, iCloud Drive-based launchers have always kept working across iOS/iPadOS updates and device reboots. Using [MacStories Shortcuts Icons](https://www.macstories.net/pixel/shortcuts/), I’ve added a handful of folders and files to my iPad Home screen, which now looks like this:

![You can see file and folder launchers in my widgets and in the bottom-right corner of the Home screen's page.](https://cdn.macstories.net/2019-10-31-17-55-49-1637680131975.png)

You can see file and folder launchers in my widgets and in the bottom-right corner of the Home screen’s page.

The best part: as someone who’s been increasingly moving away from Dropbox, FS Bookmarks has given me another incentive to store my most used files and folders in iCloud Drive. I particularly appreciate the fact that files open directly in Quick Look, which is great to preview their contents or simply share them with the share sheet. Folder launchers have proven useful too: I like to organize my work-related documents in sub-folders; with FS Bookmarks, I no longer have to manually (and slowly) navigate the hierarchical folder structure of the Files app to reach a sub-folder nested multiple levels deep into Files.

Furthermore, FS Bookmarks-based launchers work both as Home screen icons and from the Shortcuts widget, giving you even more options to open your favorite files and folders from the Home screen. When activated from the widget, these launchers don’t even need to briefly open Shortcuts before jumping to the Files app. You can take a look at the experience of launching files and folders from the Home screen in the video below:

Launching files and folders as Home screen icons and from the Shortcuts widget.Replay

Ideally, I shouldn’t have to pin files and folders to my Home screen using a shortcut and raw filesystem paths. This should be a native feature of the Files app, which I hope Apple will consider. But until that happens, I wanted to come up with a workaround that would allow me to speed up file management on my iPhone and iPad Home screens, and I believe I’ve landed on a pretty solid implementation with FS Bookmarks.

You can download FS Bookmarks below or find it in the [MacStories Shortcuts Archive](https://www.macstories.net/shortcuts/).

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2018-11-10-14-42-06.png)

### FS Bookmarks

Create bookmarks for files and folders stored in iCloud Drive (and third-party file providers) that you can reuse as direct launchers. FS Bookmarks requires Scriptable, and it generates launchers that reopen files and folders directly in the Files app.

[Get the shortcut here.](https://www.icloud.com/shortcuts/e2781a86881b44ffb298924ceb9f0927)

* * *

  1. You can at least create bookmarks for Dropbox files, which will open in Quick Look. ↩︎
  2. Switching between apps is necessary because current iOS API limitations prevent Shortcuts from accessing Scriptable bookmarks in the background. ↩︎
