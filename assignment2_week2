Assignment 1

solution1

#!/bin/bash
mkdir localrepo
cd localrepo
git init
touch first.sh
git add first.sh
echo "echo Hello" > first.sh
git commit -am 'Added a file'
git checkout -b new_branch
echo "echo \"Hello Devops\"" > first.sh
git commit -am 'first commit on new_branch'
git checkout master
echo "echo \"Hello Devops!\"" > first.sh
git commit -am 'second commit on master'
git merge new_branch

solution 2

https://github.com/nishantkohli94/Testproject.git

 mkdir gitrepo
  gitrepo
   ls
   git init
   echo "#ninj2demo" >> README.md
   cat README.md
   git status
   git add README.md
   git commit -m "first commit"
   git status
   git remote add origin https://github.com/nishantkohli94/Testproject.git
   git push -u origin master
   git branch
   git branch branch1
   git branch branch2
   git branch branch3
   git branch
   git checkout branch1
   git branch
   touch branch1text.txt
   ls
   git status
   git commit -am "added branch1text.txt file"
   git add branch1text.txt
   git status
   git checkout branch2
   git checkout branch1
   git checkout branch2
   touch branch2text.txt
  git add branch2text.txt
  git status
  git commit -am "added file branch2text.txt"
  git status
  git checkout branch3
  git branch
  ls
  touch branch3text.txt
  vi branch3text.txt
   git status
  add branch3text.txt
  git commit -m "added a new file branch3.txt"
  git commit
  git checkout master
  git push -u origin master
  git checkout branch1
  git push -u origin branch1
  git push -u origin branch2
  git push -u origin branch3
  
  solution 3
  
  #! /bin/bash
echo "Repo. name ?"
read reponame
echo "Username ?"
read username
echo “enter the branch name to checkout exitsting remote repo”
read branchname
sudo mkdir /home/$username/
sudo chown -R root:root /home/$username/
cd /home/$username/
git clone https://github.com/$username/$reponame.git
git branch $branchname origin/$branchname


Assignment 3:

Question : Add remote name parent for ot-training/jenkins to your own repo.
Solution :     git remote add parent https://github.com/ot-training/jenkins.git

Question : Check and verify two remotes.
Solution :  Git remote -v

Output of command 

parent    https://github.com/ot-training/jenkins.git (fetch)
parent    https://github.com/ot-training/jenkins.git (push)


Question : Git fetch changes from parent repo.
Solution :    git fetch parent







Question : Git merge changes into your branch.
 Solution : git merge parent/master



Question : Git pull changes from parent repo.
            
Solution : git pull parent master
        Output :From https://github.com/ot-training/jenkins
          * branch        	master 	-> FETCH_HEAD
           Already up to date.
           
           
           Question : Check for difference in fetch and pull also create a solutions.md file inside attendees/assignments/day2 with steps and snapshots.



Assignment4:
●Rename remote name from parent to main
            git remote rename parent main



●Remove main remote.
            git remote remove main

Assignment5:
●Save your solutions.md into your repo. ----save
●Try to push solutions.md into parent repo.
             Please make sure you have the correct access rights and the repository exists.


●Create a pull request from your repo to master of parent repo.
