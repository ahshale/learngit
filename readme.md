Git is a version control system.
This is my first journey to [GitHub](https://github.com).
## Here are some commands in Git(learn from [Liao's wonderful blog](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)):

### 1. Remote Repository & Local Repository
#### 1.1 Clone repository from remote
```Shell
$ git clone git@github.com:username/reponame.git
```
#### 1.2 Pull changes from remote repo to local repo
    ```Shell
    $ git pull [remote] [local]
    ```
#### 1.3 push changes from local repo to remote repo
    ```Shell
    $ git push [remote] [local]
    ```
#### 1.4set a new repository in current folder
    ```Shell
    $ git init
    ```

### 2. Repository management
#### 2.1 put changes in Working Directory to Stage in Repository .git
    ```Shell
    $ git add file
    ```
#### 2.2 put changes in Stage to current branch in current Repository .git
    ```Shell
    $ git commit -m statement
    ```
#### 2.3 version fallback
##### 2.3.1 show log of commitment history (back to history)
    ```Shell
    $ git log
    $ git log --pretty=oneline
    ```
##### 2.3.2 show log of command history (back to history & future)
    ```Shell
    $ git reflog
    ```
##### 2.3.3 version fallback (HEAD for current repo, HEAD^/HEAD^^/HEAD~100)
    ```Shell
    $ git reset --hard commit_id
    ```
#### 2.4 check difference between Working Directory and Repository
    ```Shell
    $ git diff HEAD -- file
    ```
#### 2.5 undo edit
##### 2.5.1 undo the edit in Working Directory
    ```Shell
    $ git checkout -- file
    ```
##### 2.5.2 push back the changes in Stage to Working Directory(unstage)
    ```Shell
    $ git reset HEAD file
    $ git checkout -- file # and then undo the edit in WD
    ```
##### 2.5.3 when you push your repo to remote
    ```Shell
    $ there is nothing you can do
    ```
#### 2.6 delete file
    ```Shell
    $ rm file
    $ git rm/add file
    ```

### 3. Branch Manangement 
#### 3.1 All work should be done in dev branch, leaving master branch stable. Teammates merge their own changes to dev branch, and merge dev branch to master branch when necessary.

#### 3.2 list all the branches on show the current branch
    ```Shell
    $ git branch
    ```
#### 3.3 create branch
    ```Shell
    $ git branch <name>
    $ git checkout <name>
    ```
    or
    ```Shell
    $ git checkout -b <name>
    ```
#### 3.4 merge branch br to current branch
    ```Shell
    $ git merge <name> # using mode of "Fast forward", don't save info of branch
    ```
    ```Shell
    $ git merge --no-ff -m [statement] <name> # abandon "Fast forward", create a new commit in merge process and keep the info of branch
    ```
#### 3.5 check the merge graph
    ```Shell
    $ git log --graph --pretty=oneline --abbrev-commit
    ```
#### 3.6 delete branch
    ```Shell
    $ git branch -d <name>
    ```

#### 3.7 deal with bug branch & use stash to store and hide worksite
    ```Shell
    $ leave to be done
    ```
#### 3.8 deal with feature branch
    ```Shell
    $ leave to be done
    ```

#### 3.9 create remote dev branch to local repo and work on dev branch
    ```Shell
    $ git checkout -b <name> origin/<name> # create corresponding branch in local repo
    $ git branch --set-upstream <name> origin/<name> # build connection between local branch and remote branch
    $ git add file
    $ git commit -m statement
    $ git push origin <name>
    ```

#### 3.10 rebase
    ```Shell
    $ leave to be done
    ```

### 4. tag
    ```Shell
    $ leave to be done
    ```

### 5. ignore special file
    ```Shell
    $ leave to be done
    ```

### 6. customize alias
    
    ```Shell
    # with '--global' the configuration will work for the current user, otherwise it will only work for the current repository.
    The configuration file for each repository is its .git/config, and that for current user is .gitconfig in the user home directory.
    $ git config --global alias.st status
    $ git config --global alias.co checkout
    $ git config --global alias.ci commit
    $ git config --global alias.br branch
    $ git config --global alias.unstage 'reset HEAD'
    $ git config --global alias.last 'log -1'
    $ git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
    ```