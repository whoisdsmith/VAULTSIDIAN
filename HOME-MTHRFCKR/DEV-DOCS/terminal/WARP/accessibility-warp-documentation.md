---
created: 2022-07-16T16:04:14 (UTC -04:00)
tags: []
source: https://docs.warp.dev/features/integrations-and-plugins
author: 
---

# Accessibility - Warp Documentation

> ## Excerpt
> Our mission is to make Warp the most accessible terminal for all developers. It includes fixing the UI, making it easier to use for both experts and new engineers who are just starting to use the command line tools. We also recognize the need to improve the experience for those visually impaiared, as - to our best knowledge - other terminal emulator apps didn't really do a good job in this area. This doc summarizes what we've done so far, how does Warp work with Voice Over and outlines the main changes from the typical workflow. For the features documentation and its keyboard shortcuts, please go to the feature-specific page in the documentation.

---
Our mission is to make Warp the most accessible terminal for all developers. It includes fixing the UI, making it easier to use for both experts and new engineers who are just starting to use the command line tools. We also recognize the need to improve the experience for those visually impaiared, as - to our best knowledge - other terminal emulator apps didn't really do a good job in this area. This doc summarizes what we've done so far, how does Warp work with Voice Over and outlines the main changes from the typical workflow. For the features documentation and its keyboard shortcuts, please go to the feature-specific page in the documentation.

**Keep in mind that this is a work-in-progress and the current state is not a final state of accessibility in Warp**.

## 

How to use Warp with Voice Over?

Best way to start working with Warp & VoiceOver is to install it using brew:

This will ensure that you can receive all the future updates automatically, without the need to go through a MacOS standard drag&drop installation process.

From there, Warp should seamlessly work with Voice Over and start announcing what's happening on the screen and what are the actions you can take. This may be a major difference from other apps - as Warp announces stuff on its own, letting you know what's going on. There's currently no way to navigate between different UI elements using VO key combinations.

Once installed, it will ask you to log in. We require the log in during our Beta state. Note that during the Beta as of now, Warp also sends telemetry that we use to improve the overall user experience. You can find out more about that in the [privacy section](https://github.com/warpdotdev/docs/blob/main/features/getting-started/privacy.md).

The log in flow will require you to navigate between the app and your browser. Last step before you can start enjoying our new terminal app is filling up the onboarding survey.

The main terminal window is not that different from other terminals - there's a place to type commands (Command Input) and the list of the previously executed commands and their outputs. Warp groups those together - each command and output create a Block. You can navigate blocks with your keyboard to easily check what was the command, learn whether it was successful or not, and what was the output, as well as more easily copy the command, output, or both for further processing.

A main entry point for discovering new features and actions is our Command Palette, which you can access by executing the cmd-p shortcut.

## 

Differences from the regular Voice Over workflow

As you may notice, typical Voice Over navigation keys or settings do not currently work in Warp. In short - it's related to how our UI Framework is currently implemented and that as of now we don't yet offer a keyboard accessible way to navigate the UI elements.

Instead, whenever you perform an action and/or something happens in the background, Warp announces it to you, letting you know what's going on and what are possible actions you can take. Since it's a terminal, we care about all user actions being keyboard accessible from the start, so pretty much all our features have the assigned keybindings already. You can adjust the default keybindings following the guide from this github repository: [https://github.com/warpdotdev/keysets](https://github.com/warpdotdev/keysets). You can also always fallback to using cmd-p to check the keybinding or execute the specific action.

## 

A11y specific actions

Some a11y-specific settings are available through the command palette. For example, you can adjust the verbosity level of messages. Simply enter the command palette (cmd-p) and type "a11y" to discover related options and their keybindings.

## 

Future work

While not all Warp features are accessible yet, we've implemented a process around releasing new features and changes to the main app, to ensure that all new code provides proper a11y announcements.

This is definitely not the ideal and final implementation. We're happy to hear your thoughts and ideas on how we can improve. The biggest milestone for this work is to add support for navigating the UI elements using the keyboard. Give Warp a try, and please, do not hesitate to share your feedback: you can reach us via [email](mailto:feedback@warp.dev), chat with us on [Discord](https://discord.com/invite/warpdotdev) or file a ticket in our [Github repo](https://github.com/warpdotdev/warp).
