Git is a version control system.
This is my first journey to [GitHub](https://github.com).
## Here are some commands in Git(learn from [Liao's wonderful blog](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)):

### Remote Repository & Local Repository
#### clone repository from remote
```Shell
$ git clone git@github.com:username/reponame.git
```
#### pull changes from remote repo to local repo
```Shell
$ git pull [remote] [local]
```
#### push changes from local repo to remote repo
```Shell
$ git push [remote] [local]
```
#### set a new repository in current folder
```Shell
$ git init
```

### Repository management
#### put changes in Working Directory to Stage in Repository .git
```Shell
$ git add file
```
#### put changes in Stage to current branch in current Repository .git
```Shell
$ git commit -m statement
```
#### version fallback
##### show log of commitment history (back to history)
```Shell
$ git log
$ git log --pretty=oneline
```
##### show log of command history (back to history & future)
```Shell
$ git reflog
```
##### version fallback (HEAD for current repo, HEAD^/HEAD^^/HEAD~100)
```Shell
$ git reset --hard commit_id
```
#### check difference between Working Directory and Repository
```Shell
$ git diff HEAD -- file
```
#### undo edit
##### undo the edit in Working Directory
```Shell
$ git checkout -- file
```
##### push back the changes in Stage to Working Directory(unstage)
```Shell
$ git reset HEAD file
$ git checkout -- file # and then undo the edit in WD
```
##### when you push your repo to remote
```Shell
$ there is nothing you can do
```
#### delete file
```Shell
$ rm file
$ git rm/add file
```

### Branch Manangement 
#### All work should be done in dev branch, leaving master branch stable. Teammates merge their own changes to dev branch, and merge dev branch to master branch when necessary.

#### list all the branches on show the current branch
```Shell
$ git branch
```
#### create branch
```Shell
$ git branch <name>
$ git checkout <name>
```
or
```Shell
$ git checkout -b <name>
```
#### merge branch br to current branch
```Shell
$ git merge <name> # using mode of "Fast forward", don't save info of branch
```
```Shell
$ git merge --no-ff -m [statement] <name> # abandon "Fast forward", create a new commit in merge process and keep the info of branch
#### check the merge graph
```Shell
$ git log --graph --pretty=oneline --abbrev-commit
```
#### delete branch
```Shell
$ git branch -d <name>
```

#### deal with bug branch & use stash to store and hide worksite
```Shell
$ leave to be done
```
#### deal with feature branch
```Shell
$ leave to be done
```

#### create remote dev branch to local repo and work on dev branch
```Shell
$ git checkout -b <name> origin/<name> # create corresponding branch in local repo
$ git branch --set-upstream <name> origin/<name> # build connection between local branch and remote branch
$ git add file
$ git commit -m statement
$ git push origin <name>
```
#### rebase
```Shell
$ leave to be done
```

### tag
```Shell
$ leave to be done
```
