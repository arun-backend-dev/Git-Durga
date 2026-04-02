git diff commnd:
----------------

-In the content of a file we can get difference between:
           1)working directory vs staging area
           2)working directory vs last commit
           3)staging area vs last commit
           4)working directory vs specified commit
           5)staging area vs specified commit
           
           
Scenario 1:
-------------------
Initially i have 2 files in working directory named file1.txt and file2.txt having 2 lines each and i staged and i committed and then i modified both files having 4 lines in each file and i staged and committed and now i modified file1.txt having 5 lines and i staged but not committed so far and now i modified file1.txt having 6 lines and i not staged


1)git diff file1.txt
--------------------
-it shows the difference between staged area and working directory of file1.txt

diff --git a/file1.txt b/file1.txt
index a8226d0..a0cf774 100644
--- a/file1.txt
+++ b/file1.txt
@@ -3,3 +3,4 @@ second line in file1.txt
 third line in file1.txt
 fourth line in file1.txt
 fifth line n file1.txt
+sixth line in file1.txt
   
   1)diff --git a/file1.txt b/file1.txt :
      a/file1.txt------>source copy which means staging area 
      b/file1.txt------>Destination copy means working directory
      
   2)index a8226d0..a0cf774 100644:
     a8226d0-------->hash of source file content(staging area) 
     a0cf774 ------->hash of destination file content(working directory)
     100644-------->GIT file mode  
      
   3)--- a/file1.txt
   source copy missing some lines(staging area)
   
   4)+++ b/file1.txt
   +++ means new lines added in  destination copy(working directory)
      
      
      
   + means destination version
from 3rd line onwards total 4 lines

Third line in file1.txt
Fourth line in file1.txt
fifth line in file1.txt
+sixth line in file1.txt

If any line prefixed with space means it is unchanged.
If any line prefixed with + means it is added in destination copy.
If any line prefixed with - means it is removed in destination copy.   
      
      
      
2)git diff HEAD file1.txt
--------------------------
-it shows the difference between the latest committed file(local repo) of file1.txt and working directory of file1.txt

3)git diff --cached HEAD file1.txt , git diff --staged HEAD file1.txt , git diff --staged  file1.txt
--------------------------------
-it shows the difference between the latest committed file(local repo) of file1.txt and staging area of file1.txt

4)git diff d9ed5df file1.txt
---------------------------
-it shows the difference between file1.txt of the specified commit(d9ed5df) and the working directory of file1.txt

5) git diff --cached d9ed5df file1.txt
-----------------------------------------
-it shows the difference between file1.txt of the specified commit(d9ed5df) and the staging area of file1.txt

6)git diff HEAD HEAD~1 file1.txt
---------------------------------------
-here HEAD~1 means 2nd latest commit and HEAD means latest commit

NOTE:
----------
-comparing always from right to left

1)git diff --cached d9ed5df file1.txt then comparison starts from d9ed5df to --cached


2)git diff d9ed5df file1.txt then comparison starts from d9ed5df to working directory

3)git diff HEAD d9ed5df then all files in d9ed5df commit will be compared to all files in HEAD commit .means file1.txt of d9ed5df to file1.txt of HEAD and file2.txt of d9ed5df to file2.txt of HEAD




