_Hacks & tricks for developers working with the command line._

Whether you spend 99% of your time in your IDE, or you are an old school exclusive-vim-user that cringes at the thought of ever using a mouse in general, let alone to click a button in a memory hungry PyCharm IDE, all developers rely on using the command line to some extent.

I recently went about upgrading to the new M1 MacBook Pro, and in setting up my development environment I wanted to share some of my approaches for managing my command line environment as they served me quite well when migrating machines.

First, I want to note that much of my approach is heavily inspired from [Jeffrey Paul’s Stupid Unix Tricks Article](https://sneak.berlin/20191011/stupid-unix-tricks/), which is a great read. I have put a few of my own tweaks on top of it which I’ve included in this writeup.

## Getting Started — Manage Your Shell Startup rc Files

Let’s get started. First, I’ll introduce what my `~/.zshrc` file looks like. On your machine, your equivalent might be a `~/.bashrc` or something of the like, but I am talking about the run-command configuration file that executes on shell startup. Typically we take care of things like configuring command line software, adding aliases, setting some environment variables, etc. Often there can wind up being lots to do and these files can become a little bit involved and hard to navigate. Here’s mine:

![](https://miro.medium.com/max/700/1*44I0xPF5PPFIx_MHaJcaFQ.png)

It’s only got the one line. My `harbaugh.zshrc` file is what contains my _actual_ startup script. What’s the benefit of putting the script somewhere else? Version control! This script actually lives in a GitHub repository ([my tkutcher home repo](https://github.com/tkutcher/tkutcher)), which I have cloned locally to `~/tk/lib/`.

Side note: yes, all of my devices and machines are named after Baltimore Ravens players and Coaches.

But keeping these `rc` files in version control, I have a general reference for them, stored in the cloud, that I can adapt for machines as needed. I also have the version history so when I mess with my `rc` files and suddenly `python` starts a Python 2.7 interpreter, I can probably see what I need to fix to point it back to Python 3 and save my sanity for that hour.

Next, we can modularize our actual `rc` file itself. I created a `rc` dir in my tkutcher repository, and in it I have a collection of common and more modularized scripts that I use in startup commands. My `harbaugh.zshrc` just decides which ones it wants to source, and the only noteworthy thing it really does is this:

For example, in the `rc` directory I have that `p10k.zsh` which is the configuration file and startup for the oh-my-zsh powerlevel10k theme to make my terminal all pretty and excessive. By having this modularized, my `harbaugh.zshrc` file can source it, but if I have a separate windows machine running WSL (where there would be no powerlevel10k relevance), I don’t. At the same time, I can have all machines together use a common set of aliases I put in `aliases.sh` that they all source.

So now, for a new machine to use these common `rc` things, I just have to clone my tkutcher repo, and ultimately get the `~/.bashrc` to source whatever I want from the common stuff. Which was essentially my entire setup processes for my new Mac, an enhanced developer-friendly version of copy-paste.

So, visually, it looks something like this:

![](https://miro.medium.com/max/700/1*VgH84l07P2FTx1cee1XHxw.png)

And updating is a simple `git pull` command! Let’s say I write a new function `mkcd` which combines a `mkdir` and a `cd` in to the new dir, and I add it to that `funs.sh` above. In all of the machines I work on, I just have to do a `git pull` in my cloned tkutcher repository and now I have the `mkcd` command available everywhere. No copy-paste!

## Building your own Command Line Tools with Python

Next, I wanted to share how I go about making my own command line tools available, specifically with Python. Meaning I want to be able to write command-line apps in Python unique to my needs, and run them from anywhere.

## Easy Case: No Dependencies

If you have a simple script, that you’d just rather write in Python (because who wouldn’t), you can easily make it globally available by putting a python shebang at the top of the file and making the file executable.

As a trivial example, we could write the following script:

and run `chmod u+x echo.py` to make it executable. The first line (the shebang) says to use the python interpreter when this file is executed, so`./echo.py` will run this with the python interpreter without us needing to run `python` as a command.

Now say we want to run this from anywhere on the machine without having to enter the path to this script to execute it. In my example case, I would probably have this file in my tkutcher repo. What I can do is `cd` to `/usr/local/bin` and create a symlink to this script:

```
cd /usr/local/binsudo ln -s /Users/tkutcher/tk/lib/tkutcher/scripts/echo.py pyecho
```

Since `/usr/local/bin` is automatically on the system's path,`pyecho`will find our script and run properly.

## Hard Case: Dependencies

Now let’s say we want to have some scripts that have dependencies and use other pip packages. Or we want to package our scripts themselves in to their own package that can be pip installed. We can’t quite follow the same approach.

Generally with Python, I want a clean global environment with no pip dependencies. In other words, I want `pip freeze` to output nothing at all unless I am in a virtual environment. This makes it so for each Python project I have a completely independent environment and don’t have dependency issues at the global level.

So we can’t write global python scripts that import dependencies because we aren’t in an environment which has those dependencies.

An example for me is that at work, my engineers and I built a common `devtools` command line app in Python for working with our development projects, and it has a few other dependencies itself for things like using the GitLab API or the Azure/AWS APIs, which make it exponentially easier to maintain than trying to write the same functionality using the standard library.

The way I go about this is to create another folder inside my `~/tk/lib/` folder which holds a `venv` that has all of the dependencies I need for that purpose. So, for example, I did a `mkcd ~/tk/lib/devtools && python -m venv venv` then installed dependencies inside that venv.

After pip installing our devtools package, we have a command, `nvl`, which is then available inside that virtual environment. Still, this isn’t available globally without first running `source ~/tk/lib/devtools/venv/bin/activate` every time we want to use the `nvl` command.

Our goal is to be able to be anywhere on the machine, without being inside a virtual environment, and run `nvl`. To do this I wrote a simple `xnvl.sh` (prefixing the x so I can test out the development one separately when working on the actual code for it), that activates the relevant venv and runs the `nvl` command with forwarded args:

Now, in `/usr/local/bin` (which is already part of the path), I can create a symlink to that executable shell script:

```
sudo ln -s /Users/tkutcher/tk/lib/machines/harbaugh/xnvl.sh xnvl
```

and voila, `xnvl -h` runs my `nvl` command no matter what directory I am in on my machine, and no matter what virtual environment I am (or am not) in, with all the dependencies it needs without globally installing them. Once again, I threw this script in my home repo and all together it looks like this:

![](https://miro.medium.com/max/700/1*5OrKaQZExDezqppUtTggbg.png)

I also added another script which activates the same virtual environment and runes a `pip install --upgrade` from the `requirements.txt` file I have for that environment. Updating my command line tools is as simple as a pip upgrade!

If you are curious on building your own command-line apps/packages with Python, it is quite simple using [Poetry](https://python-poetry.org/docs/cli/).

## Storing Secrets & Environment Variables

Lastly, something that I found myself scrambling to get off of my old machine were the `.env` files I had for various projects. The files that kept some more-secret variables that I could source to run things from the command line that needed those variables for some sort of authentication.

I had to go to each individual project, see what I needed from the `.env` file (mainly lazily avoiding creating new tokens and whatnot), and then copy it over to the new machine.

I decided I would take the approach to consolidate these. I generally like the idea of keeping all of the secret things together. So I created a `~/tk/env` directory which has files like `gitlab-auth.env` , `godaddy.env` , etc. Now, this gives me a few benefits:

-   I never have to hunt down variables when I re-clone a repository somewhere else (losing my `.env` that was there), I just do a `source ~/tk/env/whatever.env`
-   Multiple projects which need the same or similar variables don’t each have to have a `.env` file with those variables, they can source the same shared one (and get updates easier for new/refreshed tokens, etc.)
-   You can keep it in version control and share it across machines on your public GitHub! Just kidding, of course. But the benefit is actually that you can isolate the secret things you have stored on your machine and explicitly not share it! So if you are syncing some folders to the cloud, or you don’t properly ignore `.env` files in your repositories, having them all in this centralized `env/` folder gives you a more explicit way to avoid the secret values ever accidentally coming off your machine.

## Wrapping Up

I will finish just recapping my directories/folder-namings in case you are interested, or if you have been reading this the whole time perplexed at my decisions for folders

-   `~/tk/`: My home for everything I deal with on my machine where I don’t have ugly `~/Documents` and `~/Music` folders that I never use and that don’t match my preferred naming. When I launch terminal and run `ls -la` I want it to be pretty.
-   `~/tk/env`: All secrets and environment variable files. I am the only one on this machine so I just wanted a central place for them.
-   `~/tk/lib`: My alternative to `/usr/local/lib` to avoid permission issues and having to run `sudo` for the things I wanted to do there.
-   `~tk/code`: Where I clone all of my repositories, grouped by organization/owner.

That is all — hope you enjoyed! I would love to hear feedback or other ideas.

You can check out my main tkutcher repository at [https://github.com/tkutcher/tkutcher/](https://github.com/tkutcher/tkutcher/)