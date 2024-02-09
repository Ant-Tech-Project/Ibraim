# Confict Resolution
- [What can cause a conflict? ](#what-can-cause-a-conflict)
- [Cover strategies for conflict resolution](#cover-strategies-for-conflict-resolution)
- [Work in pairs: Create a new repo, create a conflict and practice conflict resolution](#work-in-pairs-create-a-new-repo-create-a-conflict-and-practice-conflict-resolution)
- [provide a step-by-step instruction for how to resolve a conflict](#provide-a-step-by-step-instruction-for-how-to-resolve-a-conflict)

## What can cause a conflict? 
**Merge conflicts happen when you merge branches that have competing commits, and Git needs your help to decide which changes to incorporate in the final merge.**

If the two branches you're trying to merge both changed the same part of the same file, Git won't be able to figure out which version to use. When such a situation occurs, it stops right before the merge commit so that you can resolve the conflicts manually.

The great part of Git's merging process is that it uses the familiar edit/stage/commit workflow to resolve merge conflicts. When you encounter a merge conflict, running the git status command shows you which files need to be resolved. For example, if both branches modified the same section of hello.py, you would see something like the following:
```bash
On branch main
Unmerged paths:
(use "git add/rm ..." as appropriate to mark resolution)
both modified: hello.py
```
### Types of merge conflicts
1. **Git fails to start the merge**<br>
A merge will fail to start when Git sees there are changes in either the working directory or staging area of the current project. Git fails to start the merge because these pending changes could be written over by the commits that are being merged in. When this happens, it is not because of conflicts with other developer's, but conflicts with pending local changes. The local state will need to be stabilized using `git stash`, `git checkout`, `git commit` or `git reset`. 
```bash
error: Entry '<fileName>' not uptodate. Cannot merge. (Changes in working directory)
```
2. **Git fails during the merge**<br>
A failure DURING a merge indicates a conflict between the current local branch and the branch being merged. This indicates a conflict with another developers code. Git will do its best to merge the files but will leave things for you to resolve manually in the conflicted files.
```bash
error: Entry '<fileName>' would be overwritten by merge. Cannot merge. (Changes in staging area)
```

## Cover strategies for conflict resolution

There are a few steps that could reduce the steps needed to resolve merge conflicts in Git.

- Step 1: The easiest way to resolve a conflicted file is to open it and make any necessary changes.

- Step 2: After editing the file, we can use the git add a command to stage the new merged content.

- Step 3: The final step is to create a new commit with the help of the git commit command.

- Step 4: Git will create a new merge commit to finalize the merge.