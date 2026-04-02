git references:
----------------

-For most of the commands (like git log, git diff etc) we have to use commit ids as arguments. 
But remembering these commit ids is very difficult.

-40 length commit id | 7 characters

-Git provides some sample names for these commit ids. We can use these names directly instead of commit ids. 
-These are just pointers to commit ids.

-These sample names are nothing but references.


master:
----------
-it is nothing but a file name 
-it always points to latest commit id
-we can use master where ever we use latest commit id
- master info is available in  .git/refs/heads/master
-if we go throgh the above folder structure we can see the commit id of latest commit in master file

HEAD:
------
-it is a reference to master
-means it is a reference pointing to another reference which is called symbolic reference. so HEAD is a symbolic reference.
-by default HEAD is always pointing to master
-HEAD info is always available in .git/  directory
-HEAD is a file which points to master

detached HEAD:
---------------
-sometimes HEAD is not pointing to the branch name ,such type of HEAD is called detaches HEAD

git show
---------
The git show command is used to display detailed information about Git objects, most commonly a specific commit. By default, it shows the commit metadata (author, date, hash) followed by the textual diff of the changes made in that commit.

1)git show
-----------
-it shows the latest commit

2)git show master,HEAD
------------------
-it shows the latest commit
-as master always points to latest commit

3)git show master~1 or git HEAD~1
--------------------
-it shows latest but 1 commit


Useful Options
---------------
--stat: Shows a summary of files changed (number of insertions/deletions per file) instead of the full diff.
--name-only: Lists only the names of the files modified in the commit.
--oneline: Provides a highly condensed view, showing the shortened hash and commit message on one line.
-s or --no-patch: Suppresses the diff output entirely, showing only the commit metadata


