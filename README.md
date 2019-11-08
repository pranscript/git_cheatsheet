# Git CheatSheet
	
### Git has four Stages - Working directory, Staging Area, Local Repository and Remote repository 

```
git config --global user.name "Your username"	// to set username 
git CONFIG --global user.email "your@email.com"	// your email
git config --global --list                      // to see your global configs
```

#### Random Jargons

* To get a repository in the local system - Cloning
* To get a personal copy of someone else's repository - Forking
* Reference to the remote repository in github - Origin

### Basics

```
git clone url                       // to clone a repository into your system, auto creates the directory with the same name. Origin is also set automatically
git status                          // shows the current branch and status of the files. Shows info about untracked file or files ready to be committed
echo "Test Content" >> test.txt     // To create the file with the text written on it
cat test.txt                        // To see the contents of the file
git add start.txt                   // To add the file from working directory to staging area and is ready to be commited. Now git is tracking the file
git commit -m "Commit message"      // To commit the changes with a commit message
git push origin master              // to push the local repository to remote repository. Remote name "origin". Branch name is "master"
git remote add origin URL           // URL copied from github is set as the origin
```

### Random 1

 ```
git init projectName        // initialize a new project
ls -al                      // show all files including hidden
rm -rf newProject           // removes the directory
mv oldname newname          // renames the directory
git add .                   // adds all files to the staging area from working directory
git pull origin master      // Updates the local repository from the remote repository. It is a good practice to pull before push
git commit -am "message"    // Add files to staging area and committing in a single step
git ls-files                // To check if git is tracking the files or not
```


### Random 2

 ```
git reset HEAD filename.txt                 // to unstage the file from the staging area.
git checkout --filename.ext                 // back to the last commit, discard the changes made in the working directory
mv oldfilename.ext newfilename.ext          // rename the file through operating system outside git
git mv oldfilename.ext newfilename.ext      // renames the file as well as sends to stagin area and done by git
git add -A                                  // recursively add any changes and also updates any file that is removed, renamed or deleted.
git mv newfilename oldfilename              // if new file name in staged but you want to backoff the file from there
git add renamedfile.ext                     // if renamed the file through finder then add it and update the index.
git add -u                                  // to update the index
```

### Random 3

 ```
rm filename.ext                             // to remove untracked files. Done at o.s level
git rm filename.ext                         // file removed through git, so it is tracked by git and will enter in staged area
git reset HEAD filename.ext                 // will be unstaged for deletion but still not in working directory
git checkout                                // filename.ext --- now it will be back to working directory from staging area
git log                                     // shows commit history. First one is the last commit done
git log	--oneline --graph --decorate --all  // oneline will compress it in one line, graph will show the branches
git config --global alias.hist "log --all--graph --decorate"    // will create the alias so no need to write the whole thing
.gitconfig                                  // file name where all the configs are stored
```

### Diff Tool 

```
git diff                        // diff tells whats modified. Shows the content. The differences between two areas
git difftool                    // this will visually tell what changes has been made between working directory and staging area
git diff HEAD                   // this will compare the working directory(all tracked files) and the last commit done in local repository
git difftool HEAD               // visual representation os the differences
git diff --staged HEAD          // comparing only files in staging area and last commit(local repository).
git diff -- README.md           // changes done only to readme
git difftool -- README.md       // visually see the difference
git log --oneline               // history of commit compressede in a line
git diff tdsfysy HEAD           // diff between a particular commit(by its ID) and last commit
git diff HEAD HEAD^             // difference between last commit and (last commit -1)
git diff master origin/master   // difference between local and remote repository in master branch
```

### Branching

```
git branch -a                     // list  all local and remote branches with an * on the current active branch.
git branch                        // shows all local branches
git branch branchname             // new branch created
git checkout branchname           // to switch between available branches
git log --oneline --decorate      // to see in history
git branch -m oldname newname     // rename a branch
git branch -d branchname          // to delete a branch you are currently not on
git checkout -b title-change      // this creates a branch and switches to it in one go
git diff master branchname        // diff between two branches
git merge branchOfSourceToCurrent // this will merge the branch to the current branch(fast forward)
fast forward                      // git just placed all the commits on the master bracnch, only possible when no changes being made on target branch, means if no commits are made on master branch then it is possible 
git branch -d banchname           // to delete the merged branch
git merge branchname --no-ff      // this will preserve that we branched off from master and now merging, will result in a merge commit
git merge branchname -m "Merge changes"
git mergetool
```

### Rebase

```
git rebase master               // from current branch, rebasing the master branch
git rebase --abort              // to abort the rebase.. nothing changed
git rebase --continue           // continue the rebasing
git fetch                       // updates the references between remote and local
git pull --rebase origin master // to rebase the origin master
```


### Stash

```
git stash                   // to save any changes in work in progress file (tracked file) when not ready to commit 
git stash apply             // brings back the original state of last stash whatever was in work in progress
git stash list              // list of stash
git stash drop              // drops the last stash
git stash -u                // stash any untracked file
git stash pop               // one command to apply and drop the last stash 
git stash save "message"    // stashing a file with a particular message
git stash show stash@{1}    // shows the stash at 1st position
git stash apply stash@{1}   // apply the stash at that position
git stash drop stash@{1}    // drop the stash at that position
git stash clear             // empty the list of stashes
git stash branch branchname // new branch created, swiched to that branch, stash is applied with the same status of files.  and then stash is dropped
```

### Tags

```
git tag tagName                // will create a lightweight tag on the commit
git tag --list                 // lists all the tag
git show tagName               // shows the commit with that tag name
git tag --delete tagName       // deletes the tag name
git tag -a tagName             // annotated tag which includes a message
git tag tagName -m "message"   // with a message 
git diff tagName1 tagName2     // to see the differences
git tag -a tagName commitID    // put a tag to a specific commit id 
git tag -a tagName -f commitID // to edit the tag
git push origin tagName        // push the tag to remote
git push origin master --tags  // sync the master branch as well as the tags
git push origin :tagName       // this tag has been deleted from the remote repo
```