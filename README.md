
	1. Working directory, staging area, git repository and remote repository --- four stages
	2. To start first time 

		1. git config --global user.name "nAME"
		2. GIT CONFIG --global user.email "fdfd" 
		3. git config --global --list
	3. To get a repository in the local system - cloning

		1. git clone url -- auto creates the directory with the same name
		2. git status -- tells that it is on the master branch -- and is it updated or not.
		3. working directory is where we do all the work and git monitors the changes
	4. echo "Test jksd" >> start.txt ---- this will create the file with the text written on it
	5. cat start.txt ---  to see the contents of the file
	6. git status --  shows an untracked file which is a file in the working directory which hasnt been added to git
	7. git add start.txt --- this will tell git
	8. git status -- shows start.txt file in the staging are and ready to be committed, we can still backout from the staging area. It is used to commit at once
	9. git commit -m "dfgd"
	10. git status -- it tell that this branch is ahead of master branch by 1 commit and working directory is clean
	11. All files moved from the staging area to the local repository.
	12. git push origin master --- remote name is origin and name of the branch to push which is master


	1. git init newProject --- to create new project
	2. ls -al --- show all files including hidden
	3. rm -rf newProject ------remove the directory


	1. mv oldname newname ---- to rename the folder
	2. git init ----initialize the new directory
	3. git status ---- reminds that we are in master branch 
	4. git add . ------add to staging area
	5. git commit -m "dsfdsfs"
	6. If we remove .git folder then git will not manage the project

    
	1. Join existing project 

		1. by forking, we get a personal copy of someone else's repository. Then we can clone it
		2. git clone url
		3. git status ---- since we cloned so it will tell that we are on branch master and up to date
		4. origin is reference to the remote repository in github. master is the branch on that repository.


	1. git pull origin master --- this will update the local repository from the remote repository. Best practice.


	1. git commit -am "message" --- add and commit in single step.
	2. git ls-files ------To check if git is tracking the files or not


	1. git add . ------it adds all the files recursively from the current folder


	1. git reset HEAD filename.ext ---- this unstaged the file from the staging area.
	2. git checkout --filename.ext  ----  back to the last commit, discard the changes made in the working directory


	1. git mv oldfilename.ext newfilename.ext --  renames the file and stages too
	2. git commit -m "renamed" ----committed
	3. mv oldfilename.ext newfilename.ext --- this is through operating system outside git
	4. git status ----- this will show that you first deleted it and then added. So we need to use following command
	5. git add -A  -- --- recursively add any changes and also updates any file that is removed, renamed or deleted.
	6. git mv newfilename oldfilename --- if new file name in staged but you want to backoff the name
	7. git add renamedfile.ext ---- this will add the file that you renamed through finder.. update the index by 
	8. git add -u ---updates the index


	1. rm filename.ext  ---- to remove untracked files. 
	2. git rm filename.ext ---- file removed inside git tracked by git -- it will enter in staged
	3. git reset HEAD filename.ext ---- will be unstaged for deletion but still not in working directory
	4. git checkout -- filename.ext --- now it will be back 


	1. git help log  --- shows options
	2. git log ----- commit history ---first one is last commit
	3. git log --oneline --graph --decorate ------------ oneline will compress in one line, 


	1. git config --global alias.hist "log --all--graph --decorate"  ----- will create  the alias
	2. .gitconfig is the file name where the configs are stored


	1. .gitignore  ---- which ignore files 
	2. *.log (to ignore all log files), log (to ignore the folder log)


	1. git diff ------ git status tell its modified but not what .. diff tells whats modified
	2. git difftool ---- this will visually tell what changes has been made between working directory and staging
	3. git diff HEAD ------ this will compare the working directory and the last commit(local repository)
	4. git difftool HEAD ----- visual representation
	5. git diff --staged HEAD ---- comparing staging area and last commit(local repository).
	6. git diff -- README.md ------ changes shown only to readme and not other files
	7. git difftool -- README.md  ----- visually
	8. git log --oneline ----- history of commit
	9. git diff tdsfysy HEAD ---- diff between that commit and last commit
	10. git diff HEAD HEAD^ ---- difference between last commit and last commit -1
	11. git diff master origin/master


	1. git remote add origin <URL>


