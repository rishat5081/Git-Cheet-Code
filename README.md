## Git Cheat Code

### Using CMD

#### 1. Set Global Config

```
git config --global -e
```

#### 2. Setting default editor for git

```
git config --global core.editor "code --wait"
```

#### 3. Setting next line config for windows

```
git config --global core.autocrlf true
```

#### 4. Setting next line config for mac/ linux

```
git config --global core.autocrlf input
```

#### 5. Git help details information

```
git config --help
```

#### 6. Git help for short information

```
git config --h
```

#### 7. Initialize Git

```
git init
```

#### 8. Git add `(Add Snapshots to Staging Area)`

- You can use `.` for all the files in the directory
- You can use `*.txt` all the `.txt` files in the directory
- You can use `file1.txt` for `file1.txt` in the directory

```
git add .  || git add *.txt || git add file1.txt
```

#### 9. Get Repo Status

```
git status
```

#### 10. Git commit Snapshot to Repo

```
git commit -m "First Commit"
```

#### 11. Show files in the Staging Area

```
git ls-files
```

### Accidently add a folder or file to staging area than remove it like these commands

#### 12. Remove file or directory from the staging Area

- Use the point 11 to see the files

```
git rm --cached -r accidentlyAddedFile.txt
```

#### 13. View the changes took place in Staging Area

```
git diff --staged
```

<img src="./Diff --staged.PNG" alt="MarineGEO circle logo" />

### Description of the Diff (diffing)

- `--- a/file1.js` will be the old file with -
- `+++ a/file1.js` represent the new file with +
- `@@ -1,3 +1,5 @@` represent the header in the file and the left side represent the line number starting and ending and same for the right side but after the adding the old Snapshot to staging area
- `hello \n world` represent the old file information and with `+` and green it represent new file

#### 14. Adding VSCODE for diff (diffing)

```
git config --global diff.tool vscode
```

#### 15. Config VSCODE for diff (diffing)

```
git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"
```

- Check the `.gitconfig` file for $REMOTE and $LOCAL should be added. Use point 1 to open `.gitconfig`.

#### 16. Launch VSCODE for diff (diffing)

```
git difftool
```

#### 17. Git Log

    Display all the logs of the commits

```
git log
```

- `git log --oneline` display log in one line
- `git log --oneline --reverse` display log in one line in descending order
- `git log --oneline --stat` display log in one line in show the changes also

#### 18. Git Show

    Display all the code changes in the commits are done.

```
git show
```

- `git show 06ay` is the commit id `06ay` used from point 17.
- `git show HEAD~1` show the changes start from HEAD and move 1 step ahead. 1 can be changed depending upon your commits.

#### 19. Git restore changes to older version of file

    Reverse the changes to older version locally (local machine). If you have modified a file and want to go back to older version locally

```
git restore file1.txt
```

- You can use `.` for all the files in the directory
- You can use `*.txt` all the `.txt` files in the directory
- You can use `file1.txt` for `file1.txt` in the directory

#### 20. Git restore changes from Staging Area to Working directory (Local Machine)

    Reverse the changes from the staging area to the working directory (local machine).

```
git restore --staged file1.txt
```

- You can use `.` for all the files in the directory
- You can use `*.txt` all the `.txt` files in the directory
- You can use `file1.txt` for `file1.txt` in the directory

#### 21. Git restore from previous commit to Working directory

    Restore the from previous commit to Working directory if you have accidently or intentionally deleted it.

```
git restore --source=HEAD~1 file1.txt
```

- `git show HEAD~1` show the restore the file starting from HEAD and move 1 step ahead. 1 can be changed depending upon your commits.

#### 21. Git clean

    Remove the untracked files

```
git clean
```

There are some tags used with this command.

- You can use `-h` for help.

### Git Logs

#### 22. print last three git commits

```
git log --oneline -3
```

- Chnage -3 to how many numbers of logs you want.

#### 23. print changes made in commit

```
git log --oneline --patch
```

- Chnage -3 to how many numbers of logs you want.

#### 24. print git commits using author name

```
git log --oneline --author="Saad"
```

#### 25. print git commits using date

```
git log --oneline --after="2020-12-01"  ||

git log --oneline --before="2020-12-01" ||

git log --oneline --after="yesterday" ||

git log --oneline --after="one week ago" ||

git log --oneline --after="one month ago" ||

git log --oneline --after="one year ago"
```

#### 26. print git commits using characters in commit message

```
git log --oneline --grep= "first commit by saad"
```

#### 27. print git commits having specific word or characters in code

```
git log --oneline -S"add()"
```

#### 28. print git commits having specific word or characters in code and also print the code

```
git log --oneline -S"add()" --patch
```

#### 29. print specific range of commits

```
git log --oneline  098aac..as1333
```

#### 30. print commits log which have changed some specific file

```
git log --oneline  file1.txt

if error then use -> git log --oneline -- file1.txt
```

#### 31. Shows the commit from last two commits till last commit

```
git show HEAD~2
```

#### 32. Shows the logs in file only

```
git show HEAD~2 --name-only
```

#### 33. Shows the changes from last

```
git diff HEAD~2 HEAD
```

#### 32. Shows the changes in file only

```
git diff HEAD~2 HEAD --name-only
```

## Git Checkout

#### 33. Move to the previous commit

```
git checkout 01480   #01480 is commit id
```

<b> Here the HEAD will move to the commit and leave the master node. </b>

<img src="./commit_Checkout.png"/>

#### 33. Move to the master commit

```
git checkout master
```

## Git Finding Bugs

#### 34. start debugging

```
git bisect start
```

#### 35. Bad commit tag

```
git bisect bad
```

#### 36. Good commit tag

```
git bisect good c9821  #c9821 is commit id (git log --oneline)
```

#### 37. Reset bisect to master node

```
git bisect reset
```

## Git Commit Authors

#### 38. See all the author

See all the options from `git shortlog -h`

```
git shortlog
```

## Git Blaming

#### 39. find out the author of specific piece of code

See all the options from `git blame -h`

```
git blame file1.txt
```

#### 40. find the blame with specific lines

```
git blame -e L 1,3 file1.txt
```

`-e` represent email and `L` represent Lines

## Git Tag

#### 41. Add a tag to a commit

See all the options from `git tag -h`

```
git tag v1.0.1  5ac56q   #5ac56q is commit id(git log --oneline)
```

# Git Branch

#### 42. Create a branch

```
git branch newBranch
```

#### 43. View all branches

```
git branch
```

#### 44. Switch to nwew branch

```
git switch newBranch
```

#### 45. Rename branch

```
git branch -m newBranch newNameofBranch
```

#### 46. Delete branch

```
git branch -d  newNameofBranch
```

- use `-D` to forcefully delete the branch even if you haven't commit it.

#### 47. View two branches commits

```
git log  master..newNameofBranch
```

#### 48. View code changes between two branches commits

```
git diff  master..newNameofBranch
```

#### 49. View files changes between two branches commits

```
git diff  --name-only master..newNameofBranch

or

git diff  --name-status master..newNameofBranch
```

# Git Stashing

It means putting the changes into the save place without committing it to the repo.

#### 50. Stash a change

```
git stash push -m "My first Stash"
```

#### 51. Add all files to Stash

```
git stash push -am "Add all Stash" # -a mean all and m mean message.
```

#### 51. View all Stashes

```
git stash list
```

#### 52. View changes in the Stash

```
git stash show @stash{1}  # @stash{1} is id from point 51

or

git stash show 1  # 1 is sequence of stashes
```

#### 53. Add stash into working directory (master branch)

```
git stash apply @stash{1}  # @stash{1} is id from point 51

or

git stash apply 1  # 1 is sequence of stashes
```

#### 54. drop stash

```
git stash drop @stash{1}  # @stash{1} is id from point 51

or

git stash drop 1  # 1 is sequence of stashes
```

#### 54. drop all stash

```
git stash clear

```

# Git Merge

Merging mean combining the branch changes with the master branch. Two type of merge

1. Fast Forward
2. 3 ways Merge

#### 55. Merge with Fast Forward

```
git log --oneline -a --graph

```

#### 56. Merge with Fast Forward

```
git merge newNameofBranch

```

#### 57. Merge with No Fast Forward

```
git merge --no-ff newNameofBranch

```
