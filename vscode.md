# Step-by-Step guide for Setting Up VS Code
This guide is meant to cover all the steps required to setup VS Code and incorporate it seamlessly in your workflow. This assumes you are coming in with little to no basic knowledge of coding.

## Table of Contents
1. [Introduction](#introduction)
    * [Keywords and Definitions](#keywords)
    * [What is Code?](#what-is-code)
    * [What is Visual Studio Code?](#what-is-visual-studio-code)
2. [Installing VS Code](#installing-vs-code)
    * [Add `code` shell command to PATH](#add-code-shell-command-to-path)
    * [Verifying your installation](#verifying-your-installation)
3. [Navigating VS Code](#navigating-vs-code)
    * [Git Integration](#git-integration)
    * [Opening a Terminal](#opening-a-terminal)
4. [Installing Extensions](#installing-extensions)
    * [Recommended Extensions](#recommended-extensions)
5. [Remoting with VS Code and SSH](#remoting-with-vs-code-and-ssh)
    * [Setup remote-ssh Config](#setup-remote-ssh-config) 
    * [SSH'ing into lab HPCs](#sshing-into-lab-hpcs)
6. [Additional Resources](#additional-resources)

## Introduction
### Keywords and Definitions
[List of all Keywords and Acryonyms](keywords.md)

### What is Code?
It seems like a silly questions, but those who have not had much experience coding might see it as something more fanciful than it actually is. ***Code is text***. It is text that tells the computer what to do, e.g. what operations to perform. If we think of it like this, code editors are just text editors and you can code in Notepad or TextEdit (This is the basic plain text editors that comes native with Windows or macOS). There are many languages that you can "code" in, e.g. Python, C++, and even markup languages such as html, markdown, etc. that essentially definees how to map text to computer instructions.

## What is Visual Studio Code?
How do you edit your code? When I first started learning to code, I used IDLE, which was the default coding editor that comes with my Python installation. It was easy to use, but did not help me much with writing good and fast code. Visual Studio Code (VSC for short) is a very popular code editor. In a survey on the coding website StackOverflow, VS Code became the overwhelming most popular coding tool -- and for a good reason. It is fast, lightweight, and comes with powerful plugins that are called "extensions". In fact, in some cases, you don't have to leave VS Code to run your code. If you download the neccessary extensions, you can write, debug, and run the code entirely within VS Code.

## Installing VS Code
____________________________________
To install Visual Studio Code, go to [the official installation site](https://code.visualstudio.com/download) and follow the instructions for your operating system.

Click through the installer and use the default settings, except for the menu below where you want to select "Add 'Open with Code' action to Windows Explorer file context menu" and "Add 'Open with Code' action to Windows Explorer directory context menu" as shown below,

![VSC-1](/images/vscode_install.png)

This will allow you an "Open with Code" options when you right click on any files and folder while in File Explorer.

### Add `code` shell command to PATH
If you are using a Windows machine, the shell command is already installed when you installed VS Code in the step above and you may skip this step comes with the Windows installation of VS Code. If you are using a linux or mac machine, open VS Code to setup this feature. After opening up VS Code, bring up the command palette menu by pressing `⌘+Shift+P` on mac or `Ctrl+Shift+P` on linux and search "shell command" (see image below). After selecting "Shell Command: Install 'code' command in PATH", VS Code will add the `code` shell command to your PATH, allowing you to open up vscode from your terminal using it. 

![VSC-2](/images/vscode_shell_cmd.png)


### Verifying your installation
Navigate to your prefered terminal (you should have Windows Powershell pre-installed for Windows and terminal on macOS), a window with a dark background and text should pop up. Then type `code` into the window. This is the default command to run Visual Studio Code from your terminal and is very convenient to open a directory after navigating to it via your terminal. A new window should pop up which looks like the image below:

![VSC-3](/images/vscode_open.png)





## Navigating VS Code
This section covers navigating VS Code briefly and a few useful keyboard shortcuts.

### Git integration
VS Code comes with git integration pre-installed and you can open it using by clicking the third icon from the top on the left vertical sidebar/menu. It lists changed files into 2 categories, "Changes" and "Staged Changes", you can add or remove these changes to staged changes by clicking the "+" or "-" symbols on the side of each file. You can access more git commands, e.g. `git pull`, `git push`, etc. via the UI in VS Code by click the ellipsis (...) symbol on the menu labeled "SOURCE CONTROL".


### Opening a Terminal
____________________________________

Navigate to the Menu bar, and select **View** -> **Terminal**. Alternatively, you can use the shortcut **Ctrl+\`**. 

![VSC-4](/images/vscode_terminal.png)

A panel should open up at the bottom of your VS Code window similar to below:

![VSC-5](/images/vscode_terminal_2.png)

Now you can operate with terminal as usual, try running a command, e.g. `git pull`

## Installing Extensions
Navigate to the Extension tab on the left of your Visual Studio Screen. Alternatively, use the shortcuts **`Ctrl+Shift+X`** on Windows or **`⌘+Shift+X`** on Mac. Install any of the below recommended extensions that you plan on using in your workflow. Download Remote-SSH extensions for the next part of this tutorial.

### Recommended Extensions
____________________________________
* IntelliSense, linting, and debugger tools for C++, Python or whatever your preferred language is. Just search name of language in extensions
* Jupyter
* Remote-SSH and Remote-SSH: Editing Configuration Files
* Docker
* LiveShare


## Remoting with VS Code and SSH


### Setup remote-ssh Config
____________________________________

### SSH'ing into lab HPCs
____________________________________

## Additional Resources