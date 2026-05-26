# Git Scenario-Based questions(intermediate-advanced)

# 1. Merge Conflict Scenario
 - Two developers edited the same section of app.py in different branches. During merge, Git reports a conflict.

 Why did the conflict happen?
  the conflict happened because the two developers edited the same section of app.py in different branches, when git tries to merge,it could not automatically decide which changes to keep, so it reports a merge conflict.
how would you resolve it safely?
  to resolve the conflict, the developers should open app.py, review the conflicting section marked by git, and decide which changes to keep. They can choose one version, combine both changes if needed, then save the file, test the application, and commit the resolved merge.

# 2. Accidental Commit to Main

 - you accidentally committed unfinished code directlyy to the main branch instead of a feature branch.

  How would you move the work to a new branch safely?

   - if the commit was already pushed to a shared repository, using "git revert" is safer. 
   - To move the work to new branch safely, we use "git reset --hard HEAD~1" to remove the last commit from main. 

# 3. Remote Push Rejected.

 - when you try "git push origin main", and it rejects because the remote contains work you do not have locally.

  why did this happen?
   - The main contains commits that are not in the local repository.This is to prevent overwriting other people's work or losing changes on the remote branch
 what should you do next?
   - To resolve this, we have to pull the changes in the remote repository to our local repository by using "git pull" which will fetch and merge the changes from the remote repository to the local repository.

# 4. Delete Branch recovery
 - A teammate deleted a feature branch after merge, but later realized important work is missing.
  can the commits still be recovered?
   - yes
  which git tool could help?
   -  git reflog; shows the recent HEAD movements and deleted branch references, helping locate lost commits.
   - git log --all; searches through all commits, including commits not recently attached to a branch.

# 5. Sensitive Credentials Exposure

 - A developer accidentally pushed AWS key into GitHub.
  what immediate actions should be taked?
   - revoke or disable the exposed AWS key immediately
   - generate a new key if needed
   - remove the secret from the repository history.
  why is deleting the file alone not enough?
   - deleting the file alone is not enough because git keeps the full commit history. Even if the file is removed in a new commit, the aws key still exists in the previous commits and can be viewed or recovered from the repository history.

# 6. Rebase vs Merge Decision. 

  your team wants a clean linear Git history with fewer merge commits.
   
   would you recommend merge or rebase?
    - i would recomend the use of rebase because it moves commits from one branch onto another to create a linear project history.
 what are the risks involved?

   - it changes commit history
   - dangerous if commits were already  pushed /shared with team   

# 7. Emergency Production Hotfix

  your production application is down due to a login bug while new features are still being developed.
  
   which branch strategy should be used?
    - a hotfix branch strategy should be used.
     - the hotfix branch is created  from the production branch(usually main or master) so the critical bug can be fixed quickly without including unfinished feature development.

   Explain the workflow

    - 1. create a hotfix branch from main
    - 2. fix the login issue and test the application
    - 3. commit the fix
    - 4. merge the hotfix branch back into main and deploy to production.
    - 5. merge the same hotfis into development branch(develop) so future releases also contain the fix.
    - 6. delete the hotfix branch after successful deployment. 

# 8. Working Directory Interruption

  you are halfway through implementating a feature when your manager asks you to urgently fix another issue on main.
   - what Git feature helps you switch tasks safely without committing incomplete work?
     
     - to switch tasks without commiting incomplete work we use "git stash" 

# 9. Wrong Commit Message
 
  you committed "git commit -m "stuff fixed""
   
   - How can you correct the commit message professionally without creating another commit?
    
    - To correct the commit message professionally we can use the "git commit --amend" this allows us to modify the most recent commit message.

# 10. Local Branch Behind Main

  your feature branch is several commits behind the latest main branch.
   - how can you update your branch?
     -  to update the local repository, we git merge, this merges the changes from one branch to the main branch.
     
   Compare merge vs rebase approaches.

    - merge preserves original timeline (non-destructive), 
    git rebase rewrites hidtory into a straight line.
    - merge easy to see when branches were joined git,rebase is harder to see the "truth" of when work happened.
    - merge is simple and safe, rebase is powerful but dangerous on shared branches
    - merge resolved once in a single merge commit, rebase resolved commit-by-commit as they are reapplied.

# 11. Multiple Remote Repositories.

A DevOps engineer pushes code to both GitHub and GitLab from one local repository.
 - Why might organizations use multiple remotes?

    - backup and redundancy in case one platform becomes unavailable.
    - different workflows for development, CI/CD, or deployment.
    - Mirroring repositories between platforms like github and gitlab
    - separating internal and external collaboration.
    - disaster recovery and better availability

   - How would you push to a specific remote?
 
     - to push to specific remote, specify the remote name in the push command.

# 12. CI/CD Deployment Failure
  
  After merging code into main, the CI/CD pipeline fails and production deployment breaks.
   - How can Git help identify the problematic changes?
    - git can help identify the problematic changes by checking recent commits, comparing changes and tracing who introduced the issue.
   - How can you safely roll back?
    - use git revert, it creates a new commit that reverses the problematic changes, this is safe because history is preserved.
    - Use git reset, moves the branch back to previous state, rewrites history, its dangerous on shared branches if commits were already pushed.

# 13. Large Feature Development.

 A developer works on one branch for three months without merging updates from main.
  - What problems can this create?
    - Large and difficult merge conflicts.
    - The feature branch may become incompatible with the latest main branch.
    - Higher risk of bugs and integration failures.
    - CI/CD pipelines may fail after merging.
    - Code reviews become harder because there are too many changes at once.
    - Other developers may have changed the same files or architecture.
    - Delayed feedback and testing.
    - Deployment becomes riskier.
  - What best practices could prevent this situations?
    - merge or rebase frequently
    - use smaller feature branches
    - commit and push changes regulary
    - use pull requests frequently
    - use feature flags
    - run continuous integration(CI) checks
    - communicate with the teaam

# 14. Detached HEAD Situation
 
 A Student checks out a specific commit directlyy using "git checkout a1b2c3d".
  - What is a detached HEAD state?
    - This happens when a user checks a specific commit instead of a branch.
  - Why can it become dangerous? 
    - Any new commits made in detached HEAD state can become “lost” because no branch references them.
    - If the user switches branches without saving those commits, Git may eventually garbage collect them.
    - Developers may mistakenly think their work is safely stored when it is not connected to a branch.

# 15. Protected Main Branch.

  your company prevents direct pushes to the main branch.
   - Why is branch protection important?
     - Prevents direct pushes that could break production.
     - Ensures code is reviewed before merging.
     - Protects stable and production-ready code.
     - Reduces human errors such as accidental deletions or force pushes.
     - Enforces CI/CD checks, testing, and approval policies.
     - Improves security and accountability by tracking reviews and approvals.
   - How do pull requests improve software quality and collaboration?
     - Allowing team members to review code before merging.
     - Detecting bugs, security issues, and bad practices early.
     - Encouraging discussion and knowledge sharing among developers.
     - Running automated tests and CI/CD validation before merge.
     - Providing documentation and history of why changes were made.
     - Improving code consistency through reviews and standards.