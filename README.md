# MICB425_Project1
TEAM 5

Here's some instructions for merging (in case you guys need it):
https://stackoverflow.com/questions/161813/how-to-resolve-merge-conflicts-in-git  

Here's a probable use-case, from the top:
You're going to pull some changes, but oops, you're not up to date:
1) git fetch origin
2) git pull origin master  

POSSIBLE ERROR #1
From ssh://gitosis@example.com:22/projectname
 * branch            master     -> FETCH_HEAD
Updating a030c3a..ee25213
error: Entry 'filename.c' not uptodate. Cannot merge.  
  
So you get up-to-date and try again, but have a conflict:
3) git add filename.c
4) git commit -m "made some wild and crazy changes"
5) git pull origin master  

POSSIBLE ERROR #2
From ssh://gitosis@example.com:22/projectname
 * branch            master     -> FETCH_HEAD
Auto-merging filename.c
CONFLICT (content): Merge conflict in filename.c
Automatic merge failed; fix conflicts and then commit the result.  

So you decide to take a look at the changes:
3) git mergetool
Oh me, oh my, upstream changed some things, but just to use my changes...no...their changes...
4) git checkout --ours filename.c
5) git checkout --theirs filename.c
6) git add filename.c
7) git commit -m "using theirs"  

And then we try a final time
8) git pull origin master  

From ssh://gitosis@example.com:22/projectname
 * branch            master     -> FETCH_HEAD
Already up-to-date.  

If these don't work feel free to post msg on Messenger.
