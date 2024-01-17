# Guide on Version Control Systems/Git and GitHub
Starting guide to version control systems, namely Git and integrations with a remote repository service like GitHub.

## Table of Contents
1. [Introduction](#introduction)
   * [Keywords and Definitions](#keywords-and-definitions)
   * [What is Git?](#what-is-git)
   * [What is GitHub?](#what-is-github)
2. [Setting Up](#setting-up)
   * [Installation](#installation)
   * [Configuration](#configuration)
3. [Basic Git Commands](#basic-git-commands)
   * [Initialization](#initialization)
   * [Cloning](#cloning)
   * [Adding Files](#adding-files)
   * [Committing Changes](#committing-changes)
   * [Pushing to Remote](#pushing-to-remote)
   * [Pulling from Remote](#pulling-from-remote)
4. [Branching in Git](#branching-in-git)
   * [Creating Branches](#creating-branches)
   * [Switching Branches](#switching-branches)
   * [Merging Branches](#merging-branches)
5. [Using GitHub](#using-github)
   * [Creating a Repository](#creating-a-repository)
   * [Forking a Repository](#forking-a-repository)
   * [Pull Requests](#pull-requests)
   * [GitHub Issues](#github-issues)
   * [GitHub Actions](#github-actions)
6. [Best Practices](#best-practices)
   * [Commit Messages](#commit-messages)
   * [Collaborative Workflow](#collaborative-workflow)
7. [Additional Resources](#additional-resources)
8. [Conclusion](#conclusion)

## Introduction

### Keywords and Definitions
[List of all Keywords and Acryonyms](keywords.md)

**TL;DR** 
1. Git is a software that can keep track of changes in code. This is very helpful if you want to work on a work on a long projects or work with others.
2. GitHub is a website that host Git projects.

### What is Git?
Anybody who writes code knows that it is hard. Over time, code gets messy, and features are added and deleted. It is exponentially more difficult once you work with others people, because now you have to keep track of all changes that other people made.



A workflow of code writing might be as follows:

1. You have a list of files where you write your code.
2. You want to add new features to code.
3. You changed the code in some of the files.
4. You tested and found some parts worked and some parts didn't work.
5. You have to go back, but now you forgot which files you changed.
6. A collaborator made some changes to the code.
7. Some parts of the code didn't work and you have to modify their code to fit your code.

Wouldn't it be nice if there was a way to keep track of which part has been changed, and by whom? **This is the purpose of "Git". Git is a type of software called "version control systems"**. The name tells you everything: Git keeps track of different version of your code.

Git does this by the following:
1. There is a central code base that everyone contributes to called a remote repository. 
2. Each individual makes a copy of the code base and edits it on their own.
3. Inviduals submit the code for review. Approved code make it into the central code base
4. Git keep a log of all changes made by everyone. This means that one person can continue working on a copy of another person's code by simply asking Git what has changed.

A code project is called a **repository** by Git (**repo** for short). 

### What is Github?
Git is a software that track changes in your code. Each project is called a repository. **Github** is a company and a website that host repositories (A "hub of Git repo"). You can use Git to directly access repositories on Github. 

Normally, you use Git, the software, by using the command line. Github, the company, released a software called **GitHub Desktop**. This software helps you manage Git repositories using a GUI. 

## Setting Up

### Installation

To follow through on this tutorial, you need to have three things:
1. Git installed on your computer
2. Visual Studio Code or other text editor installed on your computer. 
3. A GitHub account.

Check if you already have git installed on your computer and by running the command `git --version` in your terminal/command prompt. If you do not have it installed, you can install Git on your computer by following [the installation guide](https://github.com/git-guides/install-git). 

   *  **For Window specific users:** 

         Click through the installer and use the default settings except for when you get to the window below:

         ![git_installer1](images/git_install_default_branch.png)

         Then, select "Override the default branch name for new repositories". This will make sure your default branch is named "main" when initializing git in a new repository. Trust me that it will make your life easier as GitHub and others have moved to the default branch name of "main" instead of "master". 

      \
      Verify that you have installed it correctly by re-running the command above.
      ***Note: The installer for [Windows]](https://gitforwindows.org/) comes with git bash, which is a shell that is bash/Unix-like and is strongly recommend as your default shell as command prompt and PowerShell are bad.***

      
      * **Optional Step to have have git-bash work with Anaconda**:
      Find where the directory where you installed git-bash and edit the "bash.bashrc" file by adding the two lines below at the top of the file (after the comments):
         ```s
         . "/<full>/<path>/<to>/<Anaconda3>/etc/profile.d/conda.sh"
         alias python="winpty python.exe"
         ```

         Where `<full>/<path>/<to>/<Anaconda3>` is the path where Anaconda3 is installed. 

To install Visual Studio Code, go to [the official installation site](https://code.visualstudio.com/download) and follow the instructions. See [VS Code tutorial](vscode.md)/

To create a GitHub account, go to [GitHub.com](https://github.com/) and sign up for a new account.


### Configuration
Next you should edit your git configuration file to tell Git who you are. This is because every time you make changes to code, Git will keep track that "Person A make the following changes on this date." You do this by putting your name and your email with the following commands

```
git config --global user.name "Your Name"
git config --global user.email your_no_reply_email@users.noreply.github.com
```

Where your email should be the no reply email that you received from GitHub. You can view this under the "email" tab on the left side fo the personal settings page on GitHub. See [GitHub commit email setup](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address) for details.

## Basic Git Commands

### Initialization 
[`git init`](https://git-scm.com/docs/git-init)  creates an empty Git repository with a `.git` directory for tracking changes and history of repository, hooks, etc.

### Cloning
[`git clone <repository>`](https://git-scm.com/docs/git-clone) creates a copy of a `repository`, which is usually a remote repository hosted on GitHub or GitLab, into a new local directory. This copies all history and branches when coupled with a `git pull` after. Remote repository can be cloned over https, e.g. `https://github.com/<github_username>/<repository_name>`, or SSH, e.g `git@github.com:<github_username>/<repository_name>.git`. 

### Adding Files
[`git add`](https://git-scm.com/docs/git-add) allows you to add select files to the staging area. See the image below for the sections/areas of a Git project. The staging area allows you to select which files or changes you want to go into your next commit. In other words, you do not have to commit all your saved files that you have been editing and have more fine-grain control over what you want to update in the repository. 

![git-areas](https://git-scm.com/book/en/v2/images/areas.png)

* Note: you can use `-A` flag, e.g. `git add -A`, to add all new and modified files to the staging area. This is a common case where you want to commit all changes.

Adding files can also be done in some text editors that offer a GUI for version control tools such as git. 

### Committing Changes
[`git commit`](https://git-scm.com/docs/git-commit) updates the state of the repository with all the changes recorded in the staging area. This is different than the working directory if you stage only a few new or modified files *OR* if you added files to the staging area and then made some more edits that were saved but not added to the staging area. Each commit will be tagged with a description/message that you can use to detail changes; think of this as a sort of record-keeping/logging. 

* Note: you can use `-m` flag to commit with a message in the same line instead of opening a text editor to write a message each time, e.g. `git commit -m "This is a example of a commit message"`. 

Committing files can also be done in some text editors that offer a GUI for version control tools such as git. 

### Pushing to Remote
[`git push`](https://git-scm.com/docs/git-push) updated the remote repository to the state of the local repository. You may have already noticed that even though the state of your local repository has changed after you committed changes, the remote repository has not updated. To push this state change to the remote repostiory you use the `git push`.

### Pulling from Remote
[`git pull`](https://git-scm.com/docs/git-pull) updates your local repository to the state of the remote repository. **It is usually a good idea to pull before restarting your work on a project with multiple collaborators.** This is to avoid working on a stale version of the code if your collaborators made edits since the last time you worked on the project. Another option is to use a different branch to isolate your development from changes by others. 


## Branching in Git

### Creating Branches

### Switching Branches

### Merging Branches

## Using GitHub

### Creating a Repository

### Forking a Repository

### Pull Requests
### GitHub Issues
### GitHub Actions



Additional Info:
https://git-scm.com/docs/git#_git_commands

## Additional Resources
Git has a lot of functionalities. If you want to be proficient, consider the following resources:
1. Github offical tutorial: https://docs.github.com/en/get-started/quickstart/hello-world 
2. Atlassian tutorial: https://www.atlassian.com/git/tutorials/what-is-version-control
3. ChatGPT: https://chat.openai.com/
