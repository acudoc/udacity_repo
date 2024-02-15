# One More Git Cheatsheet 

#### This document is study resources to prepare for the Github Foundation Certification.
Originally this repo started to house basic git commands. Recently I am adding my notes as I go through [this course](https://www.exampro.co/github-choose-an-exam) from Andrew Brown of ExamPro.

### Table of Contents

<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

- [Git Overview of Terms](#git-overview-of-terms)
- [Basic Commands ](#basic_commands)
   * [Create](#create)
     - [From existing repo](#from-existing-repo)
     - [From existing files](#from-existing-files)
   * [Commit](#commit)
    - [Commit only watches changes that have been marked explictly with add](#commit-only-watches-changes-that-have-been-marked-explictly-with-add)
   * [View](#view)
   * [Branches](#branches)
   * [Update](#update)
   * [Remote](#remote)
- [This describes a new commit that undoes previous commits](#this-describes-a-new-commit-that-undoes-previous-commits)
* [Useful Tools](#useful-tools)
+ [Git Workflow](#git-workflow)

<!-- TOC end -->

![Octocat!](/images/cd_octocat_med.png "Octocat Flair!")

<!-- TOC --><a name="git-overview-of-terms"></a>
## Git Overview of Terms
- **Repository** (repo): Represents the container holding the codebase 
- **Commit**: Represents a change of data in the local repo.
- **Tree**: Represents the entire history of a repo.
- **Remote**: A version of your project hosted elsewhere, used for exchanging commits.
- **Branches**: Divergent paths of developement, allowing isolated changes.
- **Main** (formally known as Master): common name for default branch
- **Clone**: Creates a complete local copy of a repo, including its history.
- **Checkout**: Switches between different branches or commits in your repo.
- **Pull**: Downloads changes from remote repo and merges them into your branch
- **Push**: Uploads local repo changes to a remote repo.
- **Fetch**: Downloads data from remote repo without integrating it into your work
- **Reset**: Undoes local changes, with options to unstage or revert commits.
- **Merge**: Combines multiple commit histories into one.
- **Staging** files: Prepares and organizes for a commit.
    - Add: Adds changes to file or files bringing them to the staging area for the next commit.
    - Commit: Saves changes as a snapshot in the local repo

- To see the complete documentation follow [Links to Git Docs](https://git-scm.com/docs)
- If your in the wild and get stuck use `git help` [command]

<!-- TOC --><a name="basic_commands"></a>
### Basic Commands

```python
main      # default level branch
origin    # default upstream
HEAD      # current branch
HEAD^     # parent of HEAD
foo..bar  # from branch foo to branch bar
```

<!-- TOC --><a name="create"></a>
### Create

<!-- TOC --><a name="from-existing-repo"></a>
##### From existing repo

Three main ways to clone a repo
- HTTPS
- SSH
- Github CLI

It is possible to clone entire repo or a single branch

```python
git clone [URL] #bring repo from existing repo
git clone ~/old ~/new
git clone --single-branch
```

<!-- TOC --><a name="from-existing-files"></a>
##### From existing files

```python
git init`
git add my file #add file to repo from local to repo
git add . #add all files
git diff --staged #used after `git add` to review changes to code
```
<!-- TOC --><a name="commit"></a>
### Commit

<!-- TOC --><a name="commit-only-watches-changes-that-have-been-marked-explictly-with-add"></a>
##### Watches changes that have been marked explictly with add

```python
git commit -m "Commit Message" # add changes of repo to main branch
git commit -a -m "Com Message" # -a: automatically stages all tracked modified files before commit
git commit --amend # Modifies most recent commit
git commit -m "Initial Commit" --allow empty # Creates empty commit to act as placeholder
git commit -m "Message" --author="name <email@example.com>" # commit with specific author
git push # send local files to remote
git push -u origin # the -u sets upstream branch
```

<!-- TOC --><a name="view"></a>
### View

```python
git status # check local files to main github branch
git diff [oldid newid]
git log [-p] [file|dir]
git blame file
git show id
git show id:file
git branch # see branches
```

<!-- TOC --><a name="branches"></a>
### Branches
Can be created through
- Issues tab
- w/ GitHub UI
- w/ GitHub Desktop
- In terminal (below)
  
```python
git branch # Lists all local branches
git branch [branch-name] # creates new branch
git branch -m [old-name][new-name] # Rename a branch
git branch -d anybranch # with -d anybranch will be deleted
git branch -a # Lists both remote and local branches
git checkout [branch-name] # switchs to branch-name
git checkout -b newbranch # this creates and moves to new branch
git merge # branches together
```

<!-- TOC --><a name="update"></a>
### Update
```python
git pull # get latest changes from branch
git fetch [remote-name] # Fetch updates withour pulling
git apply patch.diff
```

<!-- TOC --><a name="remote"></a>
### Remote
```python
# Lists all remote repositories along with their URLs
git remote -v
git remote add [name] [URL]                
git remote remove [name]     
git remote rename [old-name] [new-name]
```
  
```pythoh
# Pushes a branch and its commits to the specific remote
git push [remote-name] [branch]
  
# Pull updates from a remote branch        
git pull [remote-name] [branch]
```          


<!-- TOC --><a name="this-describes-a-new-commit-that-undoes-previous-commits"></a>
##### This describes a new commit that undoes previous commits
```python
git reset --hard # NOT UNDONE, reset to last commit
git revert branch
git commit -a --amend # replaces prev commit
```

<!-- TOC --><a name="useful-tools"></a>
### Useful Tools

- `git log` *view log history*
- `git archive` *create release tarball*
- `git bisect` *binary search for defects*
- `git cherry-pick` *take single commit from elsewhere*
- `git fsck` *check tree*
- `git gc` *compress metadata <performance>*
- `git rebase` *forward-port local changes to remote branch* 
- `git remote add URL` *register new remote repo for tree*
- `git stash` *Temporarily set aside changes*



<!-- TOC --><a name="git-workflow"></a>
#### Git Workflows

>##### Simple Github Workflow Example
>
> - Create new branch
> - Add new feature and code
> - add, commit, and push changes to the remote
> - Get changes reviewed by team member
> - Delete remote branch
> - Delete local branch
> - Pull new code on the remote master to local machine
>

##### Workflow with commands

```bash
git checkout -b my-new-branch
# ... make changes to files 
git add .   
git commit -m "my changes"   
git push -u origin my-new-branch 
```

#### Extra modifications
- After pull request complete
- `git tag 1.0.1`
- `git push --tags`

> The rest of the notes can be found at my [other Repo](https://github.com/AVhouse/Certification-Study-Notes)
