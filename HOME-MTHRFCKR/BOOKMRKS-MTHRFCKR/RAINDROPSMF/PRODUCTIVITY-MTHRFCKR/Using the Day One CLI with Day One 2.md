# Using the Day One CLI with Day One 2

created: September 26, 2016 11:54 AM (UTC)
description: /Day One (2.0) /Mac / Using the Day One CLI with Day One 2 The Day One command line tool was originally written to work with Day One Classic, and by default writes its entries to the default Day One Classic journal directory1. If you want to use this tool to write entries in Day One 2 instead, there are a couple options. Option 1. Use this option if you don’t use Day One Classic at all. Modify the settings file for Day One Classic to automatically use the Day One 2 auto-import journal instead. Run the following command in Terminal: defaults write "$HOME/Library/Group Containers/5U8NS4GX82.dayoneapp/Data/Preferences/dayone.plist" JournalPackageURL "$HOME/Library/Group Containers/5U8NS4GX82.dayoneapp2/Data/Auto Import/Default Journal.dayone" Fixed!2 Now the CLI tool will automatically work! echo "This is my new entry" | dayone new Note that Option 1 will break Day One Classic. If you still use Classic, don’t use Option 1. On the other hand, if you don’t use Day One Classic at all, t
folder: BOOKMRKS-MTHRFCKR / PRODUCTIVITY-MTHRFCKR / Day One
url: http://help.dayoneapp.com/using-the-day-one-cli-with-day-one-2