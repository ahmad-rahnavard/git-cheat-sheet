


# GIT CHEAT SHEET [:arrow_up:](#index)
Git is the free and open source distributed version control system that's responsible for everything GitHub related that happens locally on your computer. This cheat sheet features the most important and commonly used Git commands for easy reference.


## Index
- [INSTALLATION & GUIS](#installation--guis-arrow_up)
- [SETUP](#setup-arrow_up)
- [STAGE & SNAPSHOT](#stage--snapshot-arrow_up)
- [BRANCH & MERGE](#branch--merge-arrow_up)
- [INSPECT & COMPARE](#inspect--compare-arrow_up)
- [TRACKING PATH CHANGES](#tracking-path-changes-arrow_up)
- [IGNORING PATTERNS](#ignoring-patterns-arrow_up)
- [SHARE & UPDATE](#share--update-arrow_up)
- [REWRITE HISTORY](#rewrite-history-arrow_up)
- [TEMPORARY COMMITS](#temporary-commits-arrow_up)


## INSTALLATION & GUIS [:arrow_up:](#index)
With platform specific installers for Git, GitHub also provides the ease of staying up-to-date with the latest releases of the command line tool while providing a graphical user interface for day-to-day interaction, review, and repository synchronization.

#### GitHub for Windows
[https://windows.github.com](https://windows.github.com)
#### GitHub for Mac
[https://mac.github.com](https://mac.github.com)

<h>
For Linux and Solaris platforms, the latest release is available on the official Git web site.

#### Git for All Platforms
[http://git-scm.com](http://git-scm.com)


## SETUP [:arrow_up:](#index)
Configuring user information used across all local repositories

```bash
# set a name that is identifiable for credit when review version history
git config --global user.name “[firstname lastname]”
```

```bash
# set an email address that will be associated with each history marker
git config --global user.email “[valid-email]”
```

```bash
# set automatic command line coloring for Git for easy reviewing
git config --global color.ui auto
```


## SETUP & INIT [:arrow_up:](#index)
Configuring user information, initializing and cloning repositories

```bash
# initialize an existing directory as a Git repository
git init
```

```bash
# retrieve an entire repository from a hosted location via URL
git clone [url]
```


## STAGE & SNAPSHOT [:arrow_up:](#index)
Working with snapshots and the Git staging area

```bash
# show modified files in working directory, staged for your next commit
git status
```

```bash
# add a file as it looks now to your next commit (stage)
git add [file]
```

```bash
# unstage a file while retaining the changes in working directory
git reset [file]
```

```bash
# diff of what is changed but not staged
git diff
```

```bash
# diff of what is staged but not yet committed
git diff --staged
```

```bash
# commit your staged content as a new commit snapshot
git commit -m “[descriptive message]”
```


## BRANCH & MERGE [:arrow_up:](#index)
Isolating work in branches, changing context, and integrating changes

```bash
# list your branches. a * will appear next to the currently active branch
git branch
```

```bash
# create a new branch at the current commit
git branch [branch-name]
```

```bash
# switch to another branch and check it out into your working directory
git checkout
```

```bash
# merge the specified branch’s history into the current one
git merge [branch]
```

```bash
# show all commits in the current branch’s history
git log
```


## INSPECT & COMPARE [:arrow_up:](#index)
Examining logs, diffs and object information

```bash
# show the commit history for the currently active branch
git log
```

```bash
# show the commits on branchA that are not on branchB
git log branchB..branchA
```

```bash
# show the commits that changed file, even across renames
git log --follow [file]
```

```bash
# show the diff of what is in branchA that is not in branchB
git diff branchB...branchA
```

```bash
# show any object in Git in human-readable format
git show [SHA]
```


## TRACKING PATH CHANGES [:arrow_up:](#index)
Versioning file removes and path changes

```bash
# delete the file from project and stage the removal for commit
git rm [file]
```

```bash
# change an existing file path and stage the move
git mv [existing-path] [new-path]
```

```bash
# show all commit logs with indication of any paths that moved
git log --stat -M
```


## IGNORING PATTERNS [:arrow_up:](#index)
Preventing unintentional staging or commiting of files
```
logs/
*.notes
pattern*/
```
Save a file with desired patterns as .gitignore with either direct string
matches or wildcard globs.

```bash
# system wide ignore pattern for all local repositories
git config --global core.excludesfile [file]
```


## SHARE & UPDATE [:arrow_up:](#index)
Retrieving updates from another repository and updating local repos

```bash
# add a git URL as an alias
git remote add [alias] [url]
```

```bash
# fetch down all the branches from that Git remote
git fetch [alias]
```

```bash
# merge a remote branch into your current branch to bring it up to date
git merge [alias]/[branch]
```

```bash
# Transmit local branch commits to the remote repository branch
git push [alias] [branch]
```

```bash
# fetch and merge any commits from the tracking remote branch
git pull
```


## REWRITE HISTORY [:arrow_up:](#index)
Rewriting branches, updating commits and clearing history

```bash
# apply any commits of current branch ahead of specified one
git rebase [branch]
```

```bash
# clear staging area, rewrite working tree from specified commit
git reset --hard [commit]
```


## TEMPORARY COMMITS [:arrow_up:](#index)
Temporarily store modified, tracked files in order to change branches

```bash
# Save modified and staged changes
git stash
```

```bash
# list stack-order of stashed file changes
git stash list
```

```bash
# write working from top of stash stack
git stash pop
```

```bash
# discard the changes from top of stash stack
git stash drop
```
