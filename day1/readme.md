# Introduction to Version Control and Git Basics
- [Define version control](#define-version-control) 
- [Explain the purpose and features of Git](#explain-the-purpose-and-feature-of-git)
- [Discuss the drawbacks of not using version control](#discuss-the-drawbacks-of-not-using-version-control)
- [Discuss the difference between centralized and distributed version control](#discuss-the-difference-between-centralized-and-distributed-version-control)
- [How to install Git on different operating systems?](#how-to-install-git-on-different-operating-systems)
- [Introduce fundamental commands such as git init, git add, git commit](#introduce-fundamental-commands-such-as-git-init-git-add-git-commit)
- [Explain the concept of the staging area](#explain-the-concept-of-the-staging-area)
***
## Define Version Control
Version control, also known as source control, is the practice of tracking and managing changes to software code. 
Version control systems are software tools that help software teams manage changes to source code over time.
***
## Explain the purpose and feature of Git
Git is destributed version control system. It is free and open-source.It is primarily used for tracking changes in source code during software development.
#### Features of Git
- Free and open source
- Supports non-linear development
- Creates Backups
- Scalable 
- Easy Branching
- Distributed Development.
***
## Discuss the drawbacks of not using version control

## Discuss the difference between centralized and distributed version control
| Centralized | Distributed  |
|:---|:---|
|CVCS is a traditional version control system where the source code is stored in a central server maintained by a single authority. Developers check out the code they need to work on and make changes directly to that codebase. Once the changes are made, they commit the code back to the central server.| DVCS is an evolution of version control systems that address the limitations of CVCS by allowing developers to create local copies of the code repository, complete with the entire history. Each developer has a full copy of the repository on their local machine, including the change history.|
|<img src="https://media.licdn.com/dms/image/D5612AQFqbZTR8Q1V5A/article-inline_image-shrink_1500_2232/0/1696544144712?e=1712793600&v=beta&t=14uufiOn78XzZHdCOqewrW5TiynqWdbhNzEV-J8Ox4s" alt="staging area" style="width:500px;"/>|<img src="https://media.licdn.com/dms/image/D5612AQF7c-D-KQtdxQ/article-inline_image-shrink_1500_2232/0/1696544158348?e=1712793600&v=beta&t=U7wXbLlV4uBsGY-0xB0VERaTFfhlOuohck51_4O3nqE" alt="staging area" style="width:500px;"/> |

## How to install Git on different operating systems?
|Installation| |
|:---|:---|
|Linux|`sudo dnf install git-all` or `sudo apt install git-all`|
|Windows|you can use `choco install git`|
|MacOS|`brew install git`|
## Introduce fundamental commands such as git init, git add, git commit
|Command|What it does|
|:---:|:---|
|git init|The `git init` command creates a new Git repository. It can be used to convert an existing, unversioned project to a Git repository or initialize a new, empty repository. Most other Git commands are not available outside of an initialized repository, so this is usually the first command you'll run in a new project.|
|git add|The `git add` command adds a change in the working directory to the staging area. It tells Git that you want to include updates to a particular file in the next commit.<br> However, git add doesn't really affect the repository in any significant way—changes are not actually recorded until you run git commit.|
|git commit|The `git commit` command captures a snapshot of the project's currently staged changes. Committed snapshots can be thought of as “safe” versions of a project—Git will never change them unless you explicitly ask it to.|

## Explain the concept of the staging area
#### Staging area 
The primary function of the git add command, is to promote pending changes in the working directory, to the git staging area. The staging area is one of Git's more unique features, and it can take some time to wrap your head around it if you’re coming from an SVN (or even a Mercurial) background. It helps to think of it as a buffer between the working directory and the project history. The staging area is considered one of the "three trees" of Git, along with, the working directory, and the commit history.

Instead of committing all of the changes you've made since the last commit, the stage lets you group related changes into highly focused snapshots before actually committing it to the project history. This means you can make all sorts of edits to unrelated files, then go back and split them up into logical commits by adding related changes to the stage and commit them piece-by-piece. As in any revision control system, it’s important to create atomic commits so that it’s easy to track down bugs and revert changes with minimal impact on the rest of the project.
<img src="https://www.devopsuniversity.org/wp-content/uploads/2021/01/git-repository.jpg" alt="staging area" style="width:500px;" style="margin-left:250px;"/>
