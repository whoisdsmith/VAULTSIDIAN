---
tags:: medium
created: 2022-08-05T17:16:15 (UTC -04:00)
tags: []
source: https://medium.com/unknownimous/the-most-hackle-free-guide-to-terminal-beautification-for-macos-a-crash-course-in-z-shell-6e57ab17ad5e
author: Dijoraj Sen Roy
---

# The most hackle-free guide to terminal beautification for MacOS — A crash course in Z-shell customisation | by Dijoraj Sen Roy | Unknownimous | Medium

---
Speeding it up more than the standard bash terminal that comes with your MacOS by using iTerm2, Z shell, Oh My Zsh along with the Powerlevel10k theme and Neofetch to make your terminal look like this:

![[1_OGkMRGV3rY2_i645wDT0g.png]]

_NOTE : This tutorial will use iterm2 which is a popular alternative to the MacOS terminal. If you want you can use other terminals, usually Alacritty is a good option and looks damn cool too. This guide will also cover some simple things you can do with the Z-shell to show you why it is so much better than the bash shell. If you get stuck somewhere, don’t worry and keep reading I’ve tried to cover all the problems I ran into myself and how I went back. The reason I decided to write this article, even though some similar articles exist out there, is that personally I’ve run into problems and bugs at many points trying out themes and thus to make others lives easier, I made this comprehensive hackle-free guide to getting a fast and good looking terminal._

## Step 1 : Download Homebrew if you already haven’t.

Homebrew is the best thing to happen to the MacOS and honestly it makes developers' lives easy every day. If you’re not aware of this novel software, learn how to use it! At some point, it will be useful to you because of how easily you can download packages and maintain them with it, Without needing to know the git and ruby code underneath. You can get homebrew here, Just run this code in your terminal and answer install prompts:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

## Step 2 : Download iTerm2 using Homebrew commands

Why iTerm2? For the simple reason that it is way more customisable than the Mac terminal, you can adjust transparency, add images to the background, download and use themes for iTerm2, use custom fonts and a lot more:

```
brew cask install iterm2
```

_NOTE : If you want to see how to use custom themes and fonts follow this section or else feel free to skip to step 3._

1.  To open Preferences (Settings for iTerm2 basically) use COMMAND+i. A window will pop up where you can play around with colours and fonts, whatever works for you. I’m currently using the custom theme called dark+ with foreground text set to green. You can get all the themes here :

Select the theme you would like to download the code as an .itermcolors file then go to preferences on iterm2 and select color presets. Import the file from where you saved it and select it. Don’t forget to save your settings by selecting “Copy current settings to default profile” in General.

2\. I’m also using a downloaded custom font called Inconsolata dz, which is a powerline font, (you maybe asked to download this by Powerlevel10k but it's not compulsory and I’ll show you why later). However, if you want to download it:

```
# clone the repo of powerline fontsgit clone https://github.com/powerline/fonts.git --depth=1# installcd fonts./install.sh# clean-up a bit, remove the file after installation.cd ..rm -rf fonts# If you want to uninstall Powerline fonts completely for some  #reason :./uninstall.sh
```

After doing this the fonts should appear in Text > Fonts > Dropdown Menu.

## Step 3 : Open iTerm2 and install zsh and ohmyzsh

Zsh is a fast alternative to bash commands with the advantage that you can club your repetitive bash commands into a single zsh alias. It is very customisable, you can use custom themes, apps, and plugins with zsh. However, zsh alone is incomplete and requires a powerful plugin manager like ohmyzsh which we will be installing as well. I will also cover some simple things you can do with Z-Shell and OhMyZsh.

```
brew install zsh
```

Then paste and execute this in your terminal for Oh My Zsh:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## Step 4 : Learning how to work your way around Z-Shell

(If you do not care about this you may skip) Now that you have Z-shell and Oh My Zsh installed, somethings you Should know before we download the Powerlevel10k theme and Neofetch to further beautify our terminal are these: Managing Themes, Managing Plugins, Adding a permanent alias ( think of this as the custom commands) and finally getting your pip and conda commands to work with Zsh because they don’t do so by default.

1.  Managing themes: Say you’ve downloaded a custom theme and applied it to the terminal (Which we will soon), However ensuring that the theme loads every time, on startup is another issue altogether. To do this we will:

```
open ~/.zshrc
```

Think of this file as the code that executes every time you start your Z-shell. Head over to the part that says ZSH\_THEME and edit its value. the default should be “robbyrussell” you can make it “agnoster” or a custom theme after we download it. But DON’T close the File just yet :)

2\. Managing Plugins : In the same File zshrc go to the section that says plugins = (git) and edit it to plugins = (git docker). This will add docker as a plugin to the Z-shell. To know more about what plugins to use for your convenience head over to this link, however fair warning: Using too many plugins will slow you terminal startup considerably. Again don’t close the file after you’re done.

3\. Now I had run into an issue way later that screwed up everything for me, i.e, I couldn’t run conda or pip on my Z-shell. So I’m giving you guys the fix to this early on itself. Just like ~/.zshrc our bash shell has a file that allows us to use conda commands, we will simply call the file in our zshrc file. So open the zshrc file and at the end of it copy this code:

