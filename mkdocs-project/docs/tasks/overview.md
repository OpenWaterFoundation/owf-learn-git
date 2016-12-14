# Common Git Tasks / Overview

This documentation provides guidance on common tasks that are simple enough to run on the command line.

The following are helpful cheat sheets:

* [GitHub Git Cheat Sheet](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf)

The following is a list of common tasks that are explained below.
Most of these tasks use the Git command line such as Git BASH.

* [Determine whether remote repository is ahead of local](#task-determine-whether-remote-repository-is-ahead-of-local)
* [Unstage file(s) that should not be committed](#task-unstage-filess-that-should-not-be-committed)

## Task - Determine whether remote repository is ahead of local

**Scenario**:  You are collaborating with another developer and want to know if the remote repository
is ahead of the local repository, meaning does the remote have commits that are not in the local.
You want to know because you will need to do a `git pull` or `git fetch` and then `git merge` to get caught up.

**Solution:**

* See [Stack Overflow article "Check if pull needed in git"](http://stackoverflow.com/questions/3258243/check-if-pull-needed-in-git)
* See [Git Book - Git Basics - Working with Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)

First, a simple status check on the local repository checked out branch will only indicate if local changes need to be committed,
not that remote changes need to be pulled:

```bash
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

To get an overview of the remote repository:


```bash
# To inspect the origin
$ git remote show origin
* remote origin
  Fetch URL: https://github.com/OpenWaterFoundation/cdss-app-snodas-tools.git
  Push  URL: https://github.com/OpenWaterFoundation/cdss-app-snodas-tools.git
  HEAD branch: master
  Remote branch:
    master tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local ref configured for 'git push':
    master pushes to master (local out of date)
```

To list how many commits are different between the remote `origin/master` and the local `HEAD` branch:

```bash
$ git rev-list HEAD...origin/master --count
2
```

Do the following to bring the remote repository references up to date locally and then check whether the remote is ahead.
Note that as per a [Stack Overflow article](http://stackoverflow.com/questions/2688251/what-is-the-difference-between-git-fetch-origin-and-git-remote-update-origin)
`git remote update` is equivalent to `git fetch -all`.


```bash
# 1) First use the following to bring remote references up to date
git remote update
$ git remote update
Fetching origin
remote: Counting objects: 13, done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 13 (delta 4), reused 12 (delta 3), pack-reused 0
Unpacking objects: 100% (13/13), done.
From https://github.com/OpenWaterFoundation/cdss-app-snodas-tools
   cce3321..4016452  master     -> origin/master


# 2a) Then list whether the current branch is up to date
git status -uno
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean


# 2b) OR, to show commits in all of the branches whose names end in `master` (such as `master` and `origin/master`):
git show-branch *master
$ git status -uno
On branch master
Your branch is behind 'origin/master' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
nothing to commit (use -u to show untracked files)
```

## Task - Unstage files(s) that should not be committed

**Scenario**:  You ran `git add...` and some files were added to the staging area that should not have been.
You removed the files, added to `.gitignore` etc. but need to make sure they won't get committed.

**Solution:**

* See [Stack Overflow article answer by Max summarized below](http://stackoverflow.com/questions/19730565/how-to-remove-files-from-git-staging-area)
* See [git rm](https://git-scm.com/docs/git-rm)

```bash
# To recursively remove files in a folder that was added:
git rm --cached -r theFolder
# To remove speciic files that were added:
git rm --cached filename1 filename2
```

Can also use `--dry-run` to see what will be done.
