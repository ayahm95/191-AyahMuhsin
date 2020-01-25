# Git Kata: Basic Commits
This kata will introduce you to the `git add` and `git commit` commands.

This is a very introductory kata. if you have used `git status`, `git log --oneline --graph`, `git add` and `git commit` extensively you should probably skip it.

You can look at the bottom of this file, if you have not yet done basic git configuration.

## Setup:

1. Run `. setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

1. Use `git status` to see which branch you are on.
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

2. What does `git log` look like?
$ git log
fatal: your current branch 'master' does not have any commits yet

3. Create a file
4. What does the output from `git status` look like now?
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        newfile.txt

nothing added to commit but untracked files present (use "git add" to track)

5. `add` the file to the staging area

6. How does `git status` look now?
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   newfile.txt

7. `commit` the file to the repository
ayahm@Ayah MINGW64 ~/Desktop/git-katas/basic-commits/exercise (master)
$ git commit -m "Add new file to repository"
[master (root-commit) 7ba912e] Add new file to repository
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 newfile.txt

8. How does `git status` look now?
$ git status
On branch master
nothing to commit, working tree clean

9. Change the content of the file you created earlier
10. What does `git status` look like now?
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   newfile.txt

no changes added to commit (use "git add" and/or "git commit -a")

11. `add` the file change

12. What does `git status` look like now?
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   newfile.txt


13. Change the file again
14. Make a `commit`
$ git commit -m 'Changed the file'
[master 2034b28] Changed the file
 1 file changed, 1 insertion(+)


15. What does the `status` look like now? The `log`?
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   newfile.txt

no changes added to commit (use "git add" and/or "git commit -a")

$ git log
commit 2034b2882f670846654c857f4cee234907e9ee79 (HEAD -> master)
Author: Ayah Muhsin <amuhsin@uci.edu>
Date:   Fri Jan 24 17:45:29 2020 -0800

    Changed the file

commit 7ba912e7c5e57b8bf37d46e4fefabd812a70dbb9
Author: Ayah Muhsin <amuhsin@uci.edu>
Date:   Fri Jan 24 17:42:17 2020 -0800

    Add new file to repository

16. Commit the newest change
$ git commit -m "final change"
[master d2add6d] final change
 1 file changed, 3 insertions(+), 1 deletion(-)


## Useful commands
- `git add`
- `git commit`
- `git commit -m "My commit message"`
- `git log`
- `git log -n 5`
- `git log --oneline`
- `git log --oneline --graph`
- `touch filename` to create a file (or `sc filename ''` in PowerShell)
- `echo content > file` to overwrite file with content (or `sc filename 'content'` in PowerShell)
- `echo content >> file` to append file with content (or `ac filename 'content'` in PowerShell)


## Git Initial Configuration
1. `git config --global user.name "John Doe"`
1. `git config --global user.email "johndoe@example.com`

For the vim scared:
- `git config --global core.editor nano`

For the windows peeps:
- `git config --global core.editor notepad`

Other editor options:
- `git config --global core.editor "atom --wait"`
- `git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst"`
