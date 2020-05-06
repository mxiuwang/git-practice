# git-practice
About this Repo:
This is a repository is a Git practice package with exercises designed to help you develop your Git skills, in the way it is most commonly used at Intuit! This repo is intended for any Intuit employee learning Git for the first time, or engineers wishing to familiarize themselves with the Git workflow at Intuit. 

The repository contains Scenarios in which any Intuit engineers may face, and guides you through how to make, submit, and merge a code change. In general, Scenarios are designed in ascending level of complexity. Each Scenario contains a set of instructions, some StartCode an engineer will attempt to convert to the FinalCode, and the solution. 


Setup:
1. Clone "git-practice" repo on your local machine by copying the URL of the git-practice repo and typing `git clone https://github.intuit.com/Albertasaurus/git-practice` in your terminal, in the folder where you wish you clone it. The remote located at `https://github.intuit.com/Albertasaurus/git-practice` will be referred to as "origin".
1. Fork the above repo on your account by opening the repo on Github, and clicking the "fork" button on the top right-hand corner. Observe that the URL of this remote is `github.intuit.com/<your-name>/git-practice`. From now on, this fork will be referred to as `my-fork`. 
1. Configure my-fork as a remote in your local `git-practice` repo by typing `git remote add my-fork` in the terminal, opened in your local git-practice repo. This adds "my-fork" as an alias, pointing to the remote `github.intuit.com/<your-name>/git-practice`. You can verify this step is done correctly with the command `git remote -v`, and seeing that `my-fork` is an alias pointing to `github.intuit.com/<your-name>/git-practice`.
1. Create a new branch named `master-<yourName>` in your local repo by checking out the master branch, and typing the command `git checkout -b master-<your-name>`. We are doing this to pretend `master-<your-name>` is real master branch. Normally, we do not have to do this, but we don't want the changes made in these exercises to affect the real master. 
1. Push `master-<your-name>` to origin with the command `git push -u origin master-<your-name>`. 
1. Verify that the alias `origin` points to [https://github.intuit.com/Albertasaurus/git-practice](https://github.intuit.com/Albertasaurus/git-practice) and alias `my-fork` points to [github.intuit.com/<your-name>/git-practice](github.intuit.com/<your-name>/git-practice)

```git remote -v```

Expected output: 
```my-fork	https://github.intuit.com/mwang5/git-practice?organization=mwang5 (fetch)
my-fork	https://github.intuit.com/mwang5/git-practice?organization=mwang5 (push)
origin	git@github.intuit.com:Albertasaurus/git-practice.git (fetch)
origin	git@github.intuit.com:Albertasaurus/git-practice.git (push)
```

For Each Scenario:
1. Create a new branch in your local repo named `scenario1`, `scenario`...and so on. Do the exercise in each secenario on the respective branch.
1. Do each exercise, save the changes you made, and push those changes to its remote counterpart in `my-fork`.
1. Open a Pull Request (PR) to merge those changes from `my-fork` to `master-your-name` in origin. 

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
