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

### Udacity Training

Use of the `git-completion.sh` and `git-prompt.sh` tools was described in the following Udacity Git training course:

* [Udacity:  How to Use Git and GitHub](https://www.udacity.com/course/how-to-use-git-and-github--ud775)

The recommendation is to put the following in the `.bash_profile` consistent with the scripts in the following sections.
Local modifications can be made as per preferences.

```
# START UDACITY GIT COURSE INSERT .bash_profile_course
# Enable tab completion
source ~/bin/git-completion.bash

# colors!
green="\[\033[0;32m\]"
blue="\[\033[0;34m\]"
purple="\[\033[0;35m\]"
reset="\[\033[0m\]"

# Change command prompt
source ~/bin/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=1
# '\u' adds the name of the current user to the prompt
# '\$(__git_ps1)' adds git-related stuff
# '\W' adds the name of the current directory
export PS1="$purple\u$green\$(__git_ps1)$blue \W $ $reset"
# END UDACITY GIT COURSE INSERT .bash_profile_course
```

### Auto-Completion

To enable auto-completion of Git commands, use the `git-competion.bash` script.  See:

* [Git Basics - Tips and Tricks](https://git-scm.com/book/en/v1/Git-Basics-Tips-and-Tricks)


### Set Prompt to Indicate Repository Information

It can be confusing to know what branch is being edited with command-line tools,
especially after being away from a project awhile.  The `git-prompt` bash script can help:o

* [git-prompt.sh](https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh)
