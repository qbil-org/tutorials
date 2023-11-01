# Guide to Docker/Containerization
Starting guide to using docker and containers with a brief introduction, compilation of useful docker commands, and links to useful reference material. Best way to go through this guide is to read the introduction and go through the docker tutorial (see table of contents) first. You can then reference specific commands and other parts to this guide. There are many more docker commands that you can reference from [Docker's CLI documentation](https://docs.docker.com/engine/reference/commandline/docker/)

## Table of Contents
1. [Introduction](#introduction)
    * [Keywords and Definitions](#keywords-and-definitions)
    * [What Even is Docker?](#what-even-is-docker)
    * [Why Does it Even Matter?](#why-does-it-even-matter)
2. [Running a Container](#running-a-container)
    * [`docker run`](#docker-run)
        * [`docker run` Options](#docker-run-options)
3. [Accessing a Container](#accessing-a-container)
    * [`docker exec`](#docker-exec)
4. [Managing Docker Images](#managing-docker-images)
    * [`docker pull`](#docker-pull)
    * [`docker push`](#docker-push)
    * [`docker image`](#docker-image)
5. [DockerFiles and building Images](#dockerfiles-and-building-images)
    * [`docker build`](#docker-build)
6. [Managing Containers](#managing-containers)
    * [`docker start`](#docker-start)
    * [`docker stop`](#docker-stop)
    * [`docker kill`](#docker-kill)
    * [`docker rm`](#docker-rm)
    * [`docker ps`](#docker-ps)
    * [Working with Multiple Containers](#working-with-multiple-containers)
        * [Docker-compose](#docker-compose)
        * [Container Orchestration](#container-orchestration)
7. [Tutorial](#example-tutorial)
    * [More Resources](#more-resources)

## Introduction
This file is to biefly catch you up to speed on containerization technology and Docker. 

### Keywords and Definitions
[List of all Keywords and Acryonyms](keywords.md)

### What Even is Docker?
Docker is a software company whose name has become synonymous with the containerization technology they developed/pioneered. This technology is a method of encapsulating the environment in which a software, software subcomponent or a process is meant to run in. Think of it as a wrapper or a... "container", if you will, around the process that includes the dependencies it needs to run so that if it runs in one device it runs on other devices. ***No more compatability issues that arise from different Operating System, package versions, etc.***

## Why Does it Even Matter?
Astra and Apollo HPCs in the lab run in a Docker container and is meant to have all your software, packages, custom code for experiements, etc. isolated from other's as the HPCs are a shared resource. To be able to use these HPC's appropriately and effectively, learning the technology it uses is important, because:

1. It isolates your packages/dependencies/libraries from other users where versioning and multiple PATH locations can cause issues.
2. It can be used to isolate your own experiments from each other. 
3. You can manage and troubleshoot your software/experiements
4. You are better able to reproduce and share your work 

***The first two reasons are important and is substituted with Anaconda in Titan2 and some of the other HPCs but are the most important. Please do not install things directly onto the system as this will affect other users and can conflict with the drivers, libraries, packages, code they use.***

## Running a container
### `docker run`

`docker run <image>:<tag>` is basic docker run command which "spins up" (creates) a new container based on the image you specify `<image:tag>` tells docker to create a new container based of this `<image>`. Tags are different versions of the same image, e.g. `latest` or `1.0.0`; if the tag is not specified, it will docker will look for `<image>:latest`. Options or flags can be also used to customize container settings to your preferences. Below are some of the options that might be useful to you.


#### `docker run` Options
`--gpus 'all,"capabilities=compute,utility,graphics,display"'` tells docker to use all gpus (can specify which one with "devices") and what driver capabilities in `"capabilities=compute,utility,graphics"`

`-it` runs container interactively. Behavior of this command is that you connect to container and start running a terminal within the container. Alternatively, can run with `-d` flag to run in detached mode.

`--rm` tells docker to remove container and everything in it after terminating the process. Volumes that are mounted still persist.

`--shm-size=16g` is specifiying shared memory size, default is small (64mb or something)

`--ulimit memlock=-1` memory allowed to container as specified under `ulimit` (user limit) flag. -1 is max

`-v <local_directory>:<container_directory>` tells docker to mount volume located at <local_directory> (path in system's filesystem) to <container_directory> (path to container's filesystem)

`-e <variable_name>=<value>` tells docker to set enviroment variable `variable_name` to value. If no value `=<value>` the value is defaulted to current shell session's environment variable's value. 

`--name=<name>` tells docker to name container `<name>` otherwise a random string name with be given to docker container, note: name is distinct from container id


Example:
```s
[jamesyu@astra ~]$ sudo docker run --gpus 'all,"capabilities=compute,utility,graphics,display"' -it --shm-size=16g --ulimit memlock=-1 -v /home/jamesyu/Desktop/project1:/workspace -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY --name=neuralangelo chenhsuanlin/neuralangelo:23.04-py3
```

See also:
[Docker reference](https://docs.docker.com/reference/), [NVIDIA containers](https://catalog.ngc.nvidia.com/containers)

## Accessing a Container
### `docker exec`
This command usually comes in the form `docker exec -it <container_name/id> <command>` and is used to run a command in the container names `<container_name>`, e.g. create a file, start/stop a process, access the terminal via the `-it` option. Container ID can be used in place of container's name

**Examples:**
```s
docker exec -it <container_name/id> bin/bash
```
***I probably use this the most to access the container and then run whatever I need from a bash terminal inside the container***

`-it` stands for "interactive" and `-d` for "detached", similar to above


```s
docker exec -d mycontainer touch /test/example.txt
```

`touch <file_name>` is a linux command to create a new blank file at /test/example.txt

## Managing Docker Images
### `docker pull`

Command to download image from registry (a type of repository for container images), e.g. [DockerHub](https://hub.docker.com/search?q=). In the formate `docker pull <image>:<tag>`

Example:
```
docker pull nvcr.io/nvidia/pytorch:23.10-py3
```

### `docker push`
Command to push an image to a registry with a container name and tag. 

### `docker image`
Collection of docker commands to manage images, e.g list images stored locally with `docker image ls`. You can include option flags like `-a` similar to `ls` linux command. 

Another common command is `docker image rm <image_name>`, which removes a image named `<image_name>`


## DockerFiles and building Images
WIP

### `docker build`
WIP

# Managing Containers
### `docker start`
`docker start <container_name/id>` starts one or more stopped containers

### `docker stop`
`docker stop <container_name/id>` stops one or more active containers safely

### `docker kill`
`docker kill <container_name/id>` kills one or more containers, halts all processes running the container and spins it down. This is usually used when container hangs and unable to use `docker stop` to stop a container safely

### `docker rm`
`docker rm <container_name/id>` deletes the referenced container and unnamed volumes it is connected. 

### `docker ps`
`docker ps` shows currently running containers in a table format, usually telling you the id, name, and status, e.g. starting up or how long its been up. Use `-a` option to also stopped containers as the default behaviour just shows the running containers.

### Working with Multiple Containers
You can encapsulate different subcomponents of an application in separate containers, e.g cache, storage, UI frontend, API, etc., to use containerization technology to your advantage. For example, each subcomponent can be in different programming languages or be running different versions of a package. Containers make share networks and volumes between services as needed and communicate via ports similar to network of computers. 

#### Docker Compose
Docker feature to manage multi-container applications. Uses a YAML file to define container configuration settings

See [docker compose tutorial](https://docs.docker.com/compose/gettingstarted/) for more information, but this is also somewhat beyond the scope of what is covered here.

#### Container Orchestration
There are also container orchestration technologies for automating the deployment, management, and scaling of multiple containers applications, the most popular of which is Google's [Kubernetes](https://kubernetes.io/docs/home/). E.g. spins up more containers of a specific resources (called pods) if needed, swaps them out when pushing an update, etc. This goes beyond what is covered here but more information can be found at the end under "More Resources"

## Example Tutorial
Parts 1-6 of a tutorial maintained by Docker is highly recommended to become more familar with using docker: https://docs.docker.com/get-started/

### More Resources

* https://docs.docker.com/reference/
* https://docs.docker.com/engine/reference/commandline/cli/
* https://hub.docker.com/search?q=
* https://docs.docker.com/compose/gettingstarted/
* https://kubernetes.io/docs/home/
