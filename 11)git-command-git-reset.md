git reset:
----------------
-to remove changes from staging area
-to undo commits at repositiry level

1)git reset file1.txt
--------------------
-if we accidently staged a file and want to remove from staged area we can use this command
-if we have any commit history of file1.txt then in index area it goes back to previous stage
-if we dont have any commit history then the file file will be removed from staged area consequently git will treat this file as untracked and for proof we can give command git ls-files

difference between git rm --cached and git reset
---------------------------------------
`git reset file2.txt` is safe — it only touches the `.git/index` (Staging Area) and never deletes your actual file from the folder. If file2.txt has a commit history, it restores the index entry back to HEAD. If no commit history, it simply removes the entry from the index. Either way, your file stays in your Working Directory untouched.

`git rm file2.txt` on the other hand is destructive — it removes the entry from `.git/index` AND deletes the actual file from your Working Directory. Your file is gone from the folder completely.

The only middle ground is `git rm --cached file2.txt` — it only removes the entry from `.git/index` without deleting the actual file, but unlike `git reset`, it always removes the entry regardless of whether the file has a commit history or not.