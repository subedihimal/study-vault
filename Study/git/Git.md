---
tags:
  - study
---
Git allows you to track different versions of a project over time.

**Common Commands**
- **`git init`**  
  Initializes Git in the current folder and creates a `.git` directory where all version history is stored.

- **`git add`**  
  Stages files by taking a *snapshot* of their current state.  
  → Does **not** save changes permanently.

- **`git commit`**  
  Saves the staged changes to the project history with a commit message.

- **`git log`**  
  Displays the commit history with details like commit ID, author, and date.

- **`git status`**  
  Shows:
  - Staged files
  - Modified but unstaged files
  - Untracked files

- **`git diff <old_commit> <new_commit>`**  
  Shows the differences between two commits.

- `git remote add origin <url>`
	Add a server to push your commits to for backup and collaboration

- ``git remote set-url origin <new-url>``
	Update the url of the origin

**Fixing Errors or mistakes in commit**

- `git revert <hash>`
	Creates a new commit that is negative of the commit u want to revert
- `git reset --hard <hash>`
	Puts head to the commit mentioned resulting in all the commits after that hash being deleted.
- `git reset <hash>` -> without the --hard
	Puts the head to the commit and all the changes afte it is kept in the staging area

**Branches In Git**

- `git branch`
	Shows what branch you are currently in and all the available branches
- `git checkout <branch-name>`
	Change the branch you are working on
- `git branch -d <branch-name>` OR for force delete -D flag
	Deletes the branch with that particular name
-  `git merge feat` -> **To merge feature branch into main** checkout the main branch
	Merges feature branch into the main branch. It doesn't rebase just merges all the commits
- git merge --squash feat
	Doesn't preserve the commit history of the feature branch **You need to commit after squash merge**
- `git rebase main`
	To sync your feature branch with the main branch. Better then merge as it doesnt make extra unnecessary commit.
- `git push --set-upstream origin feat`
	When u make the branch in local and want to push it to the github repo