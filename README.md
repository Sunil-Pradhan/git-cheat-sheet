# Git Cheat Sheet

![my certification](/images/Git-Cheat-Sheet-Banner.png)

Git cheat sheet saves you from learning all the commands by heart. Be free to contribute, update the grammar mistakes. 

## Table of Contents
* [Setup](#setup)
* [Create](#Create)


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
