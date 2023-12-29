Git Commands
=====================

Git Cheat Sheet
---------------------

This cheat sheet summarizes commonly used Git command line instructions for quick reference.

## Install

* GitHub for Windows - <https://windows.github.com>
* GitHub for Mac - <https://mac.github.com>
* Git for All Platforms - <http://git-scm.com>

Git distributions for Linux and POSIX systems are available on the official Git SCM web site.

## Configue Tooling

| Command | Description |
| ------- | ----------- |
| `git config --global user.name "[name]"` | Sets the name you want attached to your commit transactions |
| `git config --global user.email "[email address]"` | Sets the email you want attached to your commit transactions |
| `git config --global color.ui auto` | Enables helpful colorization of command line output |

## Branches

Branches are an important part of working with Git. Any commits you make will be made on the branch you're currently “checked out” to. Use git status to see which branch that is.

| Command | Description |
| ------- | ----------- |
| `git branch [branch-name]` | Creates a new branch |
| `git checkout [branch-name]` | Switches to the specified branch and updates the working directory |
| `git merge [branch]` | Combines the specified branch’s history into the current branch. This is usually done in pull requests, but is an important Git operation. |
| `git branch -d [branch-name]` | Deletes the specified branch |

## Create repositories

When starting out with a new repository, you only need to do it once; either locally, then push to GitHub, or by cloning an existing repository.

| Command | Description |
| ------- | ----------- |
| `git init` | Turn an existing directory into a git repository |
| `git clone [url]` | Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits |
| `git clone --branch <branchname> <remote-repo-url>` or `git clone -b <branchname> <remote-repo-url>` | Clone a specific branch |

## The .gitignore file

Sometimes it may be a good idea to exclude files from being tracked with Git. This is typically done in a special file named .gitignore . You can find helpful templates for .gitignore files at <https://github.com/github/gitignore>

## Synchronize changes

Synchronize your local repository with the remote repository on GitHub.com

| Command | Description |
| ------- | ----------- |
| `git fetch` | Downloads all history from the remote tracking branches |
| `git merge` | Combines remote tracking branch into current local branch |
| `git push` | Uploads all local branch commits to GitHub |
| `git pull` | Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. `git pull` is a combination of `git fetch` and `git merge` |

## Make changes

Browse and inspect the evolution of project files.

| Command | Description |
| ------- | ----------- |
| `git log` | Lists version history for the current branch |
| `git log --follow [file]` | Lists version history for a file, including renames |
| `git diff [first-branch]...[second-branch]` | Shows content differences between two branches |
| `git show [commit]` | Outputs metadata and content changes of the specified commit |
| `git add [file]` | Snapshots the file in preparation for versioning |
| `git commit -m "[descriptive message]"` | Records file snapshots permanently in version history |

## Redo commits

Erase mistakes and craft replacement history

| Command | Description |
| ------- | ----------- |
| `git reset [commit]` | Undoes all commits after [commit], preserving changes locally |
| `git reset --hard [commit]` | Discards all history and changes back to the specified commit |

> [!WARNING] 
> Changing history can have nasty side effects. If you need to change commits that exist on GitHub (the emote), proceed with caution. If you need help, reach out at github.community or contact support.

## Git flow

In the diagram below, you can see the basic pattern of git flow. Essentially, it gives you a few different things that don’t come out of the box with git. There’s a way to fix production code, work on new things, and even prepare for deployments.

![Git-flow diagram](/assets/img/git-flow.png "Git-flow diagram")

#### Master
-----------
This is production code - simple as that. The big change that git flow adds to the mix is that you don’t actually code ever on master. Everything here is done via merging or pull requests. This ensures that your code has gone through the process and is ready to go!

#### Hotfix
-----------
Need to fix production? Easy, start a hotfix branch and code away. When you’re done something different happens, a double merge - one into master and one into develop, ensuring that the bug you just squashed does not come back!

#### Develop
------------
This branch-like master is not committed on directly, it is a direct copy of the master branch when you enable it though. This is a one time thing, so keeping the pattern will ensure that the branches stay synced together. Merges will happen to it from both hotfix and feature branches - develop acts as an integration branch to that extent. The beauty of this is that all of the code comes together before a deployment, saving you time and lots of unneeded stress.

#### Feature
------------
This is the closest to normal git branching as you will get in git flow. Essentially, it’s a place to try out and implement new functionality. This is great, because you can have virtually unlimited features in progress and never have to worry about them breaking the main branches. On that note, you really want to start and end a feature as quickly as possible to avoid merge conflicts, because no one like them.

#### Release
------------
This is one of the greatest built-in features of the git flow pattern. This gives you a place to start staging your release to production. While that is awesome on its own, it like hotfix has a double merge at the end of it. This means that if a bug or other issue is found during a release you can still fix it and have that code automatically flow into both your master and develop branches.

## Glosary

| Term | Definition |
| ------- | ----------- |
| **git** : | an open source, distributed version-control system |
| **GitHub** : | a platform for hosting and collaborating on Git repositories |
| **commit** : | a Git object, a snapshot of your entire repository compressed into a SHA |
| **branch** : | a lightweight movable pointer to a commit |
| **clone** : | a local version of a repository, including all commits and branches |
| **remote** : | a common repository on GitHub that all team member use to exchange their changes |
| **fork** : | a copy of a repository on GitHub owned by a different user |
| **pull request** : | a place to compare and discuss the differences introduced on a branch with reviews, comments, integrated tests, and more |
| **HEAD** : | representing your current working directory, the HEAD pointer can be moved to different branches, tags, or commits when using git checkout |

## Helpful links

- https://git-scm.com/docs - Git Official Documentation.
- https://training.github.com/downloads/github-git-cheat-sheet.pdf - Git Cheat Sheet.
- https://www.campingcoder.com/2018/04/how-to-use-git-flow - How to use Git flow.
- https://git-scm.com/book/en/v2 - Git Pro Book.
