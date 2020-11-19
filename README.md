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

Each directory contains a Docker Compose file for deploying the image as a Docker Stack onto a Docker Swarm.

This allows automatic restarting of the container if it fails, and allows for things such as mounting in source file directories in a consistent way.
