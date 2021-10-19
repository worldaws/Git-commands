Git Installation :
==================
To install git -- > yum install git -y 
To check Version -- > git --version 

git config :
============
git config --global user.name “vikas99341”
git config --global user.email “vikasisinlove@gmail.com”
git config --list 
git config --global push.default simple
  
Create a git repo and push it :
==============================
To Create a Local Repository on Git :
 mkdir gitprojects/project1 -- > cd  gitprojects/project1 -- > git init (initialize empty git repository) --> vi file1
                         ls -- > you see the file in working directory but 
	git ls-files will not show anything as the file has not moved to local repo.

git log and diff :
=================

  git log -- > this will give you SHA details .
  git log --oneline -- > for brief commit detail
  git log --pretty=oneline 
  git log <particular 7 digit commit id > -- > to see details for one particular file1
  git show <comit id> or    git show <shaid > -- > detailed description
  git show HEAD -- > See the latest commit ID .
  git reset--HARD  <sha-code> -- > to uncommit some commit and move the head down 
  git fsck --lost-found -- > which commit was not done or dangaling
  git diff <fikle3.txt>  -- > differnce before commiting the change  
  git diff <commit id 1> <commit id 2>-- > will let you know changes between two commits
  git diff --staged <fikle3.txt>  -- > differnce after commiting the change 

Adding & Revert in different stages :
=====================================
  touch a.txt
  git status -- > see what has changed since last commit
  git add .  - - > add all file to staging area which can be checked by git status .
  git add --all > add all files  
  git add –A -- > to add multiple changed files in one shot 
  git  commit –m “<message >”   commit the code
  git commit –a –m “direct add “  -- > If you want to skip staging area and add 
  git rm <file name > -- > remove file from WD as well as local repo
  git rm --cached <file name > -- > remove file from Local repo
  git ls -- > view files on working directory 
  git ls-files -- > view files on local repo

Branch :
=======
 git branch to see all the available branches
 git branch <name the branch> or git checkout  -b branch1 master -- > to create a new branch branch1 from master and checkout @ same time 
 git checkout <branch name> -- > to go to <branch name > -- > changes done here will not be visible unless and until merged with master .
 git cherry-pick <sha-id > if you want to selective commit in feature branch .

To delete a branch :
  git branch –d <branch-name>

Merge conflict :
===============
 git merge go to that(master) branch and say git merge <other branch >
 merge the content -- > come to master and use “ git merge master1 “ -- > if there is a conflict on merge -- > edit the file and commit again .
 git log --oneline --graph --decorate --all	
 
Pushing and pulling from repo :
==============================
  git remote add origin “git hub clone link “ -- > copy to git  
  git remote –v (to check where is origin)
  git pull original master -- > pull command to get the code (run it from the repo)
  git fetch origin – same as git pull but will only show the change
  git push origin master  -- >  push command to put the code in git hub 
  git pull = git fetch + git merge (git fetch will check the remote repo and git pull will pull the changes)

Ignore files on commit:
=======================  
   vim .gitignore -- > if you don’t want to upload to remote directory put those extensions here .
       .gitignore file

Revert changes from staging area :
==================================
  you made changes in local repo no git add and no commit
  git checkout <file name >
  
  you made changes in local repo and done  git add and no commit
  git reset HEAD <file name >
  git checkout <file name >
  
Removing files :
=============== 
  git rm file3.txt -- > will remove from working directory and local repo and the you have commit to see in remote repo
  git rm --cached file3.txt -- > will remove the content only from Local repo and not working directory (remove prior you commit). 

Modify the comment at top :
========================== 
 git commit --amend -m “New comment” 

Adding tag :
============
 git tag --a <tag name> <7 digit commit id> -m “adding tag ”
 git tag 
 now these two are equivalent : git show <7 digit commit id >  and git show <tag name>
 
Reverting git commit :
=====================
 git revert <7 digit commit id > or git revert <commit id >
 
Remove entry from log :
======================
 git reset –hard <commit id>  -- > all the commits before this we be deleted 
 git reset –hard <commit id >  then git push –f -- > remove the commit permanently 
 git revert head -- > git push -- > remove comit with revert

Git Rebase and Stash:
=====================
 git rebase master
 git stash -- > park it temporarily
 git stash list 
 git show <stash>
 git stash pop -- > bring it back  
 git stash pop <stash number >   and same  git stash apply <stash number> -- > get your work back
  
 Git RESET and REVERT :
---------------------------
Issue with a new commit so reverting to previous commit :
 git reset --hard <commit-id> 
 git push –f 

Revert :
--------
 git revert head – 
  :q! – git push 
 you can do a cherry pick here 

Git stash :
----------
Park your work aside temporarily  git stash & git stash pop 

  
Rebasing
There are two main ways to use the git rebase command:
- as an alternative to merging
as a cleanup tool

We get a much cleaner project history. No unnecessary merge commits! We end up with a linear project history.

https://medium.com/@fredrikmorken/why-you-should-stop-using-git-rebase-5552bee4fed1
