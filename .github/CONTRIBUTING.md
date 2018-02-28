# How to Contribute

## UCSD Library Development Team
Please use the following process for creating a new [Pull Request](https://help.github.com/articles/using-pull-requests "Pull Request").

1. Create a feature branch for new work.
1. Push commits to the feature branch, with appropriate test coverage (and tests passing).
1. Prior to creating a Pull Request, make sure your branch is up to date with its parent branch (usually `develop`)
```
git checkout develop
git pull --rebase
git checkout <your-feature-branch>
git rebase develop
```
1. Run your tests again.
1. Push your changes to a remote branch. If you already have pushed your feature branch to Github, you may have to use the  
`git push --force-with-lease origin <your-feature-branch>` option instead.
1. Create a pull request by going to the branch in github (e.g. https://github.com/ucsdlib/horton/tree/branchname/) and clicking on the pull request button (green arrows going in a circle). Make sure the PR can be merged automatically, if it can't go back to Step 3.
1. Give the pull request a short meaningful title, and put a link to the relevant Github issue (following the ISSUE_TEMPLATE syntax).
1. The entire `@ucsdlib/developers` team has an opportunity to review. At least
   one Review needs to be approved. Ideally, two people will sign off.

## Merging Changes from Pull Requests

* Please take the time to review the changes and get a sense of what is being changed. Things to consider:
  * Does the commit message explain what is going on?
  * Does the code changes have tests? _Not all changes need new tests, some changes are refactorings_
  * Does the commit contain more than it should? Are two separate concerns being addressed in one commit?
* Do all tests pass successfully?
* If you are uncertain, bring other contributors into the conversation by creating a comment that includes their @username.
* If you like the pull request, but want others to chime in, create a +1 comment and tag a user.
