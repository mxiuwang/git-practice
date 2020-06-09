# About this Repo
This is a repository is a Git practice package with exercises designed to help you develop your Git skills, in the way it is most commonly used at Intuit! This repo is intended for any Intuit employee learning Git for the first time, or engineers wishing to familiarize themselves with the Git workflow at Intuit. 

The repository contains common scenarios that Intuit engineers may face. In general, scenarios are designed in ascending level of complexity. Each scenario is contained within a folder, and within each folder is a `readme` detailling all the learning goals, instructions, and solutions to each exercise.

# Setup
Perform these instructions once before doing the exercises:
1. Clone "git-practice" repo on your local machine by copying the URL of the `Albertasaurus/git-practice` repo from the Github website. Specifically, copy the SSH URL from the "Clone or download" menu on the right right. 

    In your terminal, go to the folder you wish to clone this repo (we recommend in `/Users/<your-name>/dev`)
    ```console
    $ cd ~
    $ cd dev
    ```

    Use the following command to clone the repo:
    ```console
    $ git clone git@github.intuit.com:Albertasaurus/git-practice.git
    ```
    The remote located at `https://github.intuit.com/Albertasaurus/git-practice` will be referred to as "origin".
1. Fork the above repo on your account by opening the repo on Github, and clicking the "fork" button on the top right-hand corner. Observe that the URL of this remote is `github.intuit.com/<your-name>/git-practice`. 

    From now on, this fork will be referred to as `my-fork`. 
1. Configure my-fork as a remote in your local `git-practice` repo. 

    Add `my-fork` as a remote 
    ```console
    $ git remote add my-fork github.intuit.com/<your-name>/git-practice 
    ```
    This adds "my-fork" as an alias, pointing to the remote `github.intuit.com/<your-name>/git-practice`. 
1. Create a new branch named `master-<your-name>` in your local repo by creating and checking out a new master branch
    ```console
    $ git checkout -b master-<your-name>`
    ```
    We are doing this to pretend `master-<your-name>` is real master branch. Normally, we do not have to do this, but we don't want the changes made in these exercises to affect the real master. 
1. Push `master-<your-name>` to `my-fork`
    ```console
    $ git push -u my-fork master-<your-name>
    ```
1. Push `master-<your-name>` to `origin`
    ```console
    $ git push -u origin master-<your-name>
    ```
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

Diagram depicting the realtionship between `origin`, `my-fork`, and your local repositories.

![Git repo setup overview](img/overview_diagram.png)
<!-- (This is the link to edit the diagram: https://app.mural.co/invitation/mural/intuitqboteam/1589302194189?sender=michellewang8970&key=961f09bb-98be-471c-90e8-6d71e6a1dab1) -->
* origin: refers to the remote at [https://github.intuit.com/Albertasaurus/git-practice](https://github.intuit.com/Albertasaurus/git-practice)
* my-fork: refers to the remote at `https://github.intuit.com/<your-name>/git-practice`

# Conventions and Concepts 
## Forking
Our general workflow at Intuit includes forking off a copy of the original repository (`origin`) from Albertasaurus to our own account (`my-fork`). This is to ensure an additional check-and-balance before changes are introduced to production, and is also the most common way of making contributions to open-source projects. 

## Local and Remote Repositories 
A local repository is "folder" on your computer containing your code base, and only editable by you. A remote repository is your code base located on an online server (aka "remote").

At Intuit and on projects where there are multiple contributors, each author creates a local responsitory cloned from the remote repository. When any author changes or adds new code from their local repo, they can `push`, or "send" them to the remote repo on Github.

Click [here](https://www.intertech.com/Blog/introduction-to-git-concepts/) for more information.

## Branching 
A [git branch](https://www.atlassian.com/git/tutorials/using-branches) is a pointer to a specific commit you made in your `master` branch (or another branch). It represents an independent line of development (usually to develop a specific feature), where commits are independent from the master branch. It allows developers to work on seperate feature without interference, and to merge the code together later. 
<details>
<summary>Branching Diagram</summary>

```
     E feature1
    /
A---B---C---D master
         \
          F feature2 
```
</details>

## Terminal, Command line, or Git GUIs?
All instructions/solutions in this tutorial are Bash commands, available in Mac OS terminal. However, many of the same operations can be performed with different commands, on different operating systems, or with Git GUIs such as Tower or Sourcetree. 

What's important is that you are able to use your tool of choice to verify that your commit log matches the commit diagrams provided in each quesiton.
