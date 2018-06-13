Assignment1:

    Initialize a directory as git repository.
    Create a blank files like a.txt, b.txt.
    Write "Hi Team Ninja" into a.txt
    Write "This is VCS:Git" into b.txt
    Set git config variables.
    Commit both files.
    Create a branch ninja
    Switch into branch ninja
    Update file b.txt with ""This is VCS:Git. This is ninja branch"
    Check for the difference made in the file.
    Commit your changes in ninja branch.
    Check difference between last two commits.
    Rename your file b.txt to c.txt
    Commit your changes.
    Remove file c.txt.
    Commit your changes.
    Create a file text.txt and add it.
    Remove it from the staging area.
    
    # mkdir repo
[root@client2 ~]# cd repo
[root@client2 repo]# git init .
Initialized empty Git repository in /root/repo/.git/
[root@client2 repo]# touch a.txt b.txt
[root@client2 repo]# echo "Hi Team Ninja" > a.txt
[root@client2 repo]# echo "This is VCS:Git" > b.txt
[root@client2 repo]# cat a.txt
Hi Team Ninja
[root@client2 repo]# cat b.txt
This is VCS:Git

[root@client2 .git]# git config --global user.name "nishantkohli94"
[root@client2 .git]# git config --global user.email nishantkohli94@gmail.com
[root@client2 .git]# cat config
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
[root@client2 .git]# git config --list
user.name=nishantkohli94
user.email=nishantkohli94@gmail.com
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true


[root@client2 repo]# git add .
[root@client2 repo]# git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   a.txt
        new file:   b.txt

[root@client2 repo]# git commit -m "Added test file for demo"
[master (root-commit) 4b54438] Added test file for demo
 2 files changed, 2 insertions(+)
 create mode 100644 a.txt
 create mode 100644 b.txt
[root@client2 repo]# git status
On branch master
nothing to commit, working tree clean

[root@client2 repo]# git checkout -b ninja
Switched to a new branch 'ninja'
[root@client2 repo]# git status
On branch ninja
nothing to commit, working tree clean
[root@client2 repo]# git branch -a
  master
* ninja

[root@client2 repo]# echo "This is VCS:Git. This is ninja branch" > b.txt
[root@client2 repo]# cat b.txt
This is VCS:Git. This is ninja branch


# git diff  b.txt
diff --git a/b.txt b/b.txt
index e31dd7d..bdc6c0b 100644
--- a/b.txt
+++ b/b.txt
@@ -1 +1 @@
-This is VCS:Git
+This is VCS:Git. This is ninja branch


[root@client2 repo]# git add b.txt
[root@client2 repo]# git commit -m "Add some more text"
[ninja f920d62] Add some more text
 1 file changed, 1 insertion(+), 1 deletion(-)

 # git diff f920d62c990cf84a87330e33afb93d99978d995f 4b54438b60e43bfaf4e2ee3ed78f40be92cbaacf
diff --git a/b.txt b/b.txt
index bdc6c0b..e31dd7d 100644
--- a/b.txt
+++ b/b.txt
@@ -1 +1 @@
-This is VCS:Git. This is ninja branch
+This is VCS:Git


# mv b.txt c.txt
[root@client2 repo]# git status
On branch ninja
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    b.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        c.txt

no changes added to commit (use "git add" and/or "git commit -a")
[root@client2 repo]# ls
a.txt  c.txt
[root@client2 repo]# git add c.txt
[root@client2 repo]# git commit -m "Renamed filename b with c"
[ninja 79fa6e3] Renamed filename b with c
 1 file changed, 1 insertion(+)
 create mode 100644 c.txt

 
 # rm c.txt
 # rm c.txt
rm: remove regular file `c.txt'? yes
[root@client2 repo]# ls
a.txt
[root@client2 repo]# git status
On branch ninja
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    b.txt
        deleted:    c.txt

no changes added to commit (use "git add" and/or "git commit -a")
[root@client2 repo]# git add .
[root@client2 repo]# git commit -m "Removed file name c"
[ninja 68ef5b8] Removed file name c
 2 files changed, 2 deletions(-)
 delete mode 100644 b.txt
 delete mode 100644 c.txt
 
 
 
 # git status
On branch ninja
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   test.txt

[root@client2 repo]# git rm test.txt
error: the following file has changes staged in the index:
    test.txt
(use --cached to keep the file, or -f to force removal)
[root@client2 repo]#
[root@client2 repo]#
[root@client2 repo]#
[root@client2 repo]# git status
On branch ninja
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   test.txt

[root@client2 repo]# git reset HEAD test.txt
[root@client2 repo]# git status
On branch ninja
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        test.txt

nothing added to commit but untracked files present (use "git add" to track)
