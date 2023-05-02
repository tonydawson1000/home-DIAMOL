# DIAMOL Chapter 3
[Home](ReadMe.md)
## Chapter 3 - Building your own Docker images
---
## Description
---
Chapter 3 Workthrough.

Using `podman` not `docker`

## Web Ping
---
This simple container takes some optional environemnt variables and injects them into the container on startup.

Default values are supplied for these in the Containerfile.

A Node JS App runs that continually 'Pings' a Website and writes to a log.

- Run the following command

    `podman run -d --name web-ping quay.io/tonydawson1000/web-ping`

    ( `podman run -d --name web-ping diamol/ch03-web-ping` )

- View the Logs

    `podman logs web-ping`

- Stop the container

    `podman stop web-ping`

    NOTE : You can still view the LOGS for the STOPPED Container

- Source Code

    [https://github.com/tonydawson1000/home-DIAMOL/tree/main/Chapter-3/web-ping](https://github.com/tonydawson1000/home-DIAMOL/tree/main/Chapter-3/web-ping)

    ( [https://github.com/sixeyed/diamol/tree/master/ch03/exercises/web-ping](https://github.com/sixeyed/diamol/tree/master/ch03/exercises/web-ping) )

- Container in Quay.io / DockerHub

    [https://quay.io/repository/tonydawson1000/ch03-web-ping](https://quay.io/repository/tonydawson1000/ch03-web-ping)

    ( [https://hub.docker.com/r/diamol/ch03-web-ping](https://hub.docker.com/r/diamol/ch03-web-ping) )

## Inject Environment Variables on Container Startup
---

- Remove the old Container

    `podman rm web-ping`

- Start a new Container - passing in Env Vars

    `podman run -d --name web-ping --env TARGET=google.com --env INTERVAL=5000 quay.io/tonydawson1000/web-ping`