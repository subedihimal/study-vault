---
tags:
  - Blogs
---
Git is one of the most popular and widely used **version control system** in the modern coding landscape. Even in a rare chance that some tech companies do not use git they probably use some kind of version control system that is similar to git. So this fact makes learning and being familiar with git a  non-negotiable necessity for any aspiring coders or software engineers.

Now, although we highlighted the need for learning git. Some more questions may arias in you mind. 
How do u actually use git?
How do u tell it what u want to do?
How do u tell git when to save something?
How do u tell git what to track or what amount of code is considered so called "new version"?

------------------------------------------------------------------------

**The answer to this question comes from the concept of Git Commands***
### Git Commands
Git commands are basically instructions you write to git that tells it what to do. For you to have be able to write git commands first of all u will need to have git installed in your computer. Lets go through some common and widely used git commands and learn what they actually do.

1. git init 
	As the name suggests it initializes git in the directory you run this command at. After git is initialized it is able to keep track of changes u made also you will be able to use other git commands as well.
	Syntax:
		git init
2. git add
	 It allows you to add all the changes you have made to staging area. Staging area is the place from where you can commit the changes. 
	 Syntax:
		git add <file or directory >   -> for adding individual file or directory
		git add .                                  -> for adding all the changes of files into the staging area
		
3. git  commit 
	Commit lets u create a version for the project. It generates a unique identifier for each commit. So u can go back to a commit you made in the past or see what changes have been made in between two commits. After the commit is done its like saving the changes into git.
	You can also use -m flag to write a short message about the particular commit. It is considered good practice to write it in present tense and also to use words like (add, refactor, remove, feat )
	Syntax:
		git commit -m "Your short description to describe the commit"
4. git push
	This allows you to push the changes to a remote server most popularly used is github. This allows you to have a backup, as well as make the code changes accessible for other collaborators to use.
	Syntax:
		 git push origin main
5. git log
	This displays all the commits that have been made in the past along with their unique identifier, commit message as well as  date and time of the commit. 
	Syntax
		git log
		git log --oneline               -> For more compact and cleaner output, it also removes                                                        author and date-time details
6. git diff
	This command allows you to see the different changes that occurred between two different commits. It is very useful when u need to know which files were changed and what were the changes between the commits.
	Syntax:
		git diff <commit id1> <commit di2>
7. git status
	 Shows the overall current status of git. What files are stages which are modified after the last commit or which new files have been created and are untracked.
	 Syntax 
		 git status