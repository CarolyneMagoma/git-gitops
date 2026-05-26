# Git-Exercises


# 1. Multi-Branch Feature Intergration challenge

A team is building a cloud optimization dashboard.
you must create: feature login,dashboard and reports.
each branch should contain different files and atleast 3 commits. Merge all branches into develop, finally merge develop into main.

In the image below we can see that we have four branches.

![alt text](image.png)

In the login branch we created three files file1, file2 and file 3

![alt text](/git-exercise/screenshots/image.png)
 

we created three commits in the login branch.

![alt text](/git-exercise/screenshots/image-1.png)


In the dashboard branch we created 3 files, dashboard1, dashboard2 and dashboard3

![alt text](/git-exercise/screenshots/image3.png)

the git logs for feature/dashboard we have three commits

![alt text](/git-exercise/screenshots/image4.png)

In the reports branch we created 3 files , reports1, reports2 and report3

![alt text](/git-exercise/screenshots/image5.png)

The feature/reports branch has three commits

![alt text](/git-exercise/screenshots/image6.png)


We merge all the branches to develop branch.
as we can see we have all the files that we created from each branch onto the develop branch.

![alt text](image.png)

we merged the develop branch to main branch

![alt text](image8.png)

As we can see, the main branch contains all the files from all the branches now.

![alt text](image9.png)


# 2. Two Students Edit Same Line (Conflict Lab)

Two students edit the same cofiguration line in congig/app.env
Student A changes: 
APP_MODE=development
Student B changes:
APP_MODE=production

We created congig/app.env file in the dashboard and reports branches they both contained the APP_MODE=production and APP_MODE=development.

when we tried to merge, we can see we created a conflict because the app.env file in the two branches have different content that are somewhat similar and git doesnt know which data to keep, so it creates the conflict.

![alt text](/git-exercise/screenshots/image10.png)

To resolve this conflict we have to edit one of the file to something else
for our case we combined both.

![alt text](/git-exercise/screenshots/image7.png)


# 3. Recover From Disaster(Reset vs Revert)

A bad deployment was pushed to production

here have 5 commits and we did git revert

![alt text](/git-exercise/screenshots/image8.png)

The git revert did not delete the last commit but it added a new commit

![alt text](/git-exercise/screenshots/image9.png)

we created another commit with which we did the git reset --soft HEAD~1  on

![alt text](/git-exercise/screenshots/image10.png)

We can see that this time the commit got deleted but when you do git status files changes remain staged.

![alt text](/git-exercise/screenshots/image11.png)

We did another commit and we used git reset --hard HEAD~1 this time we removed the commit as we can see the git status, the staged changes were also removed, the working directory changes deleted permanently..

![alt text](/git-exercise/screenshots/image12.png)

The difference between git revert, git reset --soft and git reset --hard is that git revert does not delete the commits but adds a new commit, git reset --soft , removes the commits but does not remove it from the staging face, git reset --hard removes the commit permanently,from the staging,and the working directory.


# 4. Simulated Team Collaboration Workflow.

We used a repository called JosephKimiri, we forked it to make a copy to our repository so we can make changes.

![alt text](/git-exercise/screenshots/image13.png)

we copied the url to that forked repository.

![alt text](/git-exercise/screenshots/image14.png)

After that we git cloned the repo to our local repo, we can see that josephkimiri has been cloned to our local repository.

![alt text](/git-exercise/screenshots/image15.png)

we created a feature branch feature/timer.

![alt text](/git-exercise/screenshots/image16.png)

we created file on the feature branch and we have to push the changes to the remote repo.

![alt text](/git-exercise/screenshots/image17.png)

after pushing on the git repository this is what we have, to pull and compare 

![alt text](/git-exercise/screenshots/image18.png)

we added a comment to our pull request

![alt text](/git-exercise/screenshots/image19.png)

we created a ruleset for the github repository.



# 5. Git Rebase vs Merge History Lab

This lab we created 7 commits that were messy and then used rebase to squash some commits ie combined some commits.and rewrote others

![alt text](/git-exercise/screenshots/image.png)

Merge  Workflow

Combines branches, a merge commit may be created.
with merge keeps complete project history, it is safer for teams because history is not rewritten, it is easier to trace when branches were merged.

Rebase Workflow

git rebase creates a cleaner liner history, its easier to read ans review, reduces unnecessary merge commits.

merge=preserves history
rebase=rewrites history for cleanliness

# 6. Emergency Hotfix Production Scenario

we created the branches
 
![alt text](image-3.png)



# 7. Stash and Context Switching Excercise

You are halfway through feature development when an urgent bug arrives.

we created a new file in a branch and when i tried to change branches i got a warning.
telling me to commit the changes or stash them so we go with stashing.

![alt text](image.png) -stashing screenshot

to save unfinished work instead of commiting we stash so we can come back later

![alt text](image-1.png)

we switched to different branch, where we did our work and switched back to the branch with stashed work.

![alt text](image-2.png)


# 8. Accidental Secret Exposure Recovery

A developer accidentally commits:
● API keys
● passwords
● .env file



