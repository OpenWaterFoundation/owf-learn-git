# Common Git Tasks / Overview

This documentation provides guidance on common tasks that are simple enough to run on the command line.

## Git Cheat Sheet

The following are helpful cheat sheets:

* [GitHub Git Cheat Sheet](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf)

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
