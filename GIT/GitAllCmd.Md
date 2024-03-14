# Git
## Content
1. Creating Snapshot
2. Browsing History
3. Branching & Marging
4. Rewriting History

## 1.  Creating Snapshots

### a ). Initializing a repository
 ~ `git init`  

### b ). Staging files

~`git add Filename` &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; *# Stages a single file*

~ `git add Filename1 filename2` &emsp;&emsp;&emsp;*# Stages multiple files*

~ `git add * .html`&emsp;&emsp; *# Stages with a pattern*

~ `git add .` &emsp;&emsp; *# Stages the current directory and all its content*


### c ). Viewing the status

~ `git status `  &emsp;&emsp; *# Full status*

~ `git status -s` &emsp;&emsp;*# Short status*

### d ). Committing the staged files 

~ `git commit -m "Message"` &emsp;&emsp; *# Commits with a one-line message*

~ `git commit` &emsp;&emsp;  *# Opens the default editor to type a long message*

### e ). Skipping the staging area

~ `git commit -am "Message"`

### f ). Removing files

~ `git rm File.html`  &emsp;&emsp; *#Removes from working directory and staging area*

~ `git rm --cached File.html`&emsp;&emsp; *#Removes from staging area only*

### g ). Renaming or moving files

~ `git mv file.html file.txt`

### h ). Viewing the staged/unstaged changes

~ `git diff` &emsp;&emsp;  *#Shows unstaged changes*

~ `git diff --staged` &emsp;&emsp;   *#Shows staged changes*

~ `git diff --cached` &emsp;&emsp; *#Same as the above*

### i ). Viewing the history

~ `git log` &emsp;&emsp;  *#Full history*

~ `git log --oneline` &emsp;&emsp;  *#Summary*

~ `git log --reverse` &emsp;&emsp; *#Lists the commits from the oldest to the newest*

### j ). Viewing a commit

~ `git show 921a2ff`  &emsp;&emsp; *#Shows the given commit*

~ `git show HEAD` &emsp;&emsp;  *#Shows the last commit*

~ `git show HEAD-2`&emsp;&emsp;  *#Two steps before the last commit*

~ `git show HEAD:file.js` &emsp;&emsp; *#Shows the version of file js stored in the last commit*

### k ). Unstaging files (undoing git add)

~ `git restore --staged file.js` &emsp;&emsp; *#Copies the last version of file js from repo to index*

### l ). Discarding local changes

~ `git restore file.js` &emsp;&emsp;  *#Copies file js from index to working directory*

~ `git restore filel.js file2.js ` &emsp;&emsp; *#Restores multiple files in the working directory*

~ `git restore .` &emsp;&emsp; *#Discards all local changes (except untracked files)*

~ `git clean -fd` &emsp;&emsp;  *#Removes all untracked files*


### m ). Restoring an earlier version of a file

~ `git restore --source=HEAD-2 file.js`

## 2. Browsing History

### a.) Viewing the history

~ `git log --stat`&emsp;&emsp;  *#Shows the list of modified files*

~ `git log --patch` &emsp;&emsp; *#Shows the actual changes (patches)*

### b.) Filtering the history

~ `git log -3` &emsp;&emsp;  *#Shows the last 3 entries*

~ `git log --author="Mosh"`

~ `git log --before="2020-08-17"`

~ `git log --after="one week ago"`

~ `git log --grep="GUI"`  &emsp;&emsp; *#Commits with "GUI" in their message*

~ `git log -S"GUI"`  &emsp;&emsp; *#Commits with "GUI" in their patches*

~ `git log hashl..hash2` &emsp;&emsp;  *#Range of commits*

~ `git log file.txt` &emsp;&emsp;  * #Commits that touched file.txt*


### c.) Formatting the log output

~ `git log --pretty=format"%an committed %H"`

### d.) Creating an alias

~ `git config --global alias.lg "log --oneline"`

### e.) Viewing a commit

~ `git show HEAD-2`

~ `git show HEAD-2.filel.txt` &emsp;&emsp; *#Shows the version of file stored in this commit*


### f.) Comparing commits

~ `git diff HEAD-2 HEAD` &emsp;&emsp; *#Shows the changes between two commits*

~ `git diff HEAD-2 HEAD file.txt` &emsp;&emsp;  *#Changes to file.txt only*


### g.) Checking out a commit

~ `git checkout BranchName` &emsp;&emsp;  *#Checks out the given commit*

~ `git checkout master`  &emsp;&emsp;  *#Checks out the master branch* 


### h.) Finding a bad commit

~ `git bisect start`

~ `git bisect bad` &emsp;&emsp;  *#Marks the current commit as a bad commit*

~ `git bisect good ca49180` &emsp;&emsp;  *#Marks the given commit as a good commit*

~ `git bisect reset`   &emsp;&emsp; *#Terminates the bisect session*

### Viewing the history of a file

git log file.txt

git log-stat file.txt

git log-patch file.txt

### Finding the author of lines

git blame file.txt

#Shows the commits that touched file txt

#Shows statistics (the number of changes) for file.txt

#Shows the patches (changes) applied to file.txt

#Shows the author of each line in file.txt

### Tagging

git tag v1.0

git tag v1.0 5e7a828

git tag

git tag -d v1.0

#Tags the last commit as v1.0

#Tags an earlier commit

#Lists all the tags

#Deletes the given tog

## 3. Branching & Merging

### Managing branches

git branch bugfix

git checkout bugfix

git switch bugfix

git switch-C bugfix

git branch-d bugfix

#Creates a new branch called bugfix

#Switches to the bugfix branch

#Same as the above

#Creates and switches

#Deletes the bugtis branch

### Stashing

git stash push-m "New tax rules

### Creates a new stash

git stash list

git stash show stash@[1]

git stash show !

git stash apply 1

git stash drop 1

git stash clear

#Lists all the stashes

#Shows the given stash

#shortcut for stash@[1]

#Applies the given stash to the working dir

#Deletes the given stash

#Deletes all the stashes

### Merging

git merge bugfix

#Merges the buglix branch into the current branch

git merge-no-ff

bugfix#Creates a merge commit even if FF is possible

git merge-squash bugfix #

### Performs a squash merge

git merge-abort

#Aborts the marge

### Viewing the merged branches

git branch --merged

#Shows the merged branches

git branch --no-merged

#Shows the unmerged branches

### Rebasing

git rebase master

#Changes the bose of the current branch

### Cherry picking

git cherry-pick dad47ed

#Applies the given commit on the current branch


## 4. Collaboration

### Cloning a repository

~ `git clone url`

### Syncing with remotes

~ `git fetch origin master` &emsp;&emsp; *#Fetches master from origin*

~ `git fetch origin` &emsp;&emsp; *#Fetches all objects from origin*

~ `git fetch` &emsp;&emsp; *#Shortcut for "git fetch origin"*

~ `git pull`  &emsp;&emsp; *#Fetch + merge*

~ `git push origin master`&emsp;&emsp;  *#Pushes master to origin*

~ `git push` &emsp;&emsp;  *#Shortcut for "git push origin master*

### Sharing tags

~ `git push origin v1.0` &emsp;&emsp;  *#Pushes tag v1.0 to origin*

~ `git push origin -delete v1.0`

### Sharing branches

~ `git branch -r` &emsp;&emsp;  *#Shows remote tracking branches*

~ `git branch -w` &emsp;&emsp;  *#Shows local & rernote tracking branches*

~ `git push -u origin bugfix` &emsp;&emsp; *#Pushes bugfix to origin*

~ `git push -d origin bugfix`&emsp;&emsp;  *#Removes bugfix from origin*

### Managing remotes

~ `git remote` &emsp;&emsp;  *#Shows remote repos*

~ `git remote add upstream url` &emsp;&emsp;  *#Adds a new remote called upstream*

~ `git remote rm upstream` &emsp;&emsp;  *#Remotes upstream*




























