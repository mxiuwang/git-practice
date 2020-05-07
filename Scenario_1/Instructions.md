# Make changes in a feature branch and merge them to master

This exercise reflects the best-case scenario, where you (an engineer) pull code down from Git, make some changes in feature branch, and push them up to to Git, and merge with remote origin with no additional changes made by other engineers, and does not cause any merge conflicts. 

What is a feature branch?

[A feature branch is simply a separate branch in your Git repo used to implement a single feature in your project.](https://bocoup.com/blog/git-workflow-walkthrough-feature-branches)

# Instructions
1. Modify FileToModify.txt so that it looks like the End Result outlined below. 
1. Push changes to `my-fork`, and open a Pull Request (PR) to merge your changes with origin. 

# End Result
Afterwards, `FileToModify.txt` should look like the following in the origin/master:
```
Line 1 
Line 2
Line 3 - Added by you
```

<details>
  <summary>Solution</summary>
  
In code:
1. Add a new line to FileToModify.txt, save file.

In Terminal:
1. Stage your changes 
```git stage -A```
1. `git commit -m "your commit message" ` // commits changes
1. `git push -u my-fork scenario1` // pushes changes from your current branch `scenario1` to the remote `my-fork`

On Github:
1. Open a Pull Request to merge changes from `my-fork` to `master-your-name` branch in origin. 
</details>