# Git Branching and Merging
- [Introduce the concept of remote repositories.](#introduce-the-concept-of-remote-repositories)
- [Discuss commands like git clone, git push, and git pull](#discuss-commands-like-git-clone-git-push-and-git-pull)
- [Explain the concept of branches and their importance.](#explain-the-concept-of-branches-and-their-importance)
- [Demonstrate creating, switching, and deleting branches.](#demonstrate-creating-switching-and-deleting-branches)
- [Discuss the merging process in Git.](#discuss-the-merging-process-in-git)

## Introduce the concept of remote repositories.
## Discuss commands like git clone, git push, and git pull
### `git clone`
is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository. In this page we'll discuss extended configuration options and common use cases of `git clone`.<br>
**Cloning to a specific folder**<br>
`git clone <repo> <directory>`<br>

**Cloning a specific tag**<br>
`git clone --branch <tag> <repo>`<br>
Clone the repository located at `＜repo＞` and only clone the ref for `＜tag＞`.

### `git push`
The `git push` command is used to upload local repository content to a remote repository. Pushing is how you transfer commits from your local repository to a remote repo. It's the counterpart to` git fetch`, but whereas fetching imports commits to local branches, pushing exports commits to remote branches. Remote branches are configured using the git remote command. Pushing has the potential to overwrite changes, caution should be taken when pushing. These issues are discussed below.<br>

**Git push usage**<br>
`git push <remote> <branch>`<br>
Push the specified branch to , along with all of the necessary commits and internal objects. This creates a local branch in the destination repository. To prevent you from overwriting commits, Git won’t let you push when it results in a non-fast-forward merge in the destination repository.<br>

`git push <remote> --force`
Same as the above command, but force the push even if it results in a non-fast-forward merge. Do not use the --force flag unless you’re absolutely sure you know what you’re doing.<br>
Push all of your local branches to the specified remote.<br>

`git push <remote> --tags`<br>
Tags are not automatically pushed when you push a branch or use the `--all` option. The `--tags` flag sends all of your local tags to the remote repository.

### `git pull`
The `git pull` command is used to fetch and download content from a remote repository and immediately update the local repository to match that content. Merging remote upstream changes into your local repository is a common task in Git-based collaboration work flows.<br>
The `git pull` command is actually a combination of two other commands, `git fetch` followed by `git merge`. In the first stage of operation `git pull` will execute a git fetch scoped to the local branch that `HEAD` is pointed at. Once the content is downloaded, `git pull` will enter a merge workflow. A new merge commit will be-created and `HEAD` updated to point at the new commit.<br>

**Common Options**<br>
`git pull <remote>`
***
## Explain the concept of branches and their importance.
Git branches are effectively a pointer to a snapshot of your changes. When you want to add a new feature or fix a bug—no matter how big or how small—you spawn a new branch to encapsulate your changes.<br>
A branch represents an independent line of development. Branches serve as an abstraction for the edit/stage/commit process. You can think of them as a way to request a brand new working directory, staging area, and project history. New commits are recorded in the history for the current branch, which results in a fork in the history of the project.

## Demonstrate creating, switching, and deleting branches.

`git branch`
List all of the branches in your repository. This is synonymous with git branch --list.

`git branch <branch>`
Create a new branch called ＜branch＞. This does not check out the new branch.

`git branch -d <branch>`
Delete the specified branch. This is a “safe” operation in that Git prevents you from deleting the branch if it has unmerged changes.

`git branch -D <branch>`
Force delete the specified branch, even if it has unmerged changes. This is the command to use if you want to permanently throw away all of the commits associated with a particular line of development.

`git branch -m <branch>`
Rename the current branch to ＜branch＞.

`git branch -a`
List all remote branches.

`git checkout -b ＜new-branch＞`
The above example simultaneously creates and checks out ＜new-branch＞.


`git checkout ＜branchname＞`
Switching branches is a straightforward operation. Executing the following will point HEAD to the tip of ＜branchname＞.
## Discuss the merging process in Git.