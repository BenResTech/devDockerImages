# devDockerImages

A repo for development Docker images

## Purpose

This repo contains Dockerfiles for the various Docker images I'm creating as part of development work.

The intent is to isolate dependencies for different work streams into Docker containers, allowing for a cleaner base environment and simplifying dependency interactions.

It is also a good way to make sure that there are no hidden dependencies that end up being satisfied by a dependency installed for a different project.

## Usage

The Dockerfiles in this repo can be built locally with:

```bash
cd [Dockerfile directory]
docker build . -t [image purpose]
```

This will then make the image available for use as `[image purpose]:latest` for a Docker run command.

The container can then be used to develop with by changing into the directory containing the source files you are interested in and then running the container with the local directory mounted inside it:

```bash
cd [source file directory]
docker container run -it -v $(pwd):/code [image purpose]:latest bash
```

This makes the source code files available inside the container environment at the `/code` directory.
