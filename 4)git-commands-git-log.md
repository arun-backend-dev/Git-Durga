1)git log
------------------
-it shows to see history of all commits in local repo====>git log

##git log filename.txt
---------------------------
-it shows all commits related to filename.txt file only

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

##git log --grep="features", git log --grep="features" --oneline"
------------------------------
-👉 It shows only those commits whose commit message contains the given text