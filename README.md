# git-demo
## Demo repository for learning git
### Basic commands
* git clone <url (either ssh or https)> --> clone repository from remote server
* git init --> initialize a new repository in current working directory
* git pull origin \<branchName\> --> pull branch from remote repository
* git add \<fileName\> --> add file from working directory to staging area
* git commit --> commit to local repository (will open default editor to provide commit message)
* git commit -m "\<commit message\>" --> same as above only providing commit message inline
* git commit -am "\<commit message\>" --> add files from working directory to staging area and commits to local repository with commit message (will only add files listed by git ls-files, i.e. new files will not be added)
* git push origin \<branchName\> --> pushing local repository to remote repository

### File manipulation commands
* git ls-files --> lists all files controlled by git
* git mv \<oldFileName\> \<newFileName\> --> rename a file
* git mv \<oldDirName/fileName\> \<newDirName/\> --> move a file to another directory

### Log/history commands
* git log --> show commit log history
* git log --abbrev-commit --> same as above with shortened commit sha1
* git log --oneline --> same as above with one line per commit
* git log --oneline --graph --decorate -all --> will create ASCII graph for history (mostly visual when branching and merging)
* git log --since="time statement" --> limit the history for time since "time statement" (e.g. git log --since="3 days ago")
* git log -- \<fileName\> --> limit history to specific file

### Diff commands
* git diff --> diff between working directory and staging area
* git difftool --> same as above only using the configured difftool
* git [diff|difftool] HEAD --> diff between working directory and local repository (last commit)
* git [diff|difftool] --staged HEAD --> diff between staging area and local repository (last commit)
* git [diff|difftool] -- \<fileName\> --> diff a single file
* git [diff|difftool] \<commit 1 sha1\> \<commit 2 sha1\> --> diff between 2 arbitrary commits (e.g. git difftool 6a21df8 ac67ca4)
* git [diff|difftool] HEAD HEAD^ --> diff between local repository and 1 commit before
* git [diff|difftool] \<branchName\> \<origin/branchName\> --> diff between local branch and remote branch (or any arbitrary 2 branches)

### Branch commands
* git branch -a --> list local and remote branches
* git branch \<myNewBranch\> --> create new local branch
* git branch -m \<oldBranchName\> \<newBranchName\> --> rename branch
* git branch -d \<branchName\> --> delete local branch
* git checkout \<myNewBranch\> --> switch to local branch myNewBranch
* git checkout -b \<newBranchName\> --> create new branch and switch to it in single command

### Merge commands
* git merge /<branchName/> --> merge branchName to master (fast-forward)
* git merge --no-ff /<branchName/> --> merge branchName to master (no fast-forward)
* git mergetool --> open configured mergetool to resolve merge conflicts