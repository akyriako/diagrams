# Development Guide

> [!IMPORTANT] 
> The Development Guide for Diagrams for Open Telekom Cloud is taking a slightly different approach than the upstream repository to create
> a development environment (Dev Containers) but they both share roots to the same notion of using disposable docker containers as
> development environments and the Dockerfile of this project stems from the original but with a few enhancements.  

## Dev Container

Any IDE that supports [Dev Containers](https://code.visualstudio.com/docs/devcontainers/containers), but in this case everything is tailored for Visual Studio Code, will build a container with all the necessary prerequisites to get you started, based on the extensions and features defined in **devcontainer.json** and in the accompanying **Dockerfile**. A `python:3.11.9-alpine` container will be spawned with the following extras pre-installed:

### Visual Studio Code Extensions

- Python, Python Debugger
- Git Graph
- Resource Monitor
- GraphViz Diagrams Previewer

## Build & Publish changes to PyPi

Diagrams project is using [Poetry]() for Python environment isolation, package management and publishing. All the configuration defining the parameters and metadata of the project along with its build and packaging requirements can be found at `pyproject.toml`. 

### Build

In order to build the project you just have to execute the command:

```shell
poetry build
```

which will place the output files in `/dist`, already excluded in `.gitignore`

### Publish

Publishing requires setting up first the Poetry configuration with the your PyPi token:

```shell
poetry config pypi-token.pypi pypi-XXXXXXXXXXXXXXXXXXXX
```

and then publishing, is just a simple command:

```shell
poetry publish
```

## Docker Container

If you are not interested in using Dev Containers and you want to fallback to the setup of the upstream Diagrams, you can follow the documentation guide they provide:

[Documentation Guide](https://github.com/mingrammer/diagrams/blob/master/DEVELOPMENT.md)

> [!NOTE]
> The folder `docker/dev` is not needed by Diagrams for Open Telekom Cloud, but is left there to ensure the compatibility
> with the upstream in case of future syncs. It is **not** recommended to remove it.
