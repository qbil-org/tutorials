# QBIL/CISI Primer for New Lab Members
List of onboarding materials and resources for incoming lab membors for software development. 


# Table of Contents
1. [Introduction and Overview](#introduction)
    * [Keywords and Definitions](#keywords)
    * [Software Development Lifecycle and Agile](#software-development-lifecycle-and-agile)
2. [Continuous Integration/Continuous Deployment](#continuous-integrationcontinous-deployment)
    * [Do I need it?](#do-i-need-cicd)
3. [Integrated Development Environment and Text Editors](#idetext-editors)
4. [Version Control System](#version-control-system)
5. [Integration](#integration)
    * [Containerization](#containerization)
7. [Documentation and Best Practices](#documentation-and-best-practices)


# Introduction
### Keywords
[List of all Keywords and Acryonyms][keywords]

## Software Development Lifecycle and Agile
You might have heard of have never heard of the term software development lifecycle. If you haven't, count it to your benefit beacuse it can be summarized as separating the development of a software application into multiple phases to help improve the quality and reduce time and cost associated with development. A lot of this in my opinion is PR/marketing talk so I'm cutting it down to a few key highlights:

1. It is usually separated into 6 phases: 1. Defining/analyzing requirements, 2. System/architecture design, 3. Implementation, 4. Testing, 5. Deployment, 6. Maintenance*.
2. There are multiple types of "models" for this workflow/timeline of software development, e.g. Waterfall model
3. **"Test early, test often"** as it saves a lot of hours further down the road when you eventually realize your code does not function as you expected to because you forgot to test it. **You do not want to have to rewrite your entire code because of bad assumptions made from not testing it**
4. **"Agile"** arose to embody the concept of separating development of an application to multiple increments instead of developing the entire application sequentially and of iterating quickly. The idea is to do short "sprints" for shippable/deliverable features, getting feedback, and then iteratively refining§.
5. There are a lot of methods and tools, e.g. "Kanban Board", "Scrum", and "Sprints" employed to improve efficiency, but crux of the methodology is to **iterate quickly**. 

\* See waterflow method for more information on the 6 phases and what each means. \
§ A sprint can be imagined as a condensed development lifecycle. 

[Agile](https://agilemanifesto.org/)


All of this is key to understanding the need for a DevOps (**Dev**elopment and **Op**eration**s**). Which is frequently used to describe a pipeline for code development that utilizes some of the core concepts in Agile method and adds automation. Arises from the ability and need to iterate, test, and deploy continously.

# Continuous Integration/Continuous Deployment
Continuous Integration/Continuous Deployment stands or "CI/CD" for short refers to a developmental pipeline designed to take advantage of automation to iterate quickly on your software product/service.

### Do I need CI/CD?
A natural question that arises... The answer is usually ***NO***, surprisingly. You may use parts of it, e.g. a version control system such as git, but maybe you should not invest your time into developing a pipeline for a single experiment you are running in the lab. 

Do use it if you are:
* Developing an application, service, or pipeline that you intend others in the lab to use. 
* Working with multiple collaborators using different machines/configurations/etc. 

Additionally, you want to balance your present need of running experiments and with the future rewards of building a pipeline/automation that improves a workflow OR is something that can be built upon. 

## IDE/Text Editors
There are many text editors that you can use and each have their own advantages/disadvantages. Vim, atom, sublime, VScode and notepad++ are some of the popular text editors out there, but use whatever you are accustomed to or is easier for you. **Generally, if you have not had extensive experience with a particular text editor, we recommend VSCode because it is easy to pick up, become proficient, and scales with your growth well via its extensions/add-ons**. See [tutorial](vscode.md) on VS Code

## Version Control System
Needs no defintion apart from its name, VCS for short. We use **git** like everyone else, so please see [git tutorial page](version-control.md) for more details. The only additional thing to mention here is that keep in mind git is a distributed version control system, this means that commits that you make on a local copy of the repository on your device will not update the remote repository automatically. You have to push these commits to the remote repository via `git push` command. Similarly, you should have a habit of checking for updates prior to each time you start working on the repository again using the `git pull` command. You may want to develop on a separate branch.  

## Integration
There are a lot of continous integration tools such as GitHub Actions, GitLab CI/CD, CircleCI, Jenkins, etc. The usual workflow is: 

1) Changes are pushed to the remote repository
2) A Hook or Polling mechanism that senses a change to the repository triggers a CI pipeline to spin up VMs with configuration based on a YAML (Yet Another Markup Language) file.
3) Configured VMs builds the  "artifact", e.g. docker image, python package, C++ libraries, etc.
4) An automated testing suite is run, this usually includes unit and integration tests. 
5) If tests pass, the artifact is pushed to registry for later deployment. If tests fails, it notifies contributer.

GitLab CI and Github Actions are integrated with the remote repository service and would be easier to use for integration. 

### Containerization
Containerization describes a technology of encapsulating the environment in which a software, software subcomponent, or a process is meant to run in. Think of it as a wrapper or a... "container". They are used throughout the CI/CD pipeline, particularly for build, integration, and deployment. Details are in the [container tutorial](containers.md). 

# Documentation and Best Practices
**Document as much as reasonably possible for your future self and others**. Use single- and multi-line comments throughout your code. If you want to build a tool or API others may use, think about using something like Sphinx (Python projects) or Doxygen (C++ projects). 

## Best Practices
Some nice documents about different topics and best practices by google:
https://techdevguide.withgoogle.com/paths/principles/

[keywords]: keywords.md