---
tags:: medium
created: 2022-08-05T17:15:32 (UTC -04:00)
tags: []
source: https://medium.com/helpshift-engineering/the-most-powerful-terminal-on-macos-d8b8524925cf
author: Tanuj Soni
---

# The Most Powerful Terminal on macOS | by Tanuj Soni | helpshift-engineering | Medium

---
Are you struggling using the default terminal, Is your productivity getting affected?

I have the best solution for this, This productivity hack can change your life as a Software Engineer.

![[1Amn3ZELXFFtmgynpddcAsQ.png]]

If you want your terminal to look like this, Come on, you’re the person who must be worth reading this blog.

Let's get it done, follow these simple steps-

## Install Homebrew 🍺

-   Open terminal and paste.

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Install & Configure iTerm2 ⚙️

-   If you’re on a macOS, I strongly suggest you switch from the default mac Terminal to **iTerm2** because you can customize it the way you want. However, if you prefer to use the default Terminal or you’re on a different OS (e.g. Ubuntu), you can skip this step and use whichever terminal app you prefer.
-   The following is the single command required to install **iTerm2** on macOS using **Homebrew**🍺:

```
brew cask install iterm2
```

Now that we have a very basic **iTerm2**, let’s download the material design color theme. There are a ton of themes available at [iTerm Themes](https://iterm2colorschemes.com/). I personally prefer this specific [**Material Design Theme**](https://github.com/MartinSeeler/iterm2-material-design) by Martin Seeler.

## **To enable it:**

1.  Go to _iTerm2 > Preferences > Profiles > Colors Tab_
2.  Click on _Color Presets > Impor_
3.  Select the _theme_ file
4.  After import, select the _theme_ from _Color_ _Presets…_

## Additional Customizations

iTerm2 offers a very handy Status Bar view that you can customize to display the components of your desires.

**To enable it:**

1.  Go to _iTerm2 > Preferences > Profiles > Session_
2.  Turn on **Status bar enabled**
3.  Click on **Configure Status Bar** to begin setting up your status bar configuration by dragging components from _Status Bar Components Menu_ into _Active Components._
4.  Click on **Auto-Rainbow** to finalize with a colourful touch 🌈.

## Now comes the interesting Part, This will make your Terminal Way Better..!

## Install Oh-my-zsh :

[Oh-My-Zsh](https://github.com/ohmyzsh/ohmyzsh) is the most popular framework for managing ZSH configuration and it comes with a ton of plugins to take advantage of.  
The oh-my-zsh will replace the default terminal with zsh automatically when you install it.

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Enable Plugins

To enable some cool plugins, you have to add them to the **_.zshrc_** file located in the **$HOME** directory of your system. Open it and place them under the plugins section.

```
# An example of a plugin plugins=(git zsh-autosuggestions zsh-completions zsh-syntax-highlighting gradle)
```

## Themes — Make your terminal beautiful

There are over one hundred themes present in the Oh-My-Zsh bundle that you can choose from. Check out these [screenshots](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) on their documentation to find the perfect one for you. To enable the theme of your preference, open the **_.zshrc_** file and find an environment variable:

```
ZSH_THEME="robbyrussell"
```

Change the value to your favourite theme and you’re good to go. You may also change it to _random_ to use a random theme every time you start up a new terminal window.

## **My Recommendation**

The [**powerlevel10k**](https://github.com/romkatv/powerlevel10k) theme is probably by far the coolest theme of all. It allows the configurations to add additional infoboxes to the left and right of the terminal. To set up this theme (or any other custom themes that are not bundled with Oh-My-Zsh),

-   Clone the repository

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

-   Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`.
-   Restart your terminal to make sure that the **_.zshrc_** file is loaded.  
    Or just run `source .zshrc` .
-   Run `p10k configure` and customize it as you like.

Now You are good to go and ready to use the full power of Oh-my-zsh in your mac.

## Bonus

Try to find how to colourize your **_ls_** command.

## Thanks for Reading 😃
