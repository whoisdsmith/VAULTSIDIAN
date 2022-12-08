# git - the simple guide - no deep shit!

![](img/arrow.png)

to update your local repository to the newest commit, execute   
`git pull`  
in your working directory to _fetch_ and _merge_ remote changes.  
to merge another branch into your active branch (e.g. master), use  
`git merge <branch>`  
in both cases git tries to auto-merge changes. Unfortunately, this is not always possible and results in _conflicts_. You are responsible to merge those _conflicts_ manually by editing the files shown by git. After changing, you need to mark them as merged with  
`git add <filename>`  
before merging changes, you can also preview them by using  
`git diff <source_branch> <target_branch>`

in its simplest form, you can study repository history using.. `git log`  
You can add a lot of parameters to make the log look like what you want. To see only the commits of a certain author:  
`git log --author=bob`  
To see a very compressed log where each commit is one line:  
`git log --pretty=oneline`  
Or maybe you want to see an ASCII art tree of all the branches, decorated with the names of tags and branches:   
`git log --graph --oneline --decorate --all`  
See only which files have changed:   
`git log --name-status`  
These are just a few of the possible parameters you can use. For more, see `git log --help`


___

#article 