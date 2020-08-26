# Visual Studio Code example - using docker containers for tensorflow python work

This is a simple example for how to use the Visual Studio Code Remote Containers extension for machine learning with tensorflow.

## Why this is interesting

The VS Code Remote Containers extension automates maintaining a docker container inside of which all the tools and libraries are installed (e.g. the python conda setup, Tensorflow, ...) and also the VS Code Extensions that need language support (in this case the VS Code Python and PyLance extensions for basic VS Code integrated notebook support with autocomplete and advanced type inference from PyLance).

The content of this folder is then mapped into the container using docker shared volumes so everything is persisted. You can also interact with VS Code and all other tools in this folder as you would both from inside the container and your host OS (e.g. use git, other file viewers, ...)

The Terminal in VS Code runs inside the container, so you can use all the executables etc inside the containers (this also means you always have the bash shell inside the container as this is what the container image provides, not e.g. Powershell if you host OS is windows).

The configuration for which image to use and which extensions to run inside the container is in this folder in .devcontainer/devcontainer.json. You can also reference a dockerfile and install additional stuff on the fly when the container is started.

More information is here: https://code.visualstudio.com/docs/remote/containers#_getting-started

## How to use this

1. Clone this repo to your local disk
2. Install [VS Code](https://code.visualstudio.com/) and the VS Code Remote Container Extension and Docker if you have not already done so (See details here: https://code.visualstudio.com/docs/remote/containers#_getting-started)
3. Open the cloned repo in Vs Code, run Ctrl/Cmd + Shift + P for the command palette and choose `Remote-Containers: Open Folder in Container...`
4. The first time you do this it will pull the docker image so it might take a while.
