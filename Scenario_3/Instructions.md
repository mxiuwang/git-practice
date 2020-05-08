# Rebase with merge conflicts

This exercise reflects the scenario when you rebase your changes on top of changes made by other Intuit engineers, but there is a merge conflict you must resolve. 

You will first attempt to rebase on a feature branch on top of other engineers' changes in the master branch, manually resolve any merge conflicts, merge the changes with no conflicts, then push all changes to the remote. 

What is a merge conflict?
A [merge conflict](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts) occurs when different developers edit the same code on different feature branches, then try to merge them together. Git doesn't know which set of changes to accept, and a merge conflict results. 

# Instructions 
1. Create a feature branch on your local machine called `Scenario3`
1. Go onto Github, open `master-student-name` branch in origin, go to `Scenario_3`, open `FileToModify.txt`, and add some text on Line 3.
1. On your local machine, open `FileToModify.txt`, and add in some text (different text from the previous step).
1. Rebase your changes on top of the new changes pulled from the remote `master-your-name`
1. Resolve any merge conflicts 
1. Merge changes with the `master-your-name` branch, push them to `my-fork`, and open a PR to merge your changes with origin. 

# End Result
Afterwards, `FileToModify.txt` should look like the following in origin/master:
```
Line 1
Line 2
Line 3 - Line you chose to keep
```