# Rebase on Feature Branch with Merge Conflicts 

This exercise reflects the scenario when you rebase your changes on top of changes made by other Intuit engineers on your feature branch, but there is a merge conflict you must resolve. 

You will first attempt to rebase your changes made on feature branch on top of other engineers' changes in the same branch, and manually resolve any merge conflicts. Then, push the feature branch to remote. 

# Instructions
1. Check out`master-your-name` branch in `my-fork`, and update your repo so that your local machine, `origin`, and `my-fork` are all pointing the the latest commit.
    <details>
    <summary>Instructions</summary>

    Ensure all your changes are pushed to Github
    ```console
    $ git stage -A
    $ git commit -m "your message"
    $ git push -u my-fork master 
    ```

    Ensure your local machine contains all changes, and pointers are pointing to the latest commit 
    ```console
    $ git pull 
    ```

    Ensure that `(HEAD -> master-your-name)`, and `(origin/master-your-name, origin/HEAD)` are pointing to the latest commit, and `(my-fork/master)` contains the latest changes. 
    ```console
    $ git log
    ```
    </details>
1. Create a feature branch on your local machine called `scenario4`
    <details>
    <summary>Solution</summary>
    
    ```console
    $ git checkout -b scenario3
    ```
    </details>
1. Perform your FIRST set of changes on the `scenario4` branch, specifically on the `FileToModify.txt` in the `Scenario_4` folder on your local machine. Stage, commit, push, and PR your changes to remote `origin/master-your-name`.
    <details>
    <summary>Solution</summary>

    1. Open `FileToModify.txt` in the `Scenario_4` folder, and add in two lines so that your `FileToModify.txt` should look something like:
        ```
        Line 1
        Line 2
        Line 3A - Added by you
        Line 3B - Also added by you
        ```
    1. Stage and commit, and push your changes to `my-fork`
        ```console
        $ git stage -A
        $ git commit -m "added 2 lines"
        $ git push -u my-fork scenario4
        ```
    1. Open a PR to merge your changes from `my-fork` to `origin`
    </details>
1. Simulate changes made by another engineer by going to Github, opening the `FileToModify.txt` file in `origin/scenario4` with the new changes you pushed, and modifying one of the lines you added. Commit and push these changes. 
    <details>
    <summary>Solution</summary>

    1. Open `FileToModify.txt` in `origin/scenario4`, and change one of the lines you just added so that your `FileToModify.txt` now looks something like:
        ```
        Line 1
        Line 2
        Line 3A - Added by you
        Line 4A - Overriding changes made by another engineer
        ```
    1. Commit and push the changes to `origin/scenario4` using the Github website. See previous scenario for more detailed instructions. 
    </details>
1. In the `scenario4` branch on your local repository, perform your SECOND set of changes on the `FileToModify.txt`. Commit these changes.
    <details>
    <summary>Solution</summary>

    1. Open `FileToModify.txt` in the `Scenario_4` folder, and add in two lines so that your `FileToModify.txt` should look something like:
        ```
        Line 1
        Line 2
        Line 3A - Added by you
        Line 3B - Also added by you
        ```
    1. Stage and commit, and push your changes to `my-fork`
        ```console
        $ git stage -A
        $ git commit -m "added 2 lines"
        $ git push -u my-fork scenario4
        ```
    1. Open a PR to merge your changes from `my-fork` to `origin`
    </details>