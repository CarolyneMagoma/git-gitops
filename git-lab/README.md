# LAB 1 - Intermediate Git Collaboration

you are a part of a development team building a company website. Multiple developers are working on different features simultaneously.

# Lab setup

we created a directory, initialize the repo, created a homepage file and committed the initial file.

![alt text](/git-lab/screenshots/image.png)

# Part 1 - Create Feature Branches

in thi part we creates a new branch called feature-navbar, added a file called index.html and committed the changes.

![alt text](/git-lab/screenshot/image-1.png)

# Part 2 - Simulate Another Developer

we created another branch called feature-footer from the master branch.

![alt text](/git-lab/screenshot/image-2.png)

# Part 3 - Create Merge Conflict

we edited the same line in both branches, and when we try to merge the changes to the master we can see that we have a merge conflict.

![alt text](/git-lab/screenshot/image-3.png)

# Part 4 - Resolve Conflict

we opened the conflicted file and edited it, we staged the changes,and committed them .

![alt text](/git-lab/screenshot/image-4.png)


here is the graph.

![alt text](/git-lab/screenshot/image-5.png)

# LAB 2 - Advanced Git & DevOps workflow Lab

you are part of a cloud engineering team managing production infrastructure and application deployment, production issues appears while new features are under development.

# Lab setup

we created a directory "cloud-platform" and cd into it we then initialized the repository, created an app.txt file and commited the changes.

![alt text](/git-lab/lab2_screenshots/image.png)


# Part 1 - Feature Development

we created a new branch.

![alt text](/git-lab/lab2_screenshots/image-1.png) 

# Part 2 - Production Hotfix

we created another branch "hotfix-authentication" and merged the branch to the master branch

![alt text](/git-lab/lab2_screenshots/image-2.png)

# Part 3 - Rebase Feature Branch

we switched to feature-monitoring branch and did git rebase master, this gives a conflict.


![alt text](/git-lab/lab2_screenshots/image-3.png)

we solved the conflict and continued the rebase

![alt text](/git-lab/lab2_screenshots/image-4.png)\

# Part 4 - Stashing Scenario

modify files without committing.
we used git stash to save uncommitted files, changed to another branch and went back to the branch where we stashed our files and restored them to modified file.

![alt text](/git-lab/lab2_screenshots/image-5.png)

# Part 5 - Multiple Remote Repositories

![alt text](/git-lab/lab2_screenshots/image-6.png)

# Part 6 - Release Tagging

![alt text](/git-lab/lab2_screenshots/image-8.png)

![alt text](/git-lab/lab2_screenshots/image-7.png)

# Part 7 - Undo Mistake

we commited changes 

![alt text](/git-lab/lab2_screenshots/image-9.png)

we used git reset to undo the changes committed.

![alt text](/git-lab/lab2_screenshots/image-10.png)




