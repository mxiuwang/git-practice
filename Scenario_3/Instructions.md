# Rebase with merge conflicts

This exercise reflects the scenario when you rebase your changes on top of changes made by other Intuit engineers, but there is a merge conflict you must resolve. 

You will first attempt to rebase on a feature branch on top of other engineers' changes in the master branch, manually resolve any merge conflicts, merge the changes with no conflicts, then push all changes to the remote. 

What is a merge conflict?
A [merge conflict](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts) occurs when different developers edit the same code on different feature branches, then try to merge them together. Git doesn't know which set of changes to accept, and a merge conflict results. 

# Instructions 
1. Create a feature branch on your local machine called `Scenario3`
1. Go onto Github, open `master-student-name` branch in origin, go to `Scenario_3`, open `FileToModify.txt`, and add `Line 3A - Added by another engineer`.
1. On your local machine, open `FileToModify.txt`, and add in `Line 3B - Added by you`.
1. Rebase your changes on top of the new changes pulled from the remote `master-your-name`
1. Resolve any merge conflicts 
1. Merge changes with the `master-your-name` branch, push them to `my-fork`, and open a PR to merge your changes with origin. 

# End Result
Afterwards, `FileToModify.txt` should look like the following in origin/master:
```
Line 1
Line 2
Line 3A - Added by another engineer
Line 3B - Added by you
```

<details>
  <summary>Solution</summary>

1. Create and checkout new branch for exercise 23
    ```console
    $ git checkout -b scenario3
    ```
1. Go to Github, open `Scenario_3/FileToModify.txt` from `master-your-name`, and add a line `Line 3A - Added by another engineer`
1. On your local `scenario3` branch, open `FileToModify.txt` and add a line `Line 3B - Added by you`.
1. Stage and commit your changes 
    ```console
    $ git stage -A
    $ git commit -m "your message"
    ```
1. Update `master-your-name` with the latest changes from Git
    ```console
    $ git checkout master-your-name
    $ git pull
    $ git checkout scenario3
    ```
1. Try to rebase your changes on top of the new changes made by another engineer in master-your-name. A merge conflict should appear.
    ```console
    $ git rebase master
    ```
1. Resolve the merge conflict.
    First, go to the file where the merge conflict is occuring. You should see something like this:
    ```
    <<<<<<< HEAD
    Line 3A - Added by another engineer
    =======
    Line 3B - Added by you
    >>>>>>> Line 3B Added by you merge conflict 
    ```
    The content between `<<<<<<< HEAD` and `=======` is what is currently at the head, which is a reference to the last commit in the current branch. 

    The content between `=======` and `>>>>>>> Line 3B Added by you merge conflict` is the content you are trying to add, which is conflicting with the content from the last commit. 

    In this case, we want to keep both lines 3A and 3B. So we simply drag line 3B in between `<<<<<<< HEAD` and `=======`, make sure there's no other merge conflicts, and delete the merge conflict markers `<<<<<<< HEAD`, `=======`, and `>>>>>>> Line 3B Added by you merge conflict`.

    Your final result, after you've resolved the merge conflicts, should look like this:
    ```
    Line 1
    Line 2
    Line 3A - Added by another engineer
    Line 3B - Added by you
    ```
1. Add your changes, and continue the rebase.
    ```console
    $ git add -A 
    $ git rebase --continue
    ```
1. Check your rebased changes are in the expected order
    ```console
    $ git log
    ```
1. Push your changes to Github
    ```console
    $ git push -u my-fork scenario3
    ```
1. Open a Pull Request on Githunb to merge changes from `my-fork` to `master-your-name` branch in origin. 
</details>