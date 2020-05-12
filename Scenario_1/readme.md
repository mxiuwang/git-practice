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
1. Push changes from your current local `scenario1` branch to remote `my-fork`
    ```console
    $ git push -u my-fork scenario1
    ```
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

# End Result
Afterwards, `FileToModify.txt` should look like the following in origin/master:
```
Line 1 
Line 2
Line 3 - Added by you
```