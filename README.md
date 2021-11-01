## Git Overview of Commands

##### This is a repository to create a cheat sheet of git commands. 


### Basic

##### Use git help [command] if you're stuck

- `master`      *default devel branch*
- `origin`      *default upstream*
- `HEAD`        *current branch*
- `HEAD^`       *parent of HEAD*
- `foo..bar`    *from branch `foo` to branch `bar`*

### Create

##### From existing repo

- `git clone` *bring repo from existing repo*
    - `git clone ~/old ~/new`
    - `git clone git://..` *from github*
    - `git clone ssh://..`

##### From existing files

- `git init`
- `git add` *add file to repo from local to repo*
    - `git diff --staged` *used after `git add` to review changes to code*

### Publish

##### Commit only watches changes that have been marked explictly with add

- `git commit` *add changes of repo to main branch*
    - `git commit [-a]`  *-a: adds changed files automatically*
- `git push` *send local files to github* *(push to origin or remote)*

### View

- `git status` *check local files to main github branch*
- `git diff [oldid newid]`
- `git log [-p] [file|dir]`
- `git blame file`
- `git show id` 
    - `git show id:file`
- `git branch` *see branches*

### Branches

- `git checkout` *switch to different branch or create new branch*
    - `git checkout -b newbranch` *this creates and moves to new branch*
    - `git branch -d anybranch` *with -d anybranch will be deleted*
- `git merge` *branches together*

### Update

- `git pull` *get latest changes from branch*
- `git fetch` *from def. upstream*
    - `git fetch remote`
- `git apply patch.diff`

### Revert

##### This describes a new commit that undoes previous commits

- `git reset --hard` *NOT UNDONE, reset to last commit*
- `git revert branch`
- `git commit -a --amend` *replaces prev commit*

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


#### Git Workflow

- Create new branch
- Add new feature and code
- `add`,`commit`, and `push` changes to the remote
- Get changes reviewed by team member
- Delete remote branch
- Delete local branch
- Pull new code on the remote master to local machine 