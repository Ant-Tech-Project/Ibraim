# Git Branching and Merging
- [Introduce the concept of remote repositories.](#introduce-the-concept-of-remote-repositories)
- [Discuss commands like git clone, git push, and git pull](#discuss-commands-like-git-clone-git-push-and-git-pull)
- [Explain the concept of branches and their importance.](#explain-the-concept-of-branches-and-their-importance)
- [Demonstrate creating, switching, and deleting branches.](#demonstrate-creating-switching-and-deleting-branches)
- [Discuss the merging process in Git.](#discuss-the-merging-process-in-git)

## Introduce the concept of remote repositories.
To be able to collaborate on any Git project, you need to know how to manage your remote repositories. Remote repositories are versions of your project that are hosted on the Internet or network somewhere. You can have several of them, each of which generally is either read-only or read/write for you. Collaborating with others involves managing these remote repositories and pushing and pulling data to and from them when you need to share work. Managing remote repositories includes knowing how to add remote repositories, remove remotes that are no longer valid, manage various remote branches and define them as being tracked or not, and more. 

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

To delete a remote branch execute the following.

`git push origin --delete crazy-experiment` or `git push origin :crazy-experiment`

`git branch -m <branch>`
Rename the current branch to ＜branch＞.

`git branch -a`
List all remote branches.

`git checkout -b ＜new-branch＞`
The above example simultaneously creates and checks out ＜new-branch＞.

`git checkout ＜branchname＞`
Switching branches is a straightforward operation. Executing the following will point HEAD to the tip of ＜branchname＞.
## Discuss the merging process in Git.
Merging is Git's way of putting a forked history back together again. The `git merge` command lets you take the independent lines of development created by `git branch` and integrate them into a single branch.

<p align="center">
<img src="https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=1434" alt="merge"  margin="250px" style="width:500px;"/>
</p>

### Fast Forward Merge
<p align="center">
<img src="https://wac-cdn.atlassian.com/dam/jcr:d90f2536-7951-4e5e-ab79-f45a502fb4c8/03-04%20Fast%20forward%20merge.svg?cdnVersion=1434" alt="merge"   background-color="white" margin="250px" style="width:500px;"/>
</p>

`git merge --no-ff <branch>`
This command merges the specified branch into the current branch, but always generates a merge commit (even if it was a fast-forward merge). This is useful for documenting all merges that occur in your repository.

### 3 Way Merge
<p align="center">
<img src="https://wac-cdn.atlassian.com/dam/jcr:91aece4a-8fa0-4fc3-bae9-69d51932f104/05-06%20Fast%20forward%20merge.svg?cdnVersion=1434" alt="merge"  margin="250px" style="width:500px;"/>
</p>