# Understanding the `git` Push, Fetch, and Pull Commands

The concepts in this article can help you understand how the `git push`, `git pull`, and `git fetch` commands update your local and remote source control repositories:

- `git push` - Send any changes from your local branch to a remote repository.
- `git fetch` - Bring any changes from a remote repository branch to your local repository.
- `git pull` - Gather changes from a remote branch and merge them into a local branch.

This article also attempts to clarify how `git push` and `git fetch` are logical opposites, while `git pull` combines two tasks.

## How `git push` Updates a Remote Repository

When you run the `git push` command, `git` checks if there is a tracking branch for the default remote repository (you can set multiple remote repositories). If so, `git` sends any local changes as commits to the remote branch. You may think of this process as making the remote branch resemble your local branch.

To update the remote repository, the history between the remote and your local repository must be similar other than any recent changes (those you have made). Updating the remote repository can fail if the commit histories of your local branch and the remote branch are incompatible. For example, your local branch may have more recent commits than the remote, but the commits prior to those must be similar on the two versions of the repository. In this case, you must take steps to update your local branch with the remote branch.

## How `git fetch` Updates Your Local Repository

The `git fetch` command checks for any changes in the remote repository for the tracking branch  and updates your local repository branch with those remote changes. The update does not change your working directory or modify your `git` index (the `git` staging area).

To update your working directory with the fetched repository changes use `git merge <REMOTE-NAME>/<BRANCH-NAME>`.

## How `git pull` Updates Your Working Directory

The `git pull` command combines functions by calling `git fetch` and then `git merge`. Because the changes you fetch can sometimes clobber your local working directory contents, you may prefer to fetch and review changes before you merge them.
