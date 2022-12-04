## Simple task automation with shell scripts (on macOS)

![Introduction Image containing a clock and some code](https://miro.medium.com/max/700/1*MfQnV8HAIQBjYDyRaLo_mw.jpeg)

Sometimes in your daily work life, there are situations where tasks pile up higher than your offices door frame. Every sane person would clean up enough to leave the office — inevitably leaving some tasks behind left and right.

Often those tasks are simple — maybe not even time consuming — though still annoying to pull off or just not worth it. But what if we had a chance to automate those?

> _⚠️_ **_Disclaimer on Operating Systems  
> _**_This article uses_ `_cron_` _on the command line and thus is not applicable for Windows clients - please take a look a_ `_schtasks.exe_` _in that regard.  
> On macOS systems_ `_cron_` _is available, supported and working perfectly but the usage of it is absorbed into_ `_launchd_` _- a daemon and agent manager._

## What is `cron`?

Looking into the manual pages of `cron` it states “daemon to execute scheduled commands”. There is no magic behind this just a straight forward utility to usually automate repetitive actions in a given environment. Those tasks are commonly known as “Cron Jobs”.

In the world of system administration this could include updating installed software, backing up databases to another system or whatever you may seem reasonable.

## How is `cron` doing that?

The magic to describe when a `cron job` runs and what it has to do is described in so called `cron tab` file which is short for “`cron table`” - at least slightly shorter. There are two different variants of crontab file available: system-wide and user-specific. Both of them behave similar but obviously for different scopes.

Depending on the operating system there often is the possibility to use specified directories like `/etc/cron.hourly/` to execute scripts contained within in the named interval. But as there are too many different operating systems, I will not do a deep dive into capabilities and directories - for those please refer your own man pages.

Instead let us take a look on how a user crontab is structured. Every line in the crontab consists of a `cron` scheduling expression and the path to an executable, a script or some command to be run. The system wide crontab additionally contains a username.

```
# user crontab example* * * * * /path/to/some/script# system-wide crontab example* * * * * foobar /path/to/some/script
```

## The `cron` expression

Combing the asterisks above, they’ll create a `cron` expression. In such an expression each asterisk translates to a specific category of time, ranging from minutes to months.

```
# cron expression details$MINUTE $HOUR $DAY_OF_MONTH $MONTH $DAY_OF_WEEK /path/to/some/script # MINUTE       → 0 to 59# HOUR         → 0 to 23# DAY_OF_MONTH → 1 to 31# MONTH        → 1 to 12# DAY_OF_WEEK  → 0 to 7 (with Sunday being 0 AND 7)
```

The cron scheduling expression in the example above would simply execute the given command at every available minute. The asterisks can be replaced by numbers, ranges and intervals. All representing certain conditions. But it is worth mentioning that whatever you may configure here will not be executed if the computer is in standby, offline any other “unavailable state”.

**Always / Any Value (**`***)**   `Every available value for the given slot will be executed. Thus having an asterisk in set for minutes, will lead to execution every minute.

**Number (** `**0**` **to** `**x**`**)**  
A number sets the execution to a fixed single time. The maximum number is dependent on the slot used. Minutes range from `0` to `59`, while Hours only range from `0` to `23`.  
The expression `0 22 * * *` will execute on everyday at exactly 22:00.

**List of Values (**`**,**`**)  
**Numbers matching the definition from above can also be put in as a separated list, allowing multiple points in time (e.g. `5,10`).  
The expression `15 8,11 * * *` would lead to executions on 08:15 and 11:15 once a day.

**Range of Values (**`**-**`**)  
**Again the numbers from above can also be used as a range of values (e.g. `10–12`). This allows the easy definition of timeframe in a “From-To” manner.  
The expression would `0 8–10 * * *` would lead to executions at 08:00, 09:00 and 10:00.

**Interval (**`**/**`**)  
**The interval is allowing us to define steps with the numbers from above (e.g. `*/15`). This can be used in conjunction with the notations above (e.g. `20–40/5`).  
The expression `*/15 * * * *` would execute a command every 15 minutes, while `15 8–6/2 * * *` would execute every second hour at 15 minutes past, thus on 08:15, 10:15 and so on.

As those expressions can get tedious to translate there is also tooling available to help with this, my favourite is [https://crontab.guru/](https://crontab.guru/). It’ll help writing and translating cron expressions by not only showing a syntax reference but also “verbal translation” and the next execution.

![Example of the crontab guru website](https://miro.medium.com/max/700/1*CRXA3mfiXzC2rF2A-ZLLqA.png)

Example of the [Crontab Guru Website](http://crontab.guru/)

> _💡_ In the screenshot above you can see shorthands using the `@something` notation. On the systems allowing these, they replace the whole expression.

```
#shorthand example@hourly /path/to/some/script
```

## Environmental circumstances

Whenever the script (or command) behind the `cron` expression is executed, there are some implications which must be clear to the user creating the script. All of those are related to environment variables for the `cron` execution.

`**PATH**`The default `PATH` for a `cron` execution is only containing `/usr/bin` and `/bin`. Thus if you have to use a software that has not installed its binaries within those directories, you’ll either need to change `PATH` or use an absolute path within your script.

`**SHELL   **`The default `SHELL` is `/bin/sh`. You can change this only by overriding the thes environment variable.

`**HOME   **`The default HOME is the Users Home Directory (e.g. `~`, `/home/foobar`, `/Users/foobar`). This is always relevant when changing directories in your script and can only be overridden by changing the corresponding variable.

`**MAILTO   **`The default of `MAILTO` is the the owner of the crontab. Thus notifications are sent to your local account by default and can be seen by `mail`\-command. One can use a comma separated list of values in the environment variable to define multiple address or an empty string to display mail sending.

Opposing the usual way of just altering the Users shell, all of the above environments can be overridden directly within the crontab. Take a look at the following example:

```
# environment varsHOME=/tmp PATH=/usr/local/bin:/usr/bin:/binSHELL=/usr/bin/zshMAILTO=""# crontab scripts* * * * * /path/to/some/script
```

## Editing the `crontab`

While it would be possible to look up your crontab file and edit it with your editor of choice, the man page of cron states that it is not the intended way to do it. Instead crontab allows you to use some arguments to achieve exactly that behaviour. The following list is an overview for what is possible without using super user permissions to execute `crontab`.

`**crontab -e   **`Edits the crontab with the default terminal text editor of the session, usually set by the `EDITOR` environment variable. After saving and existing the editor, the new crontab will be installed automatically. In case there is no crontab beforehand, it will be created with this command.

`**crontab -l   **`Lists the contents of the current `crontab`. It will also print a message in case that there is no file in existence.

`**crontab -r   **`Removes the active `crontab` and prevents all further executions.

In case you want to edit another users `crontab` it is possible to specify him with the `-u` argument, but as long as that argument is involved you’ll need to make it `sudo` to make it work.

## A real life example

So all that theory around `cron` and `crontab` is fine and helpful. But let’s say server administration is not your cup of tea - what could other suitable choices of `cron` jobs?

From time to time my job requires me to make screenshots. Sometimes load of them, sometimes just a few. On other days maybe none. But over the course of maybe the last half year I did not clean them up. Not a bit. Simply because I did not made it count. On average all these screenshots were used exactly once and then blissfully ignored.

The outcome of this scenario was a screenshots directory housing more than 600 screenshots in all sizes and resolutions. And with that information we can go full circle to the beginning of this article: I had need for a repeatable task which deletes screenshots.

## Scripting a solution

After thinking about what I can do with the amount of screenshots, I came up with the plan to do a daily check for files older than 30 days and then simply send them into void where they can enjoy the eternity.

Fortunately a macOS `bash` shell supplies me with all I need for the actual deletion. As the configured directory only contains images and I’m sure there will never be something else on accident `find` will do the trick without any major issues. Once the files are found removal will be executed and all deleted files are counted.

Later on I used a macOS tool called `terminal-notifier` to send a notification once the deletion is done with two possible outcomes:

1.  A Success Message, stating the amount of deleted Screenshots
2.  A “Nothing Happened” Message, informing me that nothing was old enough to be deleted

Overall the script looks like this:

> _💡_ Just in case we will add the execution permission for my user to the script. Even though testing showed that it is not necessary, it felt like the right thing to do.`chmod u+x delete-screenshots-older-30-days.sh`did the trick just fine.

Now all I needed was a time when this must be executed. I decided on Monday to Friday at 13 o’clock. As I’m having a daily standup meeting around this time, I can know for sure that the script is executed. So let’s go and update my crontab with the following line:

```
0 13 * * 1-5 /Users/nhoffmann/.cron/delete-screenshots-older-30-days.sh
```

## The Bottom Line

Utilities like `cron` exist for ages by now and they be forgotten or unknown to some people around the world - especially with most users of software not being interested in crawling through a terminal window like in ancient times. Fortunately their existence is a great benefit for operating systems and the users that know how to use such tools.

In this particular case a really straightforward task was resolved by what can be seen as basically a one-liner and I do like the simplicity of it.

It may take a few minutes more to get in line with all configuration around it but once you’ve got the hang of it, it’s a walk in the park to get some simple automation of your daily problems going.