# Git Workflow / Overview

Git "workflow" refers to the day-to-day steps that occur to modify and add content in a Git repository.
The workflow model focus on naming conventions for branches and processes to branch and merge.
The workflow model that is chosen will depend on the size of the team and protocols for branching/merging,
testing, and releasing software.

This documentation includes the following sections:

* Git Workflow Approaches
	+ Resources:
		- [See discussion in Git in Practice by Mike McQuaid](https://www.manning.com/books/git-in-practice)
		- [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/) - often-referenced model by Vincent Driessen
		- [Jeremy Helms Gist on Branching](https://gist.github.com/digitaljhelms/4287848) - the above, with some different naming conventions
	+ [Feature Branch](feature-branch) - simple approach to use feature/bug fix branches off of master
	+ [Git Flow](git-flow) - comprehensive implementation of Vincent Driessen's model with helper scripts
* [Branch Naming](branch-naming)
* Merging
	+ Resources:
		- [Git Branching - Basic Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
		- [Fast-Forward Git Merge](https://ariya.io/2013/09/fast-forward-git-merge) - explanation of fast-forward merge (and why it may not be desirable)
		- [Atlassian tutorial:  Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
		- [Atlassian article:  Git team workflows: merge or rebase](https://www.atlassian.com/git/articles/git-team-workflows-merge-or-rebase) - useful information on rebasing/merging
	+ [Merge via Issue Suggestion](merge-via-issue-suggestion) - developer responds to a suggestion on an issue
	+ [Merge via Change Set](merge-via-change-set) - contributor provides suggested changes via a change set email
	+ [Merge via Pull Request](merge-via-pull-request) - contributor provides suggested changes via a pull request
* Continuous Integration (**TODO smalers 2017-02-12 need to add**)
