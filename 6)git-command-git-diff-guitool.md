Visual tool for checking differences:
------------------------------------
1)Helix visual merge tool(p4merge)
2)Meld
3)etc


p4merge===>Merge tool as well as diff tool

How to download and install p4merge tool :
------------------------------------------
https://www.Perforce.com

-during installation select only Merge and Diff tool



how to configure p4merge with git :
------------------------------------

difftool configuration:
----------------------
git config --global diff.tool p4merge(used to which excutable file to execute)
git config --global diff.tool.p4merge.path "C:\Program Files\Perforce\p4merge.exe"
git config --global difftool.prompt false

mergetool configuration:
----------------------
git config --global merge.tool p4merge(used to which excutable file to execute)
git config --global merge.tool.p4merge.path "C:\Program Files\Perforce\p4merge.exe"
git config --global mergetool.prompt false