```
source ~/.bash_profile
```

4\. We will see how to use custom commands as permanent aliases in this section. I hope you have your ~/.zshrc open, if not open it using the command in step 1 (you may also use vim “vi” or “nano” just anything that edits text). Head over the part that says “Example aliases” right at the end of the file and makes an alias. The format is simple alias <name> = “<bash command>”

```
# Example aliases# alias zshconfig="mate ~/.zshrc"# alias ohmyzsh="mate ~/.oh-my-zsh"# Alias to run dockeralias dk="docker ps"#Alias to show lyrics of current song (Needs swaglyrics installed)alias showlyrics="swaglyrics -c"
```

Now you can run dk and it will run docker ps or showlyrics to print lyrics of the spotify song playing (again, needs swaglyrics installed-just an example)

5\. Now that you’re done with all the edits to the ~/.zshrc file hit Command+S to save it and head over to your iTerm2 to run this code and apply all the changes, alternatively you can restart the terminal and changes will apply automatically:

```
source ~/.zshrc
```

6\. The last thing we will see is how to run bash commands in zsh, or chnage shells completely. Also if you screw up in the installation stage just run the command to uninstall ohmyzsh, it’s gonna be like a rest and you can start again. To run bash in Z-shell use the command:

```
exec bash #executes bash shell
```

To change default shell completely (requires password and to restart terminal for changes to take place):

```
chsh -s /bin/bash #zsh to bashchsh -s /bin/zsh  #bash to zsh
```

To uninstall oh my zsh and reset shell to bash to start over, simply run:

```
uninstall_oh_my_zsh #in the zsh shell#if this doesn't work remove the .ohmyzsh file from the root #directory itself before re-intsalling zshsudo rm -R "yourRootPath/.ohmyzsh"## if you screw up so bad you need to install zsh again:brew reinstall zsh
```

## Step 5 : More Customisation !

In this section, we will install Powerlevel10k, which is one of the fastest themes for the Z-shell and use Neofetch along with it which displays the PC details and distribution as shown in the image. Note that if you just came for neofetch (a lot of people do), you can also use neofetch with your bash shell, I will show you how. But using Zsh is a lot faster and easier once you start using the terminal a lot more.

## Powerlevel10k

To clone your custom theme from its github repository into the /.ohmyzsh ’s custom themes directory run the following code in your terminal :

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
```

After that’s done hopefully the theme has been downloaded into the directory. Now all you need to do is open the ~/.zshrc file and set the theme so that it opens as required (shown in step 4.1)

```
open ~/. zshrc## Head over to ZSH_THEME in zshrc and paste this line instead:ZSH_THEME="powerlevel10k/powerlevel10k"##Save and run in terminal using source or restart.
```

When you open the terminal, Powerlevel10k’s built in installation guide will start. It may prompt you to download the Meslo Font (a powerline font), It’s not compulsory to do so. The rest of the steps are pretty self explanatory, just select the designs you like. The reason we were prompted to install powerline fonts (already shown in step 2.2) is because it supports powerline glyphs that make your shell look cool. However iTerm2 has it’s own built in powerline glyphs feature that you can enable in Text > Use built-in Powerline Glyphs, that is, if you did not download the fonts in step 2.2, which is fine.

After you’re done with the installation guide make sure to add this code in ~/.zshrc so that the setup guide doesn’t start everytime you start the iTerm2. If this was automatically added during the installation guide itself you may skip the step, so it’s worth checking in ~/.zshrc

```
#open ~/.zshrc and head over to the end of the file to add:#to disable Powerline promptPOWERLEVEL9K_DISABLE_CONFIGURATION_WIZARD=true#To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh#save and source ~/.zshrc in the terminal to save settings.
```

The setup for other custom themes are also fairly similar.

## Neofetch

> Neofetch is a command-line system information tool written in `bash 3.2+`. Neofetch displays information about your operating system, software and hardware in an aesthetic and visually pleasing way.

To install neofetch just simply run:

```
brew install neofetch ##if this does not work :#1. Clone the repogit clone https://github.com/dylanaraps/neofetch#2. go to the directorycd neofetch#3. install using make commandmake install##Or you can try pip install (if you followed step 4.3)
```

Now that this is done, you can just run the command “neofetch” in the terminal to display your Mac details along with the logo (which is also customisable). Again we need to save this in the ~/.zshrc file to make neofetch run everytime the Z-shell starts. This is simple as you just need to add neofetch to the end of ~/.zshrc and save the file, then use “source ~/.zshrc” command in the terminal to save settings.

If you want to run neofetch with your bash shell as well:

```
open ~/.bash_profile##Go to the end of the file and add the neofetch commandneofetch##save and exit the text editor and enter into the terminal:source ~/.bash_profile
```

**_NOTE : Since in this tutorial we are already running ~/. bash\_profile in our ~/.zshrc, this may cause neofetch to run twice, it’s upto you to figure out which shell to use._**

Here’s the link to neofetch’s github repo if you want to play around some more and get some customisations to amp up your terminal’s looks (for expample adding a custom logo or image instead of the ASCII apple logo):

You’re all set, happy hacking!
