# Undo a specific commit that has been pushed into a remote repo

This exercise reflects the scenario when you and/or other engineers have made and pushed several commits into a remote repository, only for you to realize at a later time that one of your earlier commits contains an issue you must fix. 

You will first revert back to the last working version of the code, make your fix, and "cherry-pick", or "stack", the newer commits (made by you or other engineers) on top.

The same process can also be used if the the series of commits have not been pushed into the remote repo yet (they still reside on your local machine), but there are often simpler "undo" commands that can be used. 

# New Git commands in this section
* `git revert`
* `git cherry-pick`

# Instructions
1. Update/reset your repo using the [cleaning instructions](https://github.intuit.com/Albertasaurus/git-practice/blob/master/Cleaning.md) in the main folder so that your `local` and `origin` repos are pointing the the same commit.
1. Create a feature branch on your local machine called `scenario5`
    <details>
    <summary>Solution</summary>
    
    ```console
    $ git checkout -b scenario5
    ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:
    
    A---B master-your-name, scenario5


    Remote my-fork:
    
    <nothing relevent to show>
    

    Remote origin:
    
    A---B master-your-name
    ```
    </details>

1. Make 2 seperate commits to `FileToModify.txt` so that your file looks like 
    ```
    Line 1 
    Line 2 
    commit 1
    ```
    after the first commit, and 
    ```
    Line 1 
    Line 2 
    commit 1
    commit 2
    ```
    after the second commit.

    Stage and push these changes to `my-fork/scenario4`, and open a PR to merge these changes with `origin/master-your-name`.
1. Suppose you realize you made a mistake in your first commit, and you actually meant to write `commit 1 - correct commit`, so revert revert back to commit 1. 
1. Stack the changes made by commit 2 on top of your corrected commit 1. 
1. Push your changes to `my-fork/scenario4`, then open a PR to merge these changes with `origin/master-your-name`. 