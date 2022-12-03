![Cover image for GIT CHEATSHEET](https://res.cloudinary.com/practicaldev/image/fetch/s--koMw51J7--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sfoahn4fqdfslzx84n2j.jpg)

[![Danish Saleem](https://res.cloudinary.com/practicaldev/image/fetch/s--zz42Ir94--/c_fill,f_auto,fl_progressive,h_50,q_auto,w_50/https://dev-to-uploads.s3.amazonaws.com/uploads/user/profile_image/737886/dccf72d2-2109-4ecf-ac48-3ca61496004f.jpg)](https://dev.to/mrdanishsaleem)

[Git](https://dev.togit/) is the free and open-source distributed version control system that's responsible for everything [GitHub](https://github.com/mrdanishsaleem) related that happens locally on your computer.

This cheat sheet features the most important and commonly used Git commands for easy reference.

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#setup)SETUP

Configuring user information used across all local repositories  

```
git config --global user.name "[firstname lastname]"
set a name that is identifiable for credit when review version history
```

Enter fullscreen mode Exit fullscreen mode

```
git config --global user.email "[valid-email]"
set an email address that will be associated with each history marker
```

Enter fullscreen mode Exit fullscreen mode

```
git config --global color.ui auto
set automatic command line coloring for Git for easy reviewing
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#setup-amp-init)SETUP & INIT

Configuring user information, initializing and cloning repositories  

```
git init
initialize an existing directory as a Git repository
```

Enter fullscreen mode Exit fullscreen mode

```
git clone [url]
retrieve an entire repository from a hosted location via URL
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#stage-amp-snapshot)STAGE & SNAPSHOT

Working with snapshots and the Git staging area  

```
git status
show modified files in working directory, staged for your next commit
```

Enter fullscreen mode Exit fullscreen mode

```
git add [file]
add a file as it looks now to your next commit (stage
```

Enter fullscreen mode Exit fullscreen mode

```
git reset [file]
unstage a file while retaining the changes in working directory
```

Enter fullscreen mode Exit fullscreen mode

```
git diff
diff of what is changed but not staged
```

Enter fullscreen mode Exit fullscreen mode

```
git diff --staged
diff of what is staged but not yet commited
```

Enter fullscreen mode Exit fullscreen mode

```
git commit -m “[descriptive message]”
commit your staged content as a new commit snapshot
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#branch-amp-merge)BRANCH & MERGE

Isolating work in branches, changing context, and integrating changes  

```
git branch
list your branches. a * will appear next to the currently active branch
```

Enter fullscreen mode Exit fullscreen mode

```
git branch [branch-name]
create a new branch at the current commit
```

Enter fullscreen mode Exit fullscreen mode

```
git checkout
switch to another branch and check it out into your working directory
```

Enter fullscreen mode Exit fullscreen mode

```
git merge [branch]
merge the specified branch’s history into the current one
```

Enter fullscreen mode Exit fullscreen mode

```
git log
show all commits in the current branch’s history
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#inspect-amp-compare)INSPECT & COMPARE

Examining logs, diffs and object information  

```
git log
show the commit history for the currently active branch
```

Enter fullscreen mode Exit fullscreen mode

```
git log branchB..branchA
show the commits on branchA that are not on branchB
```

Enter fullscreen mode Exit fullscreen mode

```
git log --follow [file]
show the commits that changed file, even across renames
```

Enter fullscreen mode Exit fullscreen mode

```
git diff branchB...branchA
show the diff of what is in branchA that is not in branchB
```

Enter fullscreen mode Exit fullscreen mode

```
git show [SHA]
show any object in Git in human-readable format
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#tracking-path-changes)TRACKING PATH CHANGES

Versioning file removes and path changes  

```
git rm [file]
delete the file from project and stage the removal for commit
```

Enter fullscreen mode Exit fullscreen mode

```
git mv [existing-path] [new-path]
change an existing file path and stage the move
```

Enter fullscreen mode Exit fullscreen mode

```
git log --stat -M
show all commit logs with indication of any paths that moved
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#ignoring-patterns)IGNORING PATTERNS

Preventing unintentional staging or commiting of files  

```
logs/
*.notes
pattern*/
Save a file with desired paterns as .gitignore with either direct string
matches or wildcard globs.
```

Enter fullscreen mode Exit fullscreen mode

```
git config --global core.excludesfile [file]
system wide ignore patern for all local repositories
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#share-amp-update)SHARE & UPDATE

Retrieving updates from another repository and updating local repos  

```
git remote add [alias] [url]
add a git URL as an alias
```

Enter fullscreen mode Exit fullscreen mode

```
git fetch [alias]
fetch down all the branches from that Git remote
```

Enter fullscreen mode Exit fullscreen mode

```
git merge [alias]/[branch]
merge a remote branch into your current branch to bring it up to date
```

Enter fullscreen mode Exit fullscreen mode

```
git push [alias] [branch]
Transmit local branch commits to the remote repository branch
```

Enter fullscreen mode Exit fullscreen mode

```
git pull
fetch and merge any commits from the tracking remote branch
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#rewrite-history)REWRITE HISTORY

Rewriting branches, updating commits and clearing history  

```
git rebase [branch]
apply any commits of current branch ahead of specified one
```

Enter fullscreen mode Exit fullscreen mode

```
git reset --hard [commit]
clear staging area, rewrite working tree from specified commit
```

Enter fullscreen mode Exit fullscreen mode

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#temporary-commits)TEMPORARY COMMITS

Temporarily store modified, tracked files in order to change branches  

```
git stash
Save modified and staged changes
```

Enter fullscreen mode Exit fullscreen mode

```
git stash list
list stack-order of stashed file changes
```

Enter fullscreen mode Exit fullscreen mode

```
git stash pop
write working from top of stash stack
```

Enter fullscreen mode Exit fullscreen mode

```
git stash drop
discard the changes from top of stash stack
```

Enter fullscreen mode Exit fullscreen mode

___

## [](https://dev.to/mrdanishsaleem/git-cheatsheet-4kpn#lets-connect)Let's connect!

You can follow me on [Twitter](https://twitter.com/MrDanishSaleem), [LinkedIn](https://www.linkedin.com/in/mrdanishsaleem/) & [GitHub](https://github.com/mrdanishsaleem/)

___

If you like this post. Kindly support me by [Buying Me a Coffee](https://www.buymeacoffee.com/mrdanishsaleem)

[![Buy Me a Coffee](https://res.cloudinary.com/practicaldev/image/fetch/s--IrvJezlq--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v0ikih5nlsqs0oops11e.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--IrvJezlq--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v0ikih5nlsqs0oops11e.png)