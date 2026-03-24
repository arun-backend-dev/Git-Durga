1)git init
------------------
To provide an empty repository to our workspace so thet version control is available to our working directory
            the name of that empty repository is .git which is a hidden directory 
            
👉 In simple words:
It tells Git — “Start tracking this folder.

.git is alocal repository



2)git status
--------------
It shows the current status of all files in each area i.e. untracked files,modified files,staged files and branch information
-it shows  the current branch name
-It’s mainly used to check your work before committing

git status checks both the working directory and the staging area
It shows changes in the working directory (modified but not added)


3)git status -s
------------------------
if we want consise information

4)git add
-----------------
To add files from working directory to staging area once we added files to staging area,then git tracks these files and ready for commit.

staging area is also known as index area or cache area

1)To add all filed in CWD
--------------------------
git add .

2)To add particular files 
----------------------------
git add file1.txt file2.txt file3.txt

3)To add all java files
-------------------------------
git add *.java

4)To add all files 
-------------------
git add -A



5)git commit -m "commit message goes here"
---------------------------------------------
if we want to commit staged changes
commit message is mandatory
for every commit id unique id/hash will be generated that id is hexadecimal number of 40 characters
for every commit git records author name,mail id,time stamp,commit message
commit id is unique which can be used to idenify commit and the first 7 characters also unique

6)git commit -a -m "commit message"
---------------------------------------
If we have a file which is tracked by git and if that file we committed and again if that file got modified then we dont need to write add command   again to move that file to staging area in order to commit that file we can simply write .if and only if that file ias already previously tracked by file and for new file it will not work.

NOTE:
------
After a git commit, the staging area is not cleared; instead, Git updates it to match the latest commit snapshot, so all those files remain tracked, and since there are no differences between the working directory, staging area, and repository, git status shows “nothing to commit” until you make new changes.


7)git ls-files
----------------
it shows files present in the staging area (index)
It lists only tracked files (not untracked ones)
It helps you see what Git is currently managing


8)git log
------------------
it shows to see history of all commits in local repo====>git log
##git log <file name>
---------------------------
-it shows all commits related to specified file name

##git --oneline
--------------------------------
-it prints one line per commit
-it prints concise info of all commits
-it prints commit id+commit message only
-here the length of commit id is 7 characters(first characters of commit id)
-it is helpful if we have a lot of commits and to identify commit based on message.

##git log -n 
------------------
##git log -n 2  , git log -n 2 --oneline , git log 2 ,git log --max-count=2
----------------
-it shows only latest 2 commits

##git log --grep=pattern
----------------------------
-It searches only commit messages, not file content
-It is case-sensitive by default
##git log --grep="features", git log --grep="features" --oneline
------------------------------
-👉 It shows only those commits whose commit message contains the given text

9)git config
--------------
-it is used to know for git configurations like user name,mail id etc

##git config --list
----------------
the above command is used to list out all configurations
   
   
##git config user.name 
--------------------------------------- 
-displays user name

##git config user.name "arun"
----------------------------------------
-will set the name

##git config user.email "arun.com"
-----------------------------------------
-will set email



  
