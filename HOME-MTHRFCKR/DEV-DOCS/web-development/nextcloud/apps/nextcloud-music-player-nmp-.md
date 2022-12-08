---
tags:: apps
---
# nextcloud-music-player (nmp)

**Caution:** THIS IS A WORK IN PROGRESS

Nextcloud music player aims to be a simple but full featured audio player application that fetches all its music from a nextcloud instance.

It's built with React native and will be available on iOS as well as Android platforms.

## Current state

Currently only a 'login' page is available, which allow to successfully login to a nextcloud instance using  the OAuth2 authentication protocol.

## Motivations

Like many people, I love listening to music, which I do almost all day.

However, I was often listening to music on YouTube, which:

- Consumes a lot of internet data
- Exposes the user to the nasty and mind-narrowing YouTube algorithm
- Is definitely overkill given that I only want to listen to music in most situations, not playing music videos

For these reasons among many others and because I recently discovered and setup my own nextcloud instance, I wanted to have some native music player I'd be able to use to listen to the music stored on my nextcloud.

Unfortunately, the best and free solution I found was to use the nextcloud's web interface, which can pass any audio stream to the native iOS music player. While it worked, it was not handy at all: I wanted something simple, so simple that going to YouTube instead would never become a viable alternative.

That's why I decided to build this app!