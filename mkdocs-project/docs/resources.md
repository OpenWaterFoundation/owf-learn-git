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

The recommendation is to put the following in the software developer's `.bashrc` file.
The following calls the `git-prompt` and `git-completion.bash` scripts that are described in the following two sections.
Local modifications can be made by the developer.

```
# Enable tab completion
source ~/bin/git-completion.bash

# Enable git-aware command prompt.
# See:  http://tldp.org/HOWTO/Bash-Prompt-HOWTO/x329.html
# https://tiswww.case.edu/php/chet/bash/bashref.html#Controlling-the-Prompt
cyan="\[\033[0;36m\]"
blue="\[\033[0;34m\]"
green="\[\033[0;32m\]"
lightblue="\[\033[1;34m\]"
pink="\[\033[0;31m\]"
purple="\[\033[0;35m\]"
white="\[\033[1;37m\]"
yellow="\[\033[1;33m\]"
# reset switches back to regular color
reset="\[\033[0m\]"

# Change command prompt
source ~/bin/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=1
# '\u' adds the name of the current user to the prompt
# '\$(__git_ps1)' adds git-related stuff
# '\W' adds the name of the current directory
# Prompt will be:
#  user (branch) directory $
# where branch may be followed by:
#  * if unstaged files
#  + if staged files
export PS1="$white\u$lightblue\$(__git_ps1)$yellow \W $ $reset"
# END GIT INSERT
```

### Auto-Completion

To enable auto-completion of Git commands, use the `git-competion.bash` script.  See:

* [Git Basics - Tips and Tricks](https://git-scm.com/book/en/v1/Git-Basics-Tips-and-Tricks)


### Set Prompt to Indicate Repository Information

It can be confusing to know what branch is being edited with command-line tools,
especially after being away from a project awhile.  The `git-prompt` bash script can help:o

* [git-prompt.sh](https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh)
