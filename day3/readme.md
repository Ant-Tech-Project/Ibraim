# Confict Resolution
- [What can cause a conflict? ](#what-can-cause-a-conflict)
- [Cover strategies for conflict resolution](#cover-strategies-for-conflict-resolution)
- [Work in pairs: Create a new repo, create a conflict and practice conflict resolution](#work-in-pairs-create-a-new-repo-create-a-conflict-and-practice-conflict-resolution)
- [provide a step-by-step instruction for how to resolve a conflict](#provide-a-step-by-step-instruction-for-how-to-resolve-a-conflict)

## What can cause a conflict? 
If the two branches you're trying to merge both changed the same part of the same file, Git won't be able to figure out which version to use. When such a situation occurs, it stops right before the merge commit so that you can resolve the conflicts manually.

The great part of Git's merging process is that it uses the familiar edit/stage/commit workflow to resolve merge conflicts. When you encounter a merge conflict, running the git status command shows you which files need to be resolved. For example, if both branches modified the same section of hello.py, you would see something like the following:
```git
On branch main
Unmerged paths:
(use "git add/rm ..." as appropriate to mark resolution)
both modified: hello.py
```

## Cover strategies for conflict resolution
## Work in pairs: Create a new repo, create a conflict and practice conflict resolution
## provide a step-by-step instruction for how to resolve a conflict