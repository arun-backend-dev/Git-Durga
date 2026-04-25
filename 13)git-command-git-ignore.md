.gitignore
------------

.gitignore is a file used in Git to specify which files and folders should be ignored (not tracked or committed) by Git.

1)Avoid committing unnecessary files
2)Prevent pushing sensitive data
3)Keep repo clean and lightweight

Q)should we create that .gitignore file?
A)yes, you should create a .gitignore file


Practical
---------
$ ls
Customer.java  Orders.js  Service.java  a.txt  b.txt  c.txt  readme.md

=======================================================================

$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Customer.java
        Orders.js
        Service.java
        a.txt
        b.txt
        c.txt
        readme.md

nothing added to commit but untracked files present (use "git add" to track)

=======================================================================

vim .gitignore

 a.txt
 Customer.java
 
=======================================================================
 
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        Orders.js
        Service.java
        b.txt
        c.txt
        readme.md

nothing added to commit but untracked files present (use "git add" to track)
 
=======================================================================
$ vim .gitignore
 
  a.txt
 Customer.java
 .gitignore
 *.txt
=======================================================================
 $ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Orders.js
        Service.java
        readme.md

nothing added to commit but untracked files present (use "git add" to track)
 
=======================================================================
 
 $ cat .gitignore
a.txt
Customer.java
.gitignore
*.txt
 
 
 
 
 
 
 
 
 
 
 
 