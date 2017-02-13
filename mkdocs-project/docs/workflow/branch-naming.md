# Git Workflow / Branch Naming

Branching naming conventions are important to ensure communication within a software project.
General naming conventions will be imposed by the Git software (e.g., "master") and the Git workflow
that is selected by the core software development team (e.g., "stable" branch might be used for software releases).

Branches that will generally not be public will have less of a chance to cause issues during collaboration,
especially if the branches are never pushed to a cloud repository.
However, the branch name will often show up in commit messages and therefore it is helpful to adopt a minimal naming convention.

Assume that issues (requests and bug reports) are tracked in an issue tracker such as GitHub's issue tracker.
Each issue will then have an issue number.
Including the issue number in the branch name will ensure that a connection can be made between the branch
and various issue artifacts.

The following are properties that might be added to a branch name, with some discussion of pros and cons.
The development team and workflow for a project will determine what works best.

* use dashes between branch name parts
	+ See [Stack Overflow: Using slash character in Git branch name](http://stackoverflow.com/questions/2527355/using-the-slash-character-in-git-branch-name/2527452#2527452) - there
	are some known issues with using `/` so be safe and use a dash
* issue type
	+ using an issue type such as `feature`, `bug`, `hotfix`, `test`, `refactor`, etc. may be helpful
	+ however, an issue may evolve from bug to feature so assigning a type may be confusing
* issue number
	+ need this at a minimum to link to the issue tracker, consistent with GitHub, Bitbucket, etc. features
* developer ID
	+ not recommended because it can be found in the issue tracker, more than one person may work on the issue,
	and the assignment of a lead developer may change over time
* topic
	+ it may be helpful to include a short topic to help quickly understand the focus of the issue and not get lost in issue numbers

Examples of suitable branch names are:

* `1234`
* `1234-fix-main-menu`
* `bug-1234-crash-at-start`

Again, the approach adopted should be determined based on what works for the team.
