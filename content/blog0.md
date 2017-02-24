Title: Git branching and merge conflict
Date: 2017-01-17 10:20
Category: Review

Branching is one of the important features of git especially for those who are developers and work alongside of others on development codes.
While git provides version control for the content you are working on, branching gives you the ability to try and new things or work on issusses on a separate branch making sure the main (master) branch always has your working code in it.
As an example, assume you and your developer friend are working on code and you want to try a new feature which you are not sure it will work at the end or how long will it take for you to get it to work.
In this situation, you would make a new branch with the following command:
``` python
git branch newbranch
git checkout newbranch
```
the newbranch is the name of your new branch you just created by branch command. The checkout command will switch you to the newbranch. These two commands can be integrated to one command which makes the new branch and switches to that branch at the same time:
``` python
git checkout -b newbranch
```
To switch between branches you can use checkout command:
``` python
git checkout master
```
switched to branch 'master'.

Having your work done on the new branch (it can include several commits on this branch), you need to add the changes on this branch to the master so your friend can have access to these new features. So, you need a merge command.
First you need to checkout to the master branch by :
``` python
git checkout master
```
and while on master branch merge:
``` python
git merge newbranch
```
After a successful merge you can delete the newbranch by:
``` python
git branch -d newbranch
```
What happens if while you were working on the newbranch, your friend had made few changes on the same files on the master branch and had committed them?
This is when you get a merge conflict. In this case, an error message would come up indicating which files and where exactly on those files the conflict happened.
``` python
Auto-merging filename
CONFLICT (content): Merge conflict in filename
Automatic merge failed; fix conflicts and then commit the result.
```
Git adds standard conflict-resolution markers to the files that have conflicts, so you can open them manually and resolve those conflicts. Your file contains a section that looks something like this:
``` python
<<<<<<< HEAD:filename
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
please contact us at support@github.com
</div>
>>>>>>> newbranch:filename
``` 
everything above the ======= is from the master and below it the version on your new branch.
To resolve the merge conflict, you have to either choose one side or the other or you have to look at the files and manually correct the conflicts were they appear.After you’ve resolved each of these sections in each conflicted file, run git add on each file to mark it as resolved and now you can commit and merge with no conflict.
