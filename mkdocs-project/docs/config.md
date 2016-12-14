# Configure Git

Once Git has been installed it is necessary to set a few configuration properties.
The configuration steps will need to be repeated for each operating system, including each virtual machine,
and potentially for each tool if software stores Git configuration in different locations
(it is important as a software developer to know which Git configuration file(s) a software tool uses,
especially if the standard configuration files are not used).
Several configuration properties are set by default - only important changes are discussed here.
See:

* [Getting Started - First Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

Global configuration properties are typically saved in a hidden file named `.gitconfig` in the user's home folder
(`~/.gitconfig` on Linux and Cygwin and `C:\Users\userName\.gitconfig` on Windows), for example on Cygwin:

```ini
[user]
        name = Steve Malers
        email = steve.malers@openwaterfoundation.org
[color]
        ui = auto
[core]
        editor = vim
[merge]
        conflictstyle = diff3
[push]
        default = upstream

```

Configuration values are also saved in a repository file `.git/config`, for example as shown below.
Note that in this case some properties are used to indicate the remote (cloud) repository that is upstream of the local repository.


```
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        ignorecase = true
[remote "origin"]
        url = https://github.com/OpenWaterFoundation/owf-learn-git.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
        remote = origin
        merge = refs/heads/master

```

To list settings from the local repository and global (user) configuration file:

```
git config --list
```

## Set Global Configuration Properties

The following documentation summarizes how to set global Git configuration properties after installing software:

* [Getting Started - First Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

Typical configuration includes:

```
git config --global user.name “Joe Smith”
git config --global user.email joe.smith@yourorganization.com
git config --global core.editor someeditor

git config --list

user.name=Joe Smith
user.email=joe.smith@yourorganization.com
color.ui=auto
core.editor=vim
merge.conflictstyle=diff3
push.default=upstream

```
