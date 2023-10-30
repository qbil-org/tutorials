# Keywords
*These are my own definitions, may be biased*

**Repository**: A collection of code that is organized together in a meaninful way (e.g for a project, subcomponent, documentation, research paper implementation, etc.).

**Remote Repository**: A repository stored on a remote server that functions as a backup and is shared with all collaborators.

**Registry**: A container image library, essentially a "Repository" for container images where images and different versions of images are stored for later use. Example of registry services provided by a third-party is Docker Hub or GitHub Packages registry, etc. 

**Version Control System**: A piece of software that helps track changes to different version of a repository. This runs locally for each copy of the repository so that changes in a local repository will not be updated in another repository unless sync'ed

**Git**: A ***distributed*** version control system made by Linus Torvalds (guy who created linux). Distributed, in this sense, means that each server/computer has a complete copy/backup

**Commit**: a set of changes that updates the state of the repository

**Staging**: a conceptual area where changes can be stored prior to being committed

**Text Editor**: a software application that provides an interface to edit text, usually code in this context. Can literally be default notepad, but common editors are Vim, VSCode, Sublime, Atom, notepad++.

**Integrated Development Environment/IDE**: a software software that provides a text editor and additonal development tools, such as a debugger, build automation tools, etc.

**Debugger**: software tool that helps to test your code by running it in a controlled setting/conditions

**Linter**: static code analysis tool that helps to identify errors and bugs.

**IntelliSense**: linter + autocomplete.

**Container**: a lightweight encapsulation of a piece of software, usually a subcomponent/process of a larger software system. This includes all the OS, dependencies and everything else needed for the process to run. Containerization means the technology of encapsulating with the needed dependencies and binaries to run.

**Docker**: a containerization technology, the company that developed containerization.

**Image** (w.r.t containers): a "snapshot", including the binaries, libraries, etc. and active processes that the container runs. A container is "spun up" based on an image. An analogy for this is image is like a "class" and a container is like the "instantiation" of an image. 

**Volume** (w.r.t containers): method of storing persistent data that is linked to a container.

**DockerFile**: "recipe" for building an image from another base image (often times an OS image).

**Integration**: combining subcomponents of a system, e.g. this can be storage, cache, API, UI, etc. in a software system.

**Deployment**: Shipping/Delivering your application for the user to use, usually in reference to a release or updated version.

**Documentation**: Information about how your code works, colloquially called "docs"


# Acronyms:

**pkg**: package w.r.t. software, e.g. python package

**OS**: operating system

**VCS**: version control system

**YAML**: "Yet another markup language" is a language in which many configuration files are written in and is a human-readable.