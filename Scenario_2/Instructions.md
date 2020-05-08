# Rebase with no merge conflicts 

This exercise reflects the scenario when other Intuit engineers have made changes to master, and you must rebase your changes on top of theirs.

You will learn how to rebase your changes on a feature branch on top of other engineers' changes in the master branch, assuming there are no merge conflicts. 

What is rebasing?
[Rebase integrates changes from one branch to another](https://www.git-tower.com/learn/git/glossary/rebase), in this case allowing the user to integrate the changes made by another engineer in the `master-student-name` branch to your feature branch. 

# Instructions
1. Create a feature branch on your local machine called `Scenario2`.
1. Go onto Github, open `master-student-name` branch in origin, go to `Scenario_2`, and create a new file called `NewFile.txt`. What is in this file is not important. This simulates changes made by another engineer. 
1. On your local machine, add a new line to FileToModify.txt. These are your changes.
1. Rebase your changes on top of the new changes pulled from the remote `master-your-name`
1. Push changes to `my-fork`, and open a Pull Request (PR) to merge your changes with origin. 

# End Result
Afterwards, the files in the Scenario_2 folder on in origin/master-your-name should look like:

* Instructions.md
* FileToModify.txt
    ```
    Line 1 
    Line 2
    Line 3 - Added by you 
    ```
* NewFile.txt
    ```
    // Whatever "another engineer" added
    ```
    
<details>
  <summary>Solution</summary>

1. Create and checkout new branch for exercise 2 
    ```console
    $ git checkout -b scenario2
    ```
1. Make your changes
1. Stage and commit your changes 
    ```console
    $ git stage -A
    $ git commit -m "your message"
    ```
1. Update `master-your-name` with the latest changes from Git
    ```console
    $ git checkout master-your-name
    $ git pull
    $ git checkout scenario2
    ```
1. Rebase your changes on top of the new changes made by another engineer in master-your-name
    ```console
    $ git rebase master
    ```
    Optionally, you can check that your changes are on top of the changes imported from `master-your-name` with
    ```console
    $ git log
    ```
1. Push your changes to Github
    ```console
    $ git push
    ```
1. Open a Pull Request on Githunb to merge changes from `my-fork` to `master-your-name` branch in origin. 
</details>