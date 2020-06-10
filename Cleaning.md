# Cleaning 
At the beginning of each scenario other than scenario 1, please follow these steps to reset your local repo so we start from a "clean state". 

*Note*: You DO NOT need to do this during setup the first time. You only need to do this at the beginning of `scenario 2` and onwards. 

**Warning**: This is a destructive operation that will reset any work in progress. Please ensure you are ready to move on from the previous exercise. 

1. Check out your local `master-<your-name>` branch
    ```console
    $ git checkout master-your-name
    ```
1. Check if there are any uncommitted changes with the command:
    ```console
    $ git status 
    ```
    If there are, continue to the next step. If there aren't, you can skip the remaining steps. 
1. Delete any unstaged files and directories 
    ```console
    $ git clean -f -d 
    ```
1. Refresh pointers and references from your remote `origin` repository 
    ```console
    $ git fetch origin
    ```
1. Reset your local `master-<your-name>` branch to the same state as the `master-<your-name>` branch in `origin`.
    ```console
    $ git reset --hard origin/master-your-name
    ```


# Commit Diagram

After cleaning, our `local` and `origin` repos should both point to the same commit. Use `git log` to verify that `local/master-your-name` and `origin/master-your-name` point to the same commit, as in the following diagram: 

```
Our local repo:

A---B master-your-name


Remote my-fork:

<nothing relevent to show>


Remote origin:

A---B master-your-name
```

Recall: Use the command `git log origin/<branch-name>` if the branch you want does not appear with `git log`. 

Please use `git log` to verify the commit logs with the commit diagram in each step. 