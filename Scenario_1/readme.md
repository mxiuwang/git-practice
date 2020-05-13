# Make changes in a feature branch and merge them to master

This exercise reflects the best-case scenario, where you (an engineer) pull code down from Git, make some changes in feature branch, and push them up to to Git, and merge with remote origin with no additional changes made by other engineers, and does not cause any merge conflicts. 

What is a feature branch?

[A feature branch is simply a separate branch in your Git repo used to implement a single feature in your project.](https://bocoup.com/blog/git-workflow-walkthrough-feature-branches)

# Instructions
1. On your local machine, create a new branch called `scenario1`.
    <details>
    <summary>Solution</summary>

    ```console
    $ git checkout -b scenario1
    ```
    </details>

    <details>
    <summary>Commit Diagram</summary>

    Each letter represents a commit. Currently, both `master-your-name` and `my-fork` is pointing at the same commit (the existing content in the repo).
    ```
    A---B master-your-name, my-fork
    ```
    </details>

1. In the `scenario1` branch, modify FileToModify.txt using a text editor of your choice so that it looks like the End Result outlined below. 
1. Stage changes (on your local machine)
    <details>
    <summary>Solution</summary>
    
    ```console 
    $ git stage -A
    ```
    </details>
1. Commit changes
    <details>
    <summary>Solution</summary>
    
    ```console 
    $ git commit -m "your message"
    ```
    </details>
    <details>
    <summary>Commit Diagram</summary>

    Local Repo: 
    
    Branch `scenario1` is pointing at your new commit, C.
    ```
      C scenario1
     /
    A---B master-your-name
    ```

    `my-fork`: 
    
    no changes have been made to remote `my-fork`
    ```
    A---B master-your-name
    ```

    `origin`: 
    
    no changes have been made to remote `origin`
    ```
    A---B master-your-name
    ```
    </details>
1. Push changes from your current local `scenario1` branch to remote `my-fork`
    <details>
    <summary>Solution</summary>
    
    ```console
    $ git push -u my-fork scenario1
    ```
    </details>
    <details>
    <summary>Commit Diagram</summary>

    Local Repo: 
    
    ```
      C scenario1
     /
    A---B master-your-name
    ```

    `my-fork`: 
    ```
      C scenario1
     /
    A---B master-your-name
    ```

    `origin`:
    ```
    A---B master-your-name
    ```
    </details>
1. Open a Pull Request (PR) on the Github website to merge your changes with origin. 
    <details>
    <summary>Solution</summary>
    
    1. Go to `your-fork` (where you pushed your changes) on the Github website. By deafult, this is located at [github.intuit.com/<your-name>/git-practice](github.intuit.com/<your-name>/git-practice).
    1. Click "New pull request" (besides "Branch: master-<your-name>"). Notice this action automatically takes you to the `git-practice` repo in Albertasaurus, as this is where you are trying to merge your code change to. 
    1. Scroll down to see all the file change(s) you have made. Once you have ensured the changes are correct, click the green "Create pull request" button. Add a descriptive title and description illustrating the nature of your code change if you wish. 
    1. Git will automatically run some tests ensuring that your code change is compatible with the existing code in `origin`. If checks fail, there are some issues you need to fix in your code before you're able to merge it. You can also ask reviewers, labels, or assign this task to someone else from the column on the right-hand side. 
    1. Once all checks have passed, you can click "Merge pull request", then "Confirm merge". You also can optionally include some comments describing the merged content. 
    1. You can go to the "code" tab in `Albertasaurus/git-practice`, go to the `master-your-name` branch, and see that your changes are merged.
    </details>

    <details>
    <summary>Commit Diagram</summary>

    Local Repo: 
    
    ```
      C scenario1
     /
    A---B master-your-name
    ```

    `my-fork`: 
    ```
      C scenario1
     /
    A---B master-your-name
    ```

    `origin`:

    After `my-fork` is merged with `master-your-name`, `master-your-name` will also point at your latest commit, C.
    ```
    A---B---C master-your-name
    ```
    </details>
1. Check that your changes are pushed and merged correctly
    <details>
    <summary>Solution</summary>

    ```console
    $ git log
    ```
    The [`git log`](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History) command shows the commit log, containing all the commits and merges by all authors in this project, in reverse chronological order. 

    `(HEAD -> master-your-name)` should be at the top, pointing to the latest commit you made on your local machine. Any other local commits that have not been pushed should be stacked underneath. 

    `(origin/master-your-name, origin/HEAD)` should point to the lastest commit you pushed into `origin`, or `master-your-name`, and any other commits you pushed into this repo should be stacked underneath.
    
   `(my-fork/master)` should point to the latest commit you pushed into `my-fork`, and any other commits you pushed into this repo should be stack underneath.

    </detail>

# End Result
Afterwards, `FileToModify.txt` should look like the following in both origin/master-your-name:
```
Line 1 
Line 2
Line 3 - Added by you
```