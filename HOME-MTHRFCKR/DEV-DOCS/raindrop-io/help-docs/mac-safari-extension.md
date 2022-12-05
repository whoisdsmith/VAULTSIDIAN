---
title: Safari Extension (macOS)
slug: /safari-mac-problems
---

:::caution System requirements
- macOS 10.14 Mojave or newer
- Safari 14 or newer
- [Save to Raindrop.io](https://raindrop.io/r/extension/safari) 5.4.5 or newer
:::

<!------------------------------>
<details><summary>

### Safari extension does not appear {#not-appear}

</summary>

It's known bug first seen in Safari 14. I reported it to Apple, but no reply yet.
This bug affects any extension made specificially for latest Safari 14 (completely new API).

If the extension does not show up in Safari, try **running the below command** in the terminal and restart your computer:
```bash
/System/Library/Frameworks/CoreServices.framework/Frameworks/LaunchServices.framework/Support/lsregister -f /Applications/Safari.app
```

If command above doesn't help, try another workaround:
1. Download and install [**Safari Technology Preview**](https://developer.apple.com/safari/download/)
2. Open and close Safari Technology Preview
3. Now extensions should appear in regular Safari

</details>