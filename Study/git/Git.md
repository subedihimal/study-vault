---
tags:
  - study
---
Git allows you to track different versions of a project over time.

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

**Fixing Errors or mistakes in commit**

- `git revert <hash>`
	Creates a new commit that is negative of the commit u want to revert
- `git reset --hard <hash>`
	Puts head to the commit mentioned resulting in all the commits after that hash being deleted.
- `git reset <hash>` -> without the --hard
	Puts the head to the commit and all the changes afte it is kept in the staging area