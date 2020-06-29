# Undo a commit that has been merged with its parent branch

This scenario reflects the scenario when you wish you undo a commit that has merged a feature branch with its parent branch. Perhaps you made a mistake in your feature branch, and you wish to correct it before merging it with its parent. 

You will revert back the last commit before the merge, make your adjustments, and re-commit and push your changes. 

# New Git commands in this section
* `git revert -m 1`
* `git revert -m 2`

# Instructions
1. [Reset your repo](https://github.intuit.com/Albertasaurus/git-practice/blob/master/Cleaning.md) to a clean state
1. Create a feature branch on your local machine called `scenario7`.
    <details>
    <summary>Solution</summary>

    ```console
    $ git checkout -b scenario7
    ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:
    
          C scenario7
         /
    A---B master-your-name


    Remote my-fork:
    
    <nothing relevent to show>
    

    Remote origin:
    
    A---B master-your-name
    ```
    </details>
1. Add a line to `FileToModify.txt` in the Scenario_7 folder, and push your changes to `my-fork/scenario7`. Then, open a PR and merge these changes with `origin/<master-your-name>`.
    <details>
    <summary>Solution</summary>

    1. Add a line to `FileToModify.txt` so that it looks like:
        ```
        Line 1 
        Line 2
        Line 3 - change #1 
        ```
    1. Stage, commit, and push your changes to `my-fork/scenario7`
        ```console
        $ git stage -A
        $ git commit -m "change #1"
        $ git push -u my-fork scenario7
        ```
    1. Open a Pull Request (PR) on Github to merge changes from `my-fork/scenario7` to `origin/master-<your-name>`.
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:
    
    A---B---C scenario 7 (change #1)


    Remote my-fork:
    
    A---B---C scenario 7 (change #1)
    

    Remote origin:
    
    A---B---C' scenario 7 (change #1)
    ```
    </details>
1. 