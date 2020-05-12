# git-practice
About this Repo:
This is a repository is a Git practice package with exercises designed to help you develop your Git skills, in the way it is most commonly used at Intuit! This repo is intended for any Intuit employee learning Git for the first time, or engineers wishing to familiarize themselves with the Git workflow at Intuit. 

The repository contains common scenarios that Intuit engineers may face. In general, scenarios are designed in ascending level of complexity. Each scenario contains a set of instructions, some StartCode an engineer will attempt to convert to the FinalCode, and the solution. 


Setup:
1. Clone "git-practice" repo on your local machine by copying the URL of the git-practice repo and typing `git clone https://github.intuit.com/Albertasaurus/git-practice` in your terminal, in the folder where you wish you clone it. The remote located at `https://github.intuit.com/Albertasaurus/git-practice` will be referred to as "origin".
1. Fork the above repo on your account by opening the repo on Github, and clicking the "fork" button on the top right-hand corner. Observe that the URL of this remote is `github.intuit.com/<your-name>/git-practice`. From now on, this fork will be referred to as `my-fork`. 
1. Configure my-fork as a remote in your local `git-practice` repo by typing `git remote add my-fork` in the terminal, opened in your local git-practice repo. This adds "my-fork" as an alias, pointing to the remote `github.intuit.com/<your-name>/git-practice`. You can verify this step is done correctly with the command `git remote -v`, and seeing that `my-fork` is an alias pointing to `github.intuit.com/<your-name>/git-practice`.
1. Create a new branch named `master-<your-name>` in your local repo by checking out the master branch, and typing the command `git checkout -b master-<your-name>`. We are doing this to pretend `master-<your-name>` is real master branch. Normally, we do not have to do this, but we don't want the changes made in these exercises to affect the real master. 
1. Push `master-<your-name>` to origin with the command `git push -u origin master-<your-name>`. 
1. Verify that the alias `origin` points to [https://github.intuit.com/Albertasaurus/git-practice](https://github.intuit.com/Albertasaurus/git-practice) and alias `my-fork` points to [github.intuit.com/<your-name>/git-practice](github.intuit.com/<your-name>/git-practice)

    ```console
    $ git remote -v
    ```

    Your output should look something similar to: 
    ```
    my-fork	https://github.intuit.com/mwang5/git-practice?organization=mwang5 (fetch)
    my-fork	https://github.intuit.com/mwang5/git-practice?organization=mwang5 (push)
    origin	git@github.intuit.com:Albertasaurus/git-practice.git (fetch)
    origin	git@github.intuit.com:Albertasaurus/git-practice.git (push)
    ```

For Each Scenario:
1. Create a new branch in your local repo named `scenario1`, `scenario`...and so on. Do the exercise in each secenario on the respective branch.
1. Do each exercise, save the changes you made, and push those changes to its remote counterpart in `my-fork`.
1. Open a Pull Request (PR) to merge those changes from `my-fork` to `master-your-name` in origin. 

Notes:
* origin: refers to the remote at [https://github.intuit.com/Albertasaurus/git-practice](https://github.intuit.com/Albertasaurus/git-practice)
* my-fork: refers to the remote at [https://github.intuit.com/<your-name>/git-practice](https://github.intuit.com/<your-name>/git-practice)
* Any changes made directly in Github are to simulate changes made by another Intuit engineer. Normally, you do not do this. 
