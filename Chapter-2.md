# DIAMOL Chapter 2
[Home](ReadMe.md)
## Chapter 2 - Understanding Docker and running Hello World
---
## Description
---
Chapter 2 Workthrough.

Using `podman` not `docker`

## Hello DIAMOL
---
This simple container starts, prints out some info and then terminates.

- Run the following command

    `podman run diamol/ch02-hello-diamol`

- Source Code

    [https://github.com/sixeyed/diamol/tree/master/ch02/exercises/hello-diamol](https://github.com/sixeyed/diamol/tree/master/ch02/exercises/hello-diamol)

- Container in DockerHub

    [https://hub.docker.com/r/diamol/ch02-hello-diamol](https://hub.docker.com/r/diamol/ch02-hello-diamol)

## Interactive Terminal 
---
To start a container and connect to a terminal inside the running container.

- Run the following command

    `podman run -it diamol/base`

    - `-i` arg for 'interactive'
    - `-t` arg for 'tty / terminal'
    

- Source Code

    [https://github.com/sixeyed/diamol/tree/master/images/base](https://github.com/sixeyed/diamol/tree/master/images/base)

- Container in DockerHub

    [https://hub.docker.com/r/diamol/base](https://hub.docker.com/r/diamol/base)

## Long running container / Web Site 
---
To start a long running container in the background with some port exposed the following additional arguments are required.

This image is an Apache Web Server with a simple HTML page.

- Run the following command

    `podman run -d -p 8088:80 diamol/ch02-hello-diamol-web`

    - `-d` arg for 'detached'
    - `-p` arg for 'publish / open ports from/to the container'

- You can now access the website running inside the container at:

    [http://localhost:8088](http://localhost:8088)

- Source Code

    [https://github.com/sixeyed/diamol/tree/master/ch02/exercises/hello-diamol-web](https://github.com/sixeyed/diamol/tree/master/ch02/exercises/hello-diamol-web)

- Container in DockerHub

    [https://hub.docker.com/r/diamol/ch02-hello-diamol-web](https://hub.docker.com/r/diamol/ch02-hello-diamol-web)

---
## NOTE: This image (Dockerfile - `diamol/ch02-hello-diamol-web`) builds on top of another
---
    diamol/apache

- Source Code

    [https://github.com/sixeyed/diamol/tree/master/images/apache](https://github.com/sixeyed/diamol/tree/master/images/apache)

- Container in DockerHub

    [https://hub.docker.com/r/diamol/apache](https://hub.docker.com/r/diamol/apache)