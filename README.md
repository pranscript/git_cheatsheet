
	# Part 1
	
	Working directory, staging area, git repository and remote repository --- four stages
	To start first time 

		```
		git config --global user.name "nAME"
		```
		*```
		git CONFIG --global user.email "fdfd"
		```
		*```
		git config --global --list
		```
	To get a repository in the local system - cloning

		1. ```
		git clone url
		``` -- auto creates the directory with the same name
		```
		2. ```
		git status
		``` -- tells that it is on the master branch -- and is it updated or not.
		3. working directory is where we do all the work and git monitors the changes
	```
		echo "Test jksd" >> start.txt
		``` ---- this will create the file with the text written on it
	```
	cat start.txt
	``` ---  to see the contents of the file
	```
	git status
	``` --  shows an untracked file which is a file in the working directory which hasnt been added to git
	```
	git add start.txt
	``` --- this will tell git
	```
	git status
	``` -- shows start.txt file in the staging are and ready to be committed, we can still backout from the staging area. It is used to commit at once
	```
	git commit -m "dfgd"
	```
	 ```
	git status
	``` -- it tell that this branch is ahead of master branch by 1 commit and working directory is clean
	 All files moved from the staging area to the local repository.
	 ```
		git push origin master
		``` --- remote name is origin and name of the branch to push which is master

	
	#part 2

	 ```
	git init newProject
	``` --- to create new project
	 ```
	ls -al
	``` --- show all files including hidden
	 ```
	rm -rf newProject
	``` ------remove the directory


	 ```
	mv oldname newname
	``` ---- to rename the folder
	 ```
	git init
	``` ----initialize the new directory
	 ```
	git status
	``` ---- reminds that we are in master branch 
	 ```
	git add .
	``` ------add to staging area
	 ```
	git commit -m "dsfdsfs"
	```
	 If we remove .git folder then git will not manage the project

    
	 Join existing project 

		 by forking, we get a personal copy of someone else's repository. Then we can clone it
		 ```
		git clone url
		```
		 ```
		git status
		``` ---- since we cloned so it will tell that we are on branch master and up to date
		 origin is reference to the remote repository in github. master is the branch on that repository.


	 ```
	git pull origin master
	``` --- this will update the local repository from the remote repository. Best practice.


	 ```
	git commit -am "message"
	``` --- add and commit in single step.
	 ```
	git ls-files
	``` ------To check if git is tracking the files or not


	 ```
	git add .
	``` ------it adds all the files recursively from the current folder


	 ```
	git reset HEAD filename.ext
	``` ---- this unstaged the file from the staging area.
	 ```
	git checkout --filename.ext
	```  ----  back to the last commit, discard the changes made in the working directory


	 ```
	git mv oldfilename.ext newfilename.ext
	``` --  renames the file and stages too
	 ```
	git commit -m "renamed"
	``` ----committed
	 ```
	mv oldfilename.ext newfilename.ext
	``` --- this is through operating system outside git
	 ```
	git status
	``` ----- this will show that you first deleted it and then added. So we need to use following command
	 ```
		git add -A
		```  -- --- recursively add any changes and also updates any file that is removed, renamed or deleted.
	 ```
	git mv newfilename oldfilename
	``` --- if new file name in staged but you want to backoff the name
	 ```
	git add renamedfile.ext
	``` ---- this will add the file that you renamed through finder.. update the index by 
	 ```
	git add -u 
	```---updates the index


	 ```
	rm filename.ext
	```  ---- to remove untracked files. 
	 ```
	git rm filename.ext
	``` ---- file removed inside git tracked by git -- it will enter in staged
	 ```
	git reset HEAD filename.ext
	``` ---- will be unstaged for deletion but still not in working directory
	 ```
	git checkout
	``` -- filename.ext --- now it will be back 


	 ```
	git help log
	```  --- shows options
	 ```
	git log
	``` ----- commit history ---first one is last commit
	 ```
		git log
		``` --oneline --graph --decorate ------------ oneline will compress in one line, 


	```
	git config --global alias.hist "log --all--graph --decorate"
	```  ----- will create  the alias
	.gitconfig is the file name where the configs are stored


	.gitignore  ---- which ignore files 
	*.log (to ignore all log files), log (to ignore the folder log)


	```
	git diff
	``` ------ git status tell its modified but not what .. diff tells whats modified
	```
	git difftool
	``` ---- this will visually tell what changes has been made between working directory and staging
	```
	git diff HEAD
	```------ this will compare the working directory and the last commit(local repository)
	```
	git difftool HEAD
	``` ----- visual representation
	```
	git diff --staged HEAD
	``` ---- comparing staging area and last commit(local repository).
	```
	git diff -- README.md
	``` ------ changes shown only to readme and not other files
	```
	git difftool -- README.md
	```  ----- visually
	```
	git log --oneline
	``` ----- history of commit
	```
	git diff tdsfysy HEAD
	``` ---- diff between that commit and last commit
	 ```
		git diff HEAD HEAD^
		``` ---- difference between last commit and last commit -1
	 ```
		git diff master origin/master
		```


	 ```
		git remote add origin <URL>
		```


