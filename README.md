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
