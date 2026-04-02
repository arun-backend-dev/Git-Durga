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

##git log date
--------------------------
-it shows commits more recent than a specific date or time

--------------------------------------------------

##git log --since 2026-03-24
-------------------------------------------------

##git log --after 2026-03-24
-------------------------------------------------

##git log --after "1 hour ago"
-----------------------------------------------

##git log --after "10 days ago"
-----------------------------------------------


##git log --after "3 hours 5 minutes ago"
-----------------------------------------------


##git log --after "5 minutes ago"
-----------------------------------------------


##git log --until="2026-03-24"
-----------------------------------------------

##git log --before="2026-03-24"
-----------------------------------------------

##git log --before="5 minutes ago"
-----------------------------------------------


##git log --before="1 day ago"
-----------------------------------------------


##git log --author=arun
-----------------------------------------------

##git log --decorate
-----------------------------------------------

