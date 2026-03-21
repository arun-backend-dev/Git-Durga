

##Features of GIT

1)Distributed nature
2)Staging area(index area)
3)Branching and merging concepts
4)Open source and freeware
5)Support for multiple platforms


##GIT architecture:
--------------------
1)Working directory
2)Staging area
3)Local repository
4)Remote repository

##Life cycle of file in GIT
--------------------------
1)Untracked
2)Staged
3)Modified
4)In repository/Commited

##1)Untracked:
-------------
Every new file will be created in working directory.GIT does not aware these new files.such type of files are said to be in untracked



##2)Staged
----------------
The files which are added to staging area are said to be in staged state


git add a.txt ----------------->It will add only a.txt to staging area
git add .     ------------------> Adds ALL files (new, modified, deleted) from the current directory
      and its subdirectories to the staging area
git add a.txt b.txt c.txt-------> Adds multiple specific files (a.txt, b.txt, c.txt) to the staging area
git add *.txt-------------------> Adds all files with '.txt' extension in the current directory

##3)local Repository
---------------------
Any file which is committed is said to be in repository area or committed state

we can commit staged changes by using git commit

ex:git commit

commit message========>mandatory

git commit -m "a.txt added"


##4)Modified
-------------------

Any file which is already tracked by git,but it is modified in working dir is said to be in modified state.

















