# Git Resources

Need to list here useful Git resources including third-party cheat sheets,
template .gitignore and .gitattribute files in GitHub.

**TODO smalers 2017-01-16 maybe include this in overview**

This documentation includes the following sections:

* [Bash Utilities](#bash-utilities)
	+ [Auto-Completion](#auto-completion)
	+ [Set Prompt to Indicate Repository Information](#set-prompt-to-indicate-repository-information)

## Bash Utilities

The following are useful Bash utilities.
Note that the utilities may need to be configured multiple times depending on development environment,
for example for Cygwin, Linux, Git Bash.

### Auto-Completion

To enable auto-completion of Git commands, use the `git-competion.bash` script.  See:

* [Git Basics - Tips and Tricks](https://git-scm.com/book/en/v1/Git-Basics-Tips-and-Tricks)


### Set Prompt to Indicate Repository Information

It can be confusing to know what branch is being edited with command-line tools,
especially after being away from a project awhile.  The `git-prompt` bash script can help:o

* [git-prompt.sh](https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh)
