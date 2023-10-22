# Table of Contents
1. [Introduction](#introduction)
   * [What is Git?](#what-is-git)
   * [What is GitHub?](#what-is-github)
2. [Setting Up Git](#setting-up-git)
   * [Installation](#installation)
   * [Configuration](#configuration)
   * [GitHub Desktop](#Github-desktop)
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

# What is Git?

**TL;DR** Git is a software that can keep track of changes in code. This is very helpful if you want to work on a work on a long projects or work with others.

Anybody who writes code knows that it is hard. Over time, code gets messy, and features are added and deleted. It is exponentially more difficult once you work with others people, because now you have to keep track of all changes that other people made.

A workflow of code writing might be as follows:

1. You have a list of files where you write your code.
2. You want to add new features to code.
3. You changed the code in some of the files.
4. You tested and found some parts works and some parts didn't work.
5. You have to go back, but now you forgot which files you changed.
6. A collaborator made some changes to the code, 
7. Some parts of the code didn't work and you have to modify their code to fit your code.

Wouldn't it be nice if there was a way to keep track of which part has been changed, and by whom? This is the purpose of **Git**. Git is a type of software called **version control systems**. The name tells you everything: Git keep track of different version of the code.

Git do this by the following:
1. There is a central code base that every one contribute to. 
2. Each individual make a copy of the code base and edit it on their own.
3. Invidual submit the code for review. Approved code make it into the central code base
4. Git keep a log of all changes made by everyone. This means that one person can continue working on a copy of another person by simply asking Git what has changed.

A code project is called a **repository** by Git (**repo** for short). This guide will tell you the neccessary things you need to know to use Git with your colleagues. 

# What is Github?
Git is a software that track changes in your code. Each project is called a repository. **Github** is a company and a website that host repositories (A "hub of Git repo"). You can use Git to directly access repositories on Github. 

Normally, you use Git, the software, by using the command line. Github, the company, released a software called **GitHub Desktop**. This software helps you manage Git repositories using a GUI. In addition, this guide will teach you how to use Git using **Visual Studio Code** (VS Code for short). VS Code is a very popular code editor. It is fast, lightweight, and comes with powerful extension. 

# Additional Resources
Git has a lot of functionalities. If you want to be proficient, consider the following resources:
1. Github offical tutorial: https://docs.github.com/en/get-started/quickstart/hello-world 
2. Atlassian tutorial: https://www.atlassian.com/git/tutorials/what-is-version-control
3. ChatGPT: https://chat.openai.com/

