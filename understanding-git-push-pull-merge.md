# Understanding the `git` Push, Pull, and Fetch Commands

The concepts in this article can help you understand how the `git push`, `git pull`, and `git fetch` commands update your local and remote source control repositories:

- `git push` - Send any changes from your local branch to a remote repository.
- `git fetch` - Bring any changes in a remote repository branch to your local repository.
- `git pull` - Runs `git fetch` to gather changes from a remote branch and merges them into a local branch.

This article also attempts to clarify how `git push` and `git fetch` are logical opposites, while `git pull` combines two tasks.

## How `git push` Updates a Remote Repository

When you run the `git push` command, `git` checks if there is a tracking branch for the default remote repository (you can set multiple remote repositories). If so, `git` sends any local changes as commits to the remote branch. You may think of this process as making the remote branch resemble your local branch.

To update the remote repository, the history between the remote and your local repository must be similar other than any recent changes (those you have made). Updating the remote repository can fail if the commit histories of your local branch and the remote branch are incompatible. For example, your local branch may have more recent commits than the remote, but the commits prior to those must be similar on the two versions of the repository. In this case, you must take steps to update your local branch with the remote branch.


`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.
