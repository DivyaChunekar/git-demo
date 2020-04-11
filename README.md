# Demo git repository

This is my first git project.
Trying to work locally on my project.

Creating or modifying a file
	notepad <filename>

Checking status of git
	git status

Adding file to stagging
	git add <filename>

Commit staged file
	git commit -m "Commit Msg"

How to get out of git commit msg cmd when u don't give -m
1. Enter ur commit msg
2. Press Esc
3. Type :x!

Adding multpile file together to stageing
	git add .

Adding a file (staging ) and commiting the file in one stage
	git commit -am "Message"

Backing/Restore the chngs from stagging --- Unstage a file 
	git restore --staged <filename>

Backout Working Directory Changes 
	git restore <filename>

Checking all commit log/commit history	
	git log

After git log
if u r not able to type anything and just seeing End then ---> ENter q to exit the screen 	
Also If you don't want to read the output in a pager and want it to be just printed to the terminal then
define the environment variable GIT_PAGER to cat or set core.pager to cat by executing below git config cmd
	git config --global core.pager cat


To check or get help for git log cmd
	git help log


To get only the required fields in log like commit msg
	git log --oneline --graph --decorate --color
	
	Git log options from above: 	
	  --oneline Compacts log data on to one line, abbreviating the SHA1 hash 
	  --graph Adds asterisk marks and pipes next to each commit to show the branching graph lines 
	  --decorate Adds the markers for branch names and tags next to corresponding commits 
	  --color Adds some color to the output 
	  -- nice to have, depending on the operating system

Removing an already commited file  from git 
	git rm filename
	
	this will remove the file from commit stage whn u do "ls" u won't find that file there 
	but u hv to commit the chngs bcuz it will be there in stage like 
	whn  u do 	git status 	it will show 
		On branch master
		Changes to be committed:
 		 (use "git restore --staged <file>..." to unstage)
     		   deleted:    backup.log
 	so now do 	git commit -m"Msg"
	

  Whn u remove a file without gits knowledge  
	rm filename
	
	N now whn u chk the git status it will say changes are not stagged  for commit means it is a working directory chng so just typing 
		git add . 	
			won't work we need to give
		git add -u
			The -u parameter will recursively update Git's staging area regarding deleted/moved files outside of Git.
		then git status
			git commit  -m "msg"

Making or crating a new directory or folder
	mkdir foldername

Moving file from one location to other 
	git mv source_filename destination 			
	git mv index.html web

	then commit

To ignoore a files to that is if we want that a file or files should not be committed whn v give git commit cmd
we shld make their enteries in .gitignore file
	notepad .gitignore
		make entry of file or file type (*.log) 
	git status
	git add .gitignore
	git commit -m "msg"


To transfer file to github we will use SSH authetication and for that we will require SSH key 
1. to set up ssh key first go to ur home directory (i.e. USER/MANI) from ur project (git-demo) by 		
	cd ~
2. Now check whether u hv .ssh folder by doing ls or cd .ssh , initially u wuld not hv it
3. Thn create  .ssh folder by
	mkdir .ssh/
4. go to that .ssh folder
	cd .ssh
5. Now generate the SSH key
	 ssh-keygen -t rsa -C "divyachunekar@gmail.com"
	5.1 it will ask to enter the file in which u want to save key default will be fine so just enter
	5.2 It will ask to set a pswd : 
	5.3 Renenter pswd: 
	5.4 Ur identification has been saved
	5.5 ur public key has been saved
	
6. do ls -al
	it will show all ur files even hidden files also
	u will find to id_rsa & id_rsa_pub.  .pub file is the public side of the key and that is the content will be pasting into github.
7. Copy the contents of id_rsa_pub file 
	notepad id_rsa_pub
	copy  the content of file -> Ctrl + A --> Ctrl + C  
	close
8. Goto github
	8.1 Login
	8.2 settings
	8.3 SSH and GPG Keys
	8.4 Add/New SSH key 
		8.4.1 Give title
		8.4.2 Paste ur copied ssh public key
		8.4.3 Click on add key

9. Come back to Git bash
10. Try to access github from git bash by 
	ssh -T git@github.com
11.  Whn u do this for the first time it will ask r u sure u want to establish a connection : Say --> Yes
12. Enter pswd


13. Now goto Git hub create a new reposartory 
14. Import project from locally by giving below cmd in git bash (cmd u will find in GIt Hub for ur repo)
	git remote add origin git@github.com:scm-ninja/git-demo.git  

15 To check the files
	git remote -v
	The git remote command lists the names of all the remote repositories and 
	the -v parameter (verbose) will display the full URL of the remote repository for each remote name listed

16. To push the files from local rep to GH
	git push -u remote-name branch-name
	git push remote-name branch-name
		The git push sends all your local changes (commits) on branch branch-name to the remote named remote-name.
		The -u parameter is needed the first time you push a branch to the remote.
	
	git push -u origin master (for the first time push)
	git push origin master	(form 2nd time)

17. Now ur chngs are in ur GH repo u cn chk der.

18. now if u want to make chng do them locally and commit locally.
19. Receive Changes from Remote: Beforing pushing chng to GH first pull and merge 
	git pull remote-name branch-name
		The git pull receives all your remote changes (commits) from the remote named remote-name and on branch branch-name
	
	git pull origin master
		
2. After that just push ur chngs to GH
	git push origin master
	












