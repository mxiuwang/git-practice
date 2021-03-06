# Rebase on Feature Branch with Merge Conflicts 

This exercise reflects the scenario when you rebase your changes on top of changes made by other engineers on your feature branch, but there is a merge conflict you must resolve. 

You will first attempt to rebase your changes made on feature branch on top of other engineers' changes in the same branch, and manually resolve any merge conflicts. Then, push the feature branch to remote. 

# New Git commands in this section
No new commands 

# Instructions
1. [Reset your repo](https://github.com/mxiuwang/git-practice/blob/master/Cleaning.md) to a clean state
1. Create a feature branch on your local machine called `scenario4`
    <details>
    <summary>Solution</summary>
    
    ```console
    $ git checkout -b scenario4
    ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:
        
          C scenario4
         /
    A---B master-your-name


    Remote my-fork:
    
    <nothing relevent to show>
    

    Remote origin:
    
    A---B master-your-name
    ```
    </details>
1. Perform your FIRST set of changes on the `scenario4` branch, specifically on the `FileToModify.txt` on your local machine.
    <details>
    <summary>Solution</summary>

    Open `FileToModify.txt` in the `Scenario_4` folder, and add in a line so that your `FileToModify.txt` should look something like:
    ```
    Line 1
    Line 2
    Line 3A - Added by you
    ```
    </details>
1. Stage, commit, push, and PR your changes from your local machine to `origin`, so that your changes are available to "all developers". 
    <details>
    <summary>Solution</summary>

    Stage and commit, and push your changes to `my-fork`
    ```console
    $ git stage -A
    $ git commit -m "change #1"
    $ git push -u my-fork scenario4
    ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:

          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote my-fork:
    
          C scenario4 (change #1)
         /
    A---B master-your-name
    

    Remote origin:
    
    A---B master-your-name
    ```
    </details>

1. Simulate changes made by another engineer **on your feature branch** (the one you just pushed).
    <details>
    <summary>Solution</summary>

    1. Go to the `my-fork` repo on Github, choose the `scenario4` branch from the "Branch" dropdown, and open `FileToModify.txt` in the `Scenario_4` folder. 
    1. Add another line to `FileToModify.txt` so that your file now looks like:
        ```
        Line 1
        Line 2
        Line 3 - Added by you (change #1)
        Line 4A - Another engineer 
        ```
    1. Include the commit message "Another engineer", and click "Commit changes"
    </details>

1. Fetch the latest references from Github
    <details>
    <summary>Solution</summary>

    ```console
    $ git fetch my-fork 
    ```
    </details>

    <details>
    <summary>Commit Diagram</summary>
    
    ```
    Our local repo:

          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote my-fork:
    
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote origin:
    
    A---B master-your-name
    ```
    </details>

1. In the `scenario4` branch on your local repository, perform and commit your SECOND set of changes on the `FileToModify.txt`. 

    This simulates your ongoing work, despite your colleague making changes to your code elsewhere. 

    <details>
    <summary>Solution</summary>

    1. On your local machine, open `FileToModify.txt` in the `Scenario_4` folder of your `scenario4` branch, and add in a line so that your `FileToModify.txt` looks like:
        ```
        Line 1
        Line 2
        Line 3 - Added by you (change #1)
        Line 4B - Also added by you (change #2)
        ```
    1. Stage and commit your changes
        ```console
        $ git stage -A
        $ git commit -m "change #2"
        ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:

            E scenario4 (change #2)
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote my-fork:
    
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote origin:
    
    A---B master-your-name
    ```
    </details>

1. Rebase your changes on top of the new changes pulled from the remote `scenario4` branch in the `origin` repo. Resolve any merge conflicts. 
    <details>
    <summary>Solution</summary>

    1. Try to rebase your changes on top of the new changes made by another engineer in `my-fork/scenario4`. A merge conflict should appear.
        ```console
        $ git rebase my-fork/scenario4
        ```
    1. Resolve the merge conflict(s)
        
        For more details on how this is done, refer to Step 6 in [Scenario 3](https://github.com/mxiuwang/git-practice/tree/master/Scenario_3/#Instructions).

        Your final FileToModify.txt should look like this:
        ```
        Line 1
        Line 2
        Line 3 - Added by you (change #1)
        Line 4A - Another engineer 
        Line 4B - Also added by you (change #2)
        ```
    1. Add your changes, and continue the rebase.
        ```console
        $ git add -A 
        $ git rebase --continue
        ```
    </details>

    <details>
    <summary>Commit Diagram</summary>
    
    Recall, `E'` represents the same change as `E`, but with a different commit hash after the rebase.
    ```
    Our local repo:

              E' scenario4 (change #2)
             /
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote my-fork:
    
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote origin:
    
    A---B master-your-name
    ```
    </details>

1. Push changes to `my-fork/scenario4`
    <details>
    <summary>Solution</summary>
    
    ```console
    $ git push -u my-fork scenario4
    ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    ```
    Our local repo:

              E' scenario4 (change #2)
             /
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote my-fork:
    
              E' scenario4 (change #2)
             /
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote origin:
    
    A---B master-your-name
    ```
    </details>

1. Open a Pull Request (PR) on Github to merge changes from `my-fork/scenario4` to `origin/master-<your-name>`.
    <details>
    <summary>Solution</summary>

    1. Open a Pull Request on Githunb to merge changes from `my-fork/scenario4` to `origin/master-<your-name>`. 
    1. Run `git fetch origin` to refresh your local repo's pointers  
    </details>

    <details>
    <summary>Commit Diagram</summary>

    Recall, `E''` represents a big commit containing all the previous commits the squashed together (`C`, `D`, `E`). It has a different commit hash than `E` and `E'`. 
    ```
    Our local repo:

              E' scenario4 (change #2)
             /
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote my-fork:
    
              E' scenario4 (change #2)
             /
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name


    Remote origin:

                E'' All changes (commits C, D, and E')
               /
              E' scenario4 (change #2)
             /
            D Another engineer 
           /
          C scenario4 (change #1)
         /
    A---B master-your-name
    ```
    </details>

# End Result
Afterwards, `FileToModify.txt` should look like the following in `origin/master-<your-name>`:
```
Line 1
Line 2
Line 3 - Added by you (change #1)
Line 4A - Another engineer 
Line 4B - Also added by you (change #2)
```
