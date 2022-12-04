One reason I like using Oh-My-Zsh it that it makes theming easy. Looking at a “stock” terminal can be pretty horrible.

Zsh can be downloaded in your favorite repo or from its [official site](https://ohmyz.sh/).

## Included Themes

When you download zsh it comes stocked with one hundred themes ready to go. You can browse [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) to choose one. Adding these themes is easy as pie:

In terminal, type `open ~/.zshrc`. Here, the active theme is listed as `ZSH_THEME=”robbyrussel”`. To change the active theme, simply copy the the name of your chosen theme and paste it in place of `robbyrussel`.

Refresh your zsh terminal with `source ~/.zshrc` and your new theme should be visible.

## External Themes

If you scroll down far enough through the list pre-installed themes, you’ll see an option for [External Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes).

To install one of these, `git clone` its repo into `~/.oh-my-zsh/custom/themes`. After this, run `open ~/.zshrc` and set the theme just like before with `rubbyrussel`.

Once again, refresh with `source ~/.zshrc` and you should be good to go.