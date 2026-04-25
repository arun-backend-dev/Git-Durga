

git branch
----------
-to list out all branches

git branch <branch-name>
------------------------
-to create a new branch

git checkout <branch-name>
--------------------------
-to switch from one branch to another

git checkout -b <branch-name>
------------------------------
-it is short cut to create a new branch and switch to that branch i.e git branch <branch-name> +git checkout -b <branch-name>

=============================================================================================

$ git branch
* master (* means active branch)
==========================================================================================


Conclusions
------------
-all files and commits will be inherited by child branch from parent branch until the child branch creation.
-all files and commits which are created in child branch won't visible in parent branch.
-after the creation of child branch if we made any commits and created files in parent branch those changes wont visible in child branch
-HEAD always refers to latest commit of current branch. 



NOTE:
-----
if we want to see all the list of branches go to the below folder structure there you can find all branches in the form of files and in those files their respective latest commit id's will be saved

.git/refs/heads 














