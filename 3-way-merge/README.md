# Git Kata: 3-Way Merge

## Setup

1. Run `. setup.sh` (or `.\setup.ps1` in PowerShell)

## The task
You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.

1. Create a branch called greeting and check it out
$ git checkout greeting
Switched to branch 'greeting'

2. Edit the greeting.txt to contain your favorite greeting
3. Add greeting.txt files to the staging area
4. Commit
$ git commit -m "add file"
[greeting dbb1963] add file
 1 file changed, 1 insertion(+), 1 deletion(-)

5. Switch back to the master branch
6. Create a file README.md with information about this repository
7. Add the README.md file to staging area and make the commit
$ git commit -m "Readme"
[master 72628c6] Readme
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

8. What is the output of `git log --oneline --graph --all`?
$ git log --oneline --graph --all
* 72628c6 (HEAD -> master) Readme
| * dbb1963 (greeting) add file
|/
* fb439bf Add content to greeting.txt
* 42e6dc4 Add file greeting.txt


9. Diff the branches
$ git diff master greeting
diff --git a/README.md b/README.md
deleted file mode 100644
index 77b1ff1..0000000
--- a/README.md
+++ /dev/null
@@ -1 +0,0 @@
-this is for the 3-way merge assignment for 191A
\ No newline at end of file
diff --git a/greeting.txt b/greeting.txt
index ce01362..32f95c0 100644
--- a/greeting.txt
+++ b/greeting.txt
@@ -1 +1 @@
-hello
+hi
\ No newline at end of file


10. Merge the greeting branch into master

$ git merge greeting master
Merge made by the 'recursive' strategy.
 greeting.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

## Useful commands
- `git branch`
- `git branch <branch-name>`
- `git branch -d <branch-name>`
- `git checkout <branch-name>`
- `git checkout -b <branch-name>`
- `git branch -v`
- `git add`
- `git commit`
- `git commit -m`
- `git merge <branchA> <branchB>`
- `git diff <branchA> <branchB>`
- `git log --oneline --graph --all`
