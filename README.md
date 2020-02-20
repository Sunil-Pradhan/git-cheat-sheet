# Git Cheat Sheet

![my certification](/images/Git-Cheat-Sheet-Banner.png)

Git cheat sheet saves you from learning all the commands by heart. Be free to contribute, update the grammar mistakes. 

## Table of Contents
* [Setup](#setup)
* [Create](#Create)
* [Local Changes](#LocalChanges)
* [Search](#Search)


## Setup


**Show current configuration:** 

```
$ git config --list
```

**Show repository configuration:** 

```
$ git config --local --list
```

**Show global configuration:** 

```
$ git config --global --list
```

**Show system configuration:** 

```
$ git config --system --list
```

**Set a name that is identifiable for credit when review version history:** 

```
$ git config --global user.name “[firstname lastname]”
```

**Set an email address that will be associated with each history marker:**

```
$ git config --global user.email “[valid-email]”
```

**Set automatic command line coloring for Git for easy reviewing:**

```
$ git config --global color.ui auto
```

**Set global editor for commit:**

```
$ git config --global core.editor “code –wait”
```

## Create

**Clone an existing repository:**

There are two ways:

* SSH

* HTTP

**By SSH:**

```
$ git clone ssh://user@domain.com/repo.git
```

**By HTTP:**

```
$ git clone http://domain.com/user/repo.git
```

**Create a new local repository in the current directory:**

```
$ git init
```

**Create a new local repository in a specific directory:**

```
$ git init <directory>
```

## Local Changes

**Changes in working directory:**

```
$ git status
```

**Changes to tracked files:**

```
$ git diff
```

**See changes/difference of a specific file:**

```
$ git diff <file>
```

**Add all current changes to the next commit:**

```
$ git add .
```

**Add some changes in <file> to the next commit:**

```
$ git add -p <file>
```

**Commit all local changes in tracked files:**

```
$ git commit -a
```

**Commit previously staged changes:**

```
$ git commit
```

**Commit with message:**

```
$ git commit -m 'message here'
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
