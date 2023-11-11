# Installed PKGs

---

**1. View only recently installed items**  

Open the Terminal.app (Utilities/Terminal.app) and copy and paste this command:

---

`grep 'Installed' /private/var/log/install.log`

---

This will return a list of every item successfully installed since the new log file was created. If there’s nothing of interest there, but you think there should be, then you’re going to need to see a bit more of the log file, and perhaps find out when it was ‘rotated’ or ‘turned over’ (i.e., the last time the system archived the install.log and created a new one).  

---

**2. View the entire install log**  

---

If you’d like to see the whole log for this reason, or perhaps you want to see whether something *failed* to install, it’s probably best having the log displayed in TextEdit rather than Terminal, so copy and paste this command into the Terminal window:

---

`cat /private/var/log/install.log | open -f`

---

You’ll see at the beginning of the file it’ll tell you when the file was turned over. Don’t forget you can use TextEdit’s search facility (Command-F) to search for particular instances or items you’re interested in finding. When you’re finished viewing this file, you can simply close TextEdit and discard it. It isn’t the actual log file, but rather a local copy of it.  

---

**3. Using Console**  

---

Alternatively,, if you don’t feel comfortable in Terminal, you can view all your install logs in the Console.app. You can open Console either through Finder by navigating to /Applications/Utilities/Console.app or just by typing ‘cons’ in either Spotlight or Launchpad. Once Console is open, scroll down the sidebar, looking for **/var/log**. Click the disclosure triangle if it’s not already pointing downwards and look for **install.log**. Click on that, and then in the filter bar in the main window, type *installed* (unlike the grep command I gave you above, this one is not case sensitive and will return both ‘Installed’ and ‘installed’).  

---

examining an old, compressed install log

Notice in the screenshot above, I’m examining a turned over log, not the current one. As this particular install of Mountain Lion was only done on May 3rd, there’s only one turned over log file.  

> **Pro Tip No.2:** You can force the system to turn over all the log files, including **install.log** even if they haven’t reached their maximum size. As it says in the `man` page for `newsyslog`, this can be “useful for diagnosing system problems by providing you with fresh logs that contain only the problems.”
> 
> To force all log files to be turned over, simply enter `sudo newsyslog -F` into Terminal. Hit ‘return’ and supply your password, as always with the `sudo` command.

---

**4. Using Finder**  

If Console is a bit too off-territory for you, there’s nothing wrong with viewing your logs in Finder and TextEdit. To do that, click on the Finder, then hit ‘shift-command-G’ on the keyboard (or click ‘Go’ in the menu bar and choose ‘Go to Folder’). Type or paste this into the dialogue box:

`/var/log`

and hit the ‘Go’ button.

[![Go to folder](https://applehelpwriter.files.wordpress.com/2013/05/screen-shot-2013-05-21-at-00-47-09.png?w=543)](https://applehelpwriter.files.wordpress.com/2013/05/screen-shot-2013-05-21-at-00-47-09.png)

Right-click on any of the logs you want to open and choose ‘open with’ from the contextual menu. Choose ‘TextEdit’ or your favourite plain text editor app. If none of your text editors show up in the menu, click ‘Other’ and change the ‘Enable’ menu to ‘All Applications’. You will now be able to choose TextEdit or some other editor if you have one. Note that unlike Step 2 above when we used a Terminal command to open a copy of the install log in TextEdit, here you are viewing the actual files rather than a copy of them. Although the log files are not important to the running of your system and can be deleted or altered without causing any consequences, they do provide useful records for troubleshooting so its always good practice to keep them in tact if you can.

---
