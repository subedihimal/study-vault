---
tags:
  - Blogs
---

After u initialize a folder with "git init" command, git creates a folder name ".git". As the folder name starts with "." it is hidden in most of the file explorers.  It uses that folder to keep track of all the commits and changes you have made. Git keeps track of changes in a similar to how linked list work. Rather then saving all the files and folder as is when a commit is made, it only saves the changes that happed in the file after the previous commit.
	
	Some Key Concepts of git
	Head -> Latest commit is called head
	Hash -> Unique id given to each commit
	
	**Branching in Git**
	Branching can be utilized when you are working on a experimental or new feature and only want to update the main version of the project after you have completed the feature.
	![[blog3.png]]
	---
	###Exploring git folder structure
	
	- HEAD: Stores the data about the branches and what branch is currently being used
	- refs/heads: Stores the hash of the current branch
	- objects: All the changes are stored here with their first two hash code as a folder name for better storage. If u explore into this you will see files with commit hash. Each file includes hash of previous commit, author, commit message and hash of the tree is it part of.
	---
	Some more complex git commands
	**Fixing Errors or mistakes in commit**
	
	- `git revert <hash>`
		Creates a new commit that is negative of the commit u want to revert
	- `git reset --hard <hash>`
		Puts head to the commit mentioned resulting in all the commits after that hash being deleted.
	- `git reset <hash>` -> without the --hard
		Puts the head to the commit and all the changes afte it is kept in the staging area