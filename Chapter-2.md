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

    `podman run quay.io/tonydawson1000/ch02-hello:latest`

    ( `podman run diamol/ch02-hello-diamol` )

- Source Code

    [https://github.com/tonydawson1000/home-DIAMOL/tree/main/Chapter-2/hello](https://github.com/tonydawson1000/home-DIAMOL/tree/main/Chapter-2/hello)

    ( [https://github.com/sixeyed/diamol/tree/master/ch02/exercises/hello-diamol](https://github.com/sixeyed/diamol/tree/master/ch02/exercises/hello-diamol) )

- Container in Quay.io / DockerHub

    [https://quay.io/repository/tonydawson1000/ch02-hello](https://quay.io/repository/tonydawson1000/ch02-hello)

    ( [https://hub.docker.com/r/diamol/ch02-hello-diamol](https://hub.docker.com/r/diamol/ch02-hello-diamol) )

## Interactive Terminal 
---
To start a container and connect to a terminal inside the running container.

- Run the following command

    `podman run -it quay.io/tonydawson1000/ubi9-base`

    ( `podman run -it diamol/base` )

    - `-i` arg for 'interactive'
    - `-t` arg for 'tty / terminal'

- Source Code

    [https://github.com/tonydawson1000/home-DIAMOL/tree/main/images/base](https://github.com/tonydawson1000/home-DIAMOL/tree/main/images/base)

    ( [https://github.com/sixeyed/diamol/tree/master/images/base](https://github.com/sixeyed/diamol/tree/master/images/base) )

- Container in Quay.io / DockerHub

    [https://quay.io/repository/tonydawson1000/ubi9-base](https://quay.io/repository/tonydawson1000/ubi9-base)

    ( [https://hub.docker.com/r/diamol/base](https://hub.docker.com/r/diamol/base) )

## Long running container / Web Site 
---
To start a long running container in the background with some port exposed the following additional arguments are required.

This image is an Apache Web Server with a simple HTML page.

- Run the following command

    `podman run -d -p 8088:80 quay.io/tonydawson1000/ch02-hello-web`

    ( `podman run -d -p 8089:80 diamol/ch02-hello-diamol-web` )

    - `-d` arg for 'detached'
    - `-p` arg for 'publish / open ports from/to the container'

- You can now access the website running inside the container at:

    `http://<ip>:8088`

    - Using Podman in WSL? - Find the IP of your WSL Env...

        `ip a | grep 172`

- Source Code

    [https://github.com/tonydawson1000/home-DIAMOL/tree/main/Chapter-2/hello-web](https://github.com/tonydawson1000/home-DIAMOL/tree/main/Chapter-2/hello-web)

    ( [https://github.com/sixeyed/diamol/tree/master/ch02/exercises/hello-diamol-web](https://github.com/sixeyed/diamol/tree/master/ch02/exercises/hello-diamol-web) )

- Container in Quay.io / DockerHub

    [https://quay.io/repository/tonydawson1000/ch02-hello-web](https://quay.io/repository/tonydawson1000/ch02-hello-web)

    ( [https://hub.docker.com/r/diamol/ch02-hello-diamol-web](https://hub.docker.com/r/diamol/ch02-hello-diamol-web) )