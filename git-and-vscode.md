# Table of Contents
1. [Introduction](#introduction)
   * [What is Git?](#what-is-git)
   * [What is GitHub?](#what-is-github)
   * [What is Visual Studio Code?](#what-is-visual-studio-code)
2. [Setting Up](#setting-up-git)
   * [Installation](#installation)
   * [Setup](#git-setup)
   * [Extensions](#extensions)
3. [Basic Git Commands](#basic-git-commands)
   * [Initialization](#initialization)
   * [Cloning](#cloning)
   * [Adding Files](#adding-files)
   * [Committing Changes](#committing-changes)
   * [Pushing to Remote](#pushing-to-remote)
   * [Pulling from Remote](#pulling-from-remote)
4. [Branching in Git](#branching-in-git)
   * [Creating Branches](#creating-branch)
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

# Introduction

**TL;DR** 
1. Git is a software that can keep track of changes in code. This is very helpful if you want to work on a work on a long projects or work with others.
2. GitHub is a website that host Git projects.
3. Visual Studio Code is a code editor that has Git integrated.

## What is Git?

Anybody who writes code knows that it is hard. Over time, code gets messy, and features are added and deleted. It is exponentially more difficult once you work with others people, because now you have to keep track of all changes that other people made.

A workflow of code writing might be as follows:

1. You have a list of files where you write your code.
2. You want to add new features to code.
3. You changed the code in some of the files.
4. You tested and found some parts worked and some parts didn't work.
5. You have to go back, but now you forgot which files you changed.
6. A collaborator made some changes to the code.
7. Some parts of the code didn't work and you have to modify their code to fit your code.

Wouldn't it be nice if there was a way to keep track of which part has been changed, and by whom? This is the purpose of **Git**. Git is a type of software called **version control systems**. The name tells you everything: Git keeps track of different version of the code.

Git does this by the following:
1. There is a central code base that everyone contributes to. 
2. Each individual makes a copy of the code base and edits it on their own.
3. Inviduals submit the code for review. Approved code make it into the central code base
4. Git keep a log of all changes made by everyone. This means that one person can continue working on a copy of another person's code by simply asking Git what has changed.

A code project is called a **repository** by Git (**repo** for short). 

## What is Github?
Git is a software that track changes in your code. Each project is called a repository. **Github** is a company and a website that host repositories (A "hub of Git repo"). You can use Git to directly access repositories on Github. 

Normally, you use Git, the software, by using the command line. Github, the company, released a software called **GitHub Desktop**. This software helps you manage Git repositories using a GUI. 

## What is Visual Studio Code?
How do you edit your code? When I first started learning to code, I used IDLE, which was the default coding editor that comes with my Python installation. It was easy to use, but did not help me much with writing good and fast code. Visual Studio Code (VSC for short) is a very popular code editor. In a survey on the coding website StackOverflow, VS Code became the overwhelming most popular coding tool -- and for a good reason. It is fast, lightweight, and comes with powerful plugins that are called "extensions". In fact, in some cases, you don't have to leave VS Code to run your code. If you download the neccessary extensions, you can write, debug, and run the code entirely within VS Code.

VS Code comes with Git already pre-installed, so you can use Git with VS Code immediately. This guide will tell you the neccessary things you need to know to use Git on VS Code to collaborate with your colleagues and speed up your code development. 

# Setting Up

## Installation

To follow through on this tutorial, you need to have three things:
1. Git installed on your computer
2. Visual Studio Code installed on your computer 
3. A GitHub account.

You can install Git on your computer as a separate program by following [the installation guide](https://github.com/git-guides/install-git).

To install Visual Studio Code, go to [the official installation site](https://code.visualstudio.com/download) and follows instruction.

To create a GitHub account, go to [GitHub.com](https://github.com/) and sign up for a new account.

## Setup

Visual Studio Code should have Git already installed. To check if your installation is correct, open up Visual Studio Code. I usually open it by opening up Windows PowerShell (you should have it installed if you use Windows) and then type

```
code
```

This is the default command to run Visual Studio Code. Upon startup, this is what the program looks like: 

![VSC-1](/images/vsc-open.png)

To check if **git** is installed properly, you can try using the built-in **Terminal**. Navigate to the Menu bar, and select **View** -> **Terminal**. Alternatively, you can use the shortcut **Ctrl+\`** on Windows or **⌘ +\`** on Mac. 

![VSC-2](/images/vsc-terminal.png)
![VSC-3](/images/vsc-terminal-2.png)

Type into the Terminal 

```
git
```

You should get the following responses

```
usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--super-prefix=<path>] [--config-env=<name>=<envvar>]
           <command> [<args>]
```

The first thing you should do is tell Git who you are. This is because every time you make changes to code, Git will keep track that "Person A make the following changes on this date." You do this by putting your name and your email with the following commands

```
git config --global user.name "Your Name"
git config --global user.email youremail@email.com
```

## Extensions

All the extensions that we use in this tutorial (Git and Github) should be pre-installed with Visual Studio. Still, you should be familiar with extensions, because they are very powerful and can help you with your coding project. 

Navigate to the Extension tab on the left of your Visual Studio Screen. Alternatively, use the shortcuts **Ctrl+Shift+X** on Windows or **⌘+Shift+X** on Mac.

# Additional Resources
Git has a lot of functionalities. If you want to be proficient, consider the following resources:
1. Github offical tutorial: https://docs.github.com/en/get-started/quickstart/hello-world 
2. Atlassian tutorial: https://www.atlassian.com/git/tutorials/what-is-version-control
3. ChatGPT: https://chat.openai.com/
