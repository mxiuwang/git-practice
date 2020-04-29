# git-practice
A repository to practice your git skills!

To start:
Copy the URL of the git-practice repo on github.intuit.com and run the command "git clone <URL>" in your terminal, in the folder where you want to copy this repository. 

Scenario #1: "Happy path - create a branch in my fork and PR it to main repo"
* Start with main repo
* Fork it
* Clone the fork to your local
* Create a Feature branch (eg PD-XYZ)
* Put some commits into the branch
* Push to fork
* PR from fork to main repo

Scenario #2: "Other Intuit engineers have added stuff to master - must rebase"
* Master moves on, no conflicts
* must rebase branch on top of master to get lastest

Scenario #3: "Other Intuit engineers have added stuff to master and there are merge conflicts"
* Master moves on, but with conflicts
* must rebase branch on top of master to get lastest
* must resolve merge conflicts
--------
Line 1
Line 2
Line 2A by User 1
Line 3
Line 4A by User 1
--------
Line 1
Line 2
Line 3
Line 3A by Michelle which would always be last
--------
Line 1
Line 2
Line 2A by User 1
Line 3
Line 4A by User 1
Line 3A by Michelle which would always be last

Scenario #4 "My team-mate has added other stuff to my feature branch and there are merge conflicts"
* Merge conflits on the branch itself because my teammate is helping me on the same Feature
* Teammate has added commits to PD-XYX and I have to rebase my changes on top, and there are merge conflicts
Rollback Scenarios
