<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->


- [This is a repository to create a cheat sheet of git commands. ](#this-is-a-repository-to-create-a-cheat-sheet-of-git-commands)
- [Git Overview of Commands](#git-overview-of-commands)
   * [Basic](#basic)
    - [Use git help [command] if you're stuck](#use-git-help-command-if-youre-stuck)
   * [Create](#create)
     - [From existing repo](#from-existing-repo)
     - [From existing files](#from-existing-files)
   * [Publish](#publish)
    - [Commit only watches changes that have been marked explictly with add](#commit-only-watches-changes-that-have-been-marked-explictly-with-add)
   * [View](#view)
   * [Branches](#branches)
   * [Update](#update)
   * [Revert](#revert)
- [This describes a new commit that undoes previous commits](#this-describes-a-new-commit-that-undoes-previous-commits)
* [Useful Tools](#useful-tools)
+ [Git Workflow](#git-workflow)

<!-- TOC end -->

<!-- TOC --><a name="git-overview-of-commands"></a>
## Git Overview of Commands
This is a simple cheatsheet of commands I have needed the most. To see the complete documentation
follow [Links to Git Docs](https://git-scm.com/docs)

<!-- TOC --><a name="this-is-a-repository-to-create-a-cheat-sheet-of-git-commands"></a>
##### Cheat Sheet of git commands. 


<!-- TOC --><a name="basic"></a>
### Basic

If your in the wild and get stuck use `git help[command]` 

- `master`      *default devel branch*
- `origin`      *default upstream*
- `HEAD`        *current branch*
- `HEAD^`       *parent of HEAD*
- `foo..bar`    *from branch `foo` to branch `bar`*

<!-- TOC --><a name="create"></a>
### Create

<!-- TOC --><a name="from-existing-repo"></a>
##### From existing repo

- `git clone` *bring repo from existing repo*
- `git clone ~/old ~/new`
- `git clone git://..` *from github*
- `git clone ssh://..`

<!-- TOC --><a name="from-existing-files"></a>
##### From existing files

- `git init`
- `git add` *add file to repo from local to repo*
- `git diff --staged` *used after `git add` to review changes to code*

<!-- TOC --><a name="publish"></a>
### Publish

<!-- TOC --><a name="commit-only-watches-changes-that-have-been-marked-explictly-with-add"></a>
##### Commit only watches changes that have been marked explictly with add

- `git commit` *add changes of repo to main branch*
- `git commit [-a]`  *-a: adds changed files automatically*
- `git push` *send local files to github* *(push to origin or remote)*

<!-- TOC --><a name="view"></a>
### View

- `git status` *check local files to main github branch*
- `git diff [oldid newid]`
- `git log [-p] [file|dir]`
- `git blame file`
- `git show id` 
- `git show id:file`
- `git branch` *see branches*

<!-- TOC --><a name="branches"></a>
### Branches

- `git checkout` *switch to different branch or create new branch*
- `git checkout -b newbranch` *this creates and moves to new branch*
- `git branch -d anybranch` *with -d anybranch will be deleted*
- `git merge` *branches together*

<!-- TOC --><a name="update"></a>
### Update

- `git pull` *get latest changes from branch*
- `git fetch` *from def. upstream*
- `git fetch remote`
- `git apply patch.diff`

<!-- TOC --><a name="revert"></a>
### Revert

<!-- TOC --><a name="this-describes-a-new-commit-that-undoes-previous-commits"></a>
##### This describes a new commit that undoes previous commits

- `git reset --hard` *NOT UNDONE, reset to last commit*
- `git revert branch`
- `git commit -a --amend` *replaces prev commit*

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

#### Simple example
- Create new branch
- Add new feature and code
- `add`,`commit`, and `push` changes to the remote
- Get changes reviewed by team member
- Delete remote branch
- Delete local branch
- Pull new code on the remote master to local machine 

#### Extra modifications
- After pull request complete
- `git tag 1.0.1`
- `git push --tags`