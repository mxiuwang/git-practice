# Rebase with no merge conflicts 

This exercise reflects the scenario when other Intuit engineers have made changes to master, and you must rebase your changes on top of theirs.

You will learn how to rebase your changes a feature branch on top of other engineers' changes in the master branch, assuming there are no merge conflicts. 

What is rebasing?
[Rebase integrates changes from one branch to another](https://www.git-tower.com/learn/git/glossary/rebase), in this case allowing the user to integrate the changes made by another engineer in the `master-student-name` branch to your feature branch. 

# Instructions
1. Create a feature branch on your local machine called `Scenario2`.
1. Go onto Github, open `master-student-name` branch in origin, go to `Scenario_2`, and create a new file called `NewFile.txt`. What is in this file is not important. This simulates changes made by another engineer. 
1. On your local machine, add a new line to FileToModify.txt. These are your changes.
1. Rebase your changes on top of the new changes in the remote master-your-name
1. Push changes to `my-fork`, and open a Pull Request (PR) to merge your changes with origin. 

Code on your local machine:

Branch: master (local)
Line 1 
Line 2 

[You make a copy of master called "your-branch"]

Branch: your-branch
Line 1 
Line 2
Line 3A - Added by you 

[Meanwhile, master branch has moved on]

Branch: master
Line 1
Line 2

Line 3B - Added by another engineer  

You want upstream master to look like this:

Branch: master (upstream)
Line 1
Line 2 
Line 3A - Added by you
Line 3B - Added by another engineer 