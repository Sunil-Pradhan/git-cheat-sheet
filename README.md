
<h1 align="center">Git Cheat Sheet</h1>

<p align="center">
  <img width="500" height="208" src="https://github.com/Sunil-Pradhan/git-cheat-sheet/blob/master/img/Git-Cheat-Sheet-Logo.png">
</p>

<p align="center">
Git is the free and open source distributed version control system. This cheat sheet saves you from learning all the commands by heart and features the most important and commonly used Git commands for easy reference. 
</p>

<p align="center">
Be free to contribute and update the grammar mistakes.
</p>




## Table of Contents
* [Setup](#setup)
* [Create](#create)
* [Local Changes](#local)
* [Search](#Search)
* [Commit & History](#Commit&History)
* [Move & Rename](#Move&Rename)
* [Branches & Tags](#Branches&Tags)
* [Update & Publish](#Update&Publish)
* [Merge & Rebase](#Merge&Rebase)
* [Undo](#Undo)


<a name="setup"></a>
## Setup


**Show configuration:** 

*Current configuration:*

```
$ git config --list
```

*Repository configuration:*

```
$ git config --local --list
```

*Global configuration:*

```
$ git config --global --list
```

*System configuration:*

```
$ git config --system --list
```

<hr>

**Configuring user information used across all local repositories**

*Set a name that is identifiable for credit when review version history:*

```
$ git config --global user.name “[firstname lastname]”
```

*Set an email address that will be associated with each history marker:*

```
$ git config --global user.email “[valid-email]”
```

*Set automatic command line coloring for Git for easy reviewing:*

```
$ git config --global color.ui auto
```

*Set global editor for commit:*

```
$ git config --global core.editor “code –wait”
```
<hr>

:bulb: **Remember**

* **Ask for help** ```git <command> --help```
* **master** is the default development branch
* **origin** is the default upstream repository


<a name="create"></a>
## Create

**Initializing and cloning repositories:**

*Create a new local repository in the current directory:*

```
$ git init
```

*Create a new local repository in a specific directory:*

```
$ git init [directory_name]
```

*Clone an existing repository:*

There are two ways:

* SSH

* HTTP

By SSH: ```$ git clone ssh://user@domain.com/repo.git```

By HTTP: ```$ git clone http://domain.com/user/repo.git```


<a name="local"></a>
## Local Changes

**Working with snapshots and the Git staging area:**

*Changes in working directory, staged for your next commit:*

```
$ git status
```

*Add a file as it looks now to your next commit (stage):*

```
$ git add [File_name]
```

*Add all current changes to the next commit(root directory):*

```
$ git add .
```

*Add all current changes to the next commit(root and other directory):*

```
$ git add --all
```

or

```
$ git add -A
```

or

```
$ git add *
```

*Unstage a file while retaining the changes in working directory:*

```
$ git reset [file]
```

*Diff of what is changed but not staged:*

```
$ git diff
```

*Diff of what is staged but not yet commited:*

```
$ git diff --staged
```

*See difference of a specific file:*

```
$ git diff [file_name]
```


*Commit with message:*

```
$ git commit -m “[descriptive message]”
```

<hr>

**Commit all local changes in tracked files:**

```
$ git commit -a
```

**Commit previously staged changes:**

```
$ git commit
```

**Commit skipping the staging area and adding message:**

```
$ git commit -am 'message here'
```

**Commit to some previous date:**

```
$ git commit --date="`date --date='n day ago'`" -am "<Commit Message Here>"
```

**Change last commit:** (*Don't amend published commits!*)

```
$ git commit -a --amend
```

**Amend with last commit but use the previous commit log message:** (*Don't amend published commits!*)

```
$ git commit --amend --no-edit
```

**Change committer date of last commit:** 

```
GIT_COMMITTER_DATE="date" git commit --amend
```

**Change Author date of last commit:** 

```
$ git commit --amend --date="date"
```

**Move uncommitted changes from current branch to some other branch:** 

```
$ git stash
$ git checkout branch2
$ git stash pop
```

**Restore stashed changes back to current branch:** 

```
$ git stash apply
```

**Restore particular stash back to current branch:** ( _{stash_number}_ can be obtained from ```git stash list``` )

```
$ git stash apply stash@{stash_number}
```

**Remove the last set of stashed changes:** 

```
$ git stash drop
```

## Search

**A text search on all files in the directory:** 

```
$ git grep "Hello"
```

## Commit & History

**Show all commits, starting with newest (it'll show the hash, author information, date of commit and title of the commit):** 

```
$ git log
```

**Show all the commits(it'll show just the commit hash and the commit message):** 

```
$ git log --oneline
```

**Show all commits of a specific user:**

```
$ git log --author="username"
```

**Show changes over time for a specific file:**

```
$ git log -p <file>
```

**Show history of changes for a file with diffs:**

```
$ git log -p <file> <directory>
```

**Display commits that are present only in remote/branch in right side:**

```
$ git log --oneline <origin/master>..<remote/master> --left-right
```

**Who changed, what and when in a file:**

```
$ git blame <file>
```

**A commit identified by ID:**

```
$ git show <ID>
```

**A specific file from a specific ID:**

```
$ git show <ID>:<file>
```

**Show Reference log:**

```
$ git reflog show
```

**Delete Reference log:**

```
$ git reflog delete
```

## Move & Rename

**Rename a file:** 
Rename Index.txt to Index.html

```
$ git mv Index.txt Index.html
```

## Branches & Tags

**Create a new branch:** 

```
$ git branch <branchName>
```

**List all local branches:** 

*star( * ) marks represents the current branch* 

```
$ git branch
```

**List local/remote branches:** 

```
$ git branch -a
```

**List all remote branches:** 

```
$ git branch -r
```

**Switch to a branch:** 

```
$ git checkout <branch>
```

**Checkout single file from different branch:** 

```
$ git checkout <branch> -- <filename>
```

**Create and switch to new branch:** 

```
$ git checkout -b <branch>
```

**Create a new branch from an exiting branch and switch to new branch:** 

```
$ git checkout -b <new_branch> <existing_branch>
```

**Checkout and create a new branch from existing commit:** 

```
$ git checkout <commit-hash> -b <new_branch_name>
```

**Create a new tracking branch based on a remote branch:** 

```
$ git branch --track <new-branch> <remote-branch>
```

**Delete a local branch:** 

```
$ git branch -d <branch>
```

**Rename current branch to new branch name:** 

```
$ git branch -m <new_branch_name>
```

**Force delete a local branch(You will lose unmerged changes):** 

```
$ git branch -D <branch>
```

**Mark HEAD with a tag:** 

```
$ git tag <tag-name>
```

**Mark HEAD with a tag and open the editor to include a message:** 

```
$ git tag -a <tag-name>
```

**Mark HEAD with a tag that includes a message:** 

```
$ git tag <tag-name> -am 'message here'
```

**List all tags:** 

```
$ git tag
```

**List all tags with their messages (tag message or commit message if tag has no message):** 

```
$ git tag -n
```

## Update & Publish

**List all current configured remotes:** 

```
$ git remote -v
```

**Show information about a remote:** 

```
$ git remote show <remote>
```

**Add new remote repository, named (remote):** 

```
$ git remote add <remote> <url>
```

**Rename a remote repository, from (remote) to (new_remote):** 

```
$ git remote rename <remote> <new_remote>
```

**Remove a remote:** 

```
$ git remote rm <remote>
```
*Note: git remote rm does not delete the remote repository from the server. It simply removes the remote and its references from your local repository.*


**Download all changes from (remote), but don't integrate into HEAD:** 

```
$ git fetch <remote>
```

**Download changes and directly merge/integrate into HEAD:** 

```
$ git remote pull <remote> <url>
```

**Get all changes from HEAD to local repository:** 

```
$ git pull origin master
```

**Get all changes from HEAD to local repository without a merge:** 

```
$ git pull --rebase <remote> <branch>
```


**Publish local changes on a remote:** 

```
$ git push remote <remote> <branch>
```

**Delete a branch on the remote:** 

```
$ git push <remote> :<branch>
```
OR

```
$ git push <remote> --delete <branch> (since Git v1.7.0)
```

**Publish your tags:** 

```
$ git push --tags
```

**Configure the merge tool globally to meld (editor):** 

```
$ git config --global merge.tool meld
```

**Use your configured merge tool to solve conflicts:** 

```
$ git mergetool
```

## Merge & Rebase

**Merge (branch1) into (master):** 

```
$ git checkout <master>
$ git merge <branch1>
```

**Rebase your current HEAD onto (branch):** 

*Don't rebase published commit!*

```
$ git rebase <branch>
```

**Abort a rebase:** 

```
$ git rebase --abort
```

**Continue a rebase after resolving conflicts:** 

```
$ git rebase --continue
```

**Use your editor to manually solve conflicts and (after resolving) mark file as resolved:** 

```
$ git add <resolved-file>
```

```
$ git rm <resolved-file>
```

**Squashing commits:** 

```
$ git rebase -i <commit-just-before-first>
```

Now replace this,

```
pick <commit_id>
pick <commit_id2>
pick <commit_id3>
```
to this,

```
pick <commit_id>
squash <commit_id2>
squash <commit_id3>
```

## Resolve merge conflicts

**View merge conflicts** 

```
$ git diff
```

**View merge conflicts against base file** 

```
$ git diff --base <fileName>
```

**View merge conflicts against your changes** 

```
$ git diff --ours <fileName>
```

**View merge conflicts against other changes** 

```
$ git diff --theirs <fileName>
```

**Discard a conflicting patch** 

```
$ git reset --hard
$ git rebase --skip
```

**After resolving conflicts, merge with** 

```
$ git add <conflicting_file>
$ git rebase --continue
```

## Undo

**Discard all local changes in your working directory:** 

```
$ git reset --hard HEAD
```

**Get all the files out of the staging area(i.e. undo the last git add):** 

```
$ git reset HEAD
```

**Discard local changes in a specific file:** 

```
$ git checkout HEAD <file>
```

**Revert a commit (by producing a new commit with contrary changes):** 

```
$ git revert <commit>
```

**Reset your HEAD pointer to a previous commit and discard all changes since then:** 

```
$ git reset --hard <commit>
```

**Reset your HEAD pointer to a remote branch current state:** 

```
$ git reset --hard <remote/branch> e.g., upstream/master, origin/my-feature
```

**Reset your HEAD pointer to a previous commit and preserve all changes as unstaged changes:** 

```
$ git reset <commit>
```

**Reset your HEAD pointer to a previous commit and preserve uncommitted local changes:** 

```
$ git reset --keep <commit>
```

**Remove files that were accidentally committed before they were added to .gitignore** 

```
$ git rm -r --cached .
$ git add .
$ git commit -m "remove xyz file"
```

## Revert

**Return to the last commited state** 

*This can't be undone!*

```
$ git reset --hard
```





