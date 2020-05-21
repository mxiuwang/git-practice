# Rebase with no merge conflicts 

This exercise reflects the scenario when other Intuit engineers have made changes to master, and you must rebase your changes on top of theirs.

You will learn how to rebase your changes on a feature branch on top of other engineers' changes in the master branch, assuming there are no merge conflicts. 

What is rebasing?
[Rebase integrates changes from one branch to another](https://www.git-tower.com/learn/git/glossary/rebase), in this case allowing the user to integrate the changes made by another engineer in the `master-student-name` branch to your feature branch. 

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

    <details>
    <summary>Commit Diagram</summary>

    The local repo, `my-fork` and `origin` all point to the the existing content in the repo.

    ```
    Our local repo/remote my-fork/remote origin:
    
    A---B master-your-name
    ```
    </details>
1. Create a feature branch on your local machine called `Scenario2`.
    <details>
    <summary>Solution</summary>
    
    ```console
    $ git checkout -b scenario2
    ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:
    
    A---B master-your-name, scenario2


    Remote my-fork:
    
    A---B master-your-name
    

    Remote origin:
    
    A---B master-your-name
    ```
    </details>
1. Perform your changes on the `scenario2` branch, specifically on the  `FileToModify.txt` in the `Scenario_2` folder. 
    <details>
    <summary>Solution</summary>
    
    1. Add a Line 3 to `FileToModify.txt`
        ```
        Line 1 
        Line 2
        Line 3 - Added by you 
        ```
    1. Stage and commit your changes 
        ```console
        $ git stage -A
        $ git commit -m "your message"
        ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:
    
      D scenario2
     /
    A---B master-your-name
    

    Remote my-fork:
    
    A---B master-your-name
    

    Remote origin:
    
    A---B master-your-name
    ```
    </details>
1. Go onto Github, open `master-student-name` branch in origin, go to `Scenario_2`, and create a new file called `NewFile.txt`. What is in this file is not important.  Normally, one does not edit files in this fashion.  We are doing this to simulate changes made by another engineer.

    <details>
    <summary>Solution</summary>

    1. On the "Code" page of your `master-student-name` branch in origin, click "Create new file".
    1. Name your file `NewFile.txt` and add some text.
    1. Click "Commit changes" 
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:
    
      D scenario2
     /
    A---B master-your-name
    

    Remote my-fork:
    
    A---B master-your-name
    

    Remote origin:
    
      C another-engineer
     /
    A---B master-your-name
    ```
    </details>
1. Rebase your changes on top of the new changes pulled from the remote `master-your-name`
    <details>
    <summary>Solution</summary>
    
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
    1. Check that your changes are on top of the changes imported from `master-your-name` with
        ```console
        $ git log
        ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:
    
    A---B---C---D master-your-name
    

    Remote my-fork:
    
    A---B master-your-name
    

    Remote origin:
    
      C another-engineer
     /
    A---B master-your-name
    ```
    </details>
1. Push changes to `my-fork`, and open a Pull Request (PR) to merge your changes with origin. 
    <details>
    <summary>Solution</summary>
    
    1. Push your changes to Github
        ```console
        $ git push
        ```
        <details>
        <summary>Commit Diagram</summary>

        Our local repo:
        ```
        A---B---C---D master-your-name
        

        Remote my-fork:
        
        A---B---C---D master-your-name
        

        Remote origin:
        
          C another-engineer
         /
        A---B master-your-name
        ```
        </details>
    1. Open a Pull Request on Githunb to merge changes from `my-fork` to `master-your-name` branch in origin. 
        <details>
        <summary>Commit Diagram</summary>

        ```
        our local repo/remote my-fork/remote origin:
        
        A---B---C---D master-your-name
        ```
        </details>
    1. If you run the `git log` command, `(HEAD -> master-your-name)` and `(origin/master-your-name, origin/HEAD)` should point to commit D, and `(my-fork/master)` should point to the last commit you pushed commit to `my-fork`.
    </details>
    
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
