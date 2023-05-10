# DIAMOL Chapter 4
[Home](ReadMe.md)
## Chapter 4 - Packaging applications from source code into Docker Images
---
## Description
---
Chapter 4 Workthrough.

Using `podman` not `docker`

## .NET Prereq's
---
Ensure that .NET is [installed](https://learn.microsoft.com/en-us/dotnet/core/install/)

For WSL (AlmaLinux)
    
    `sudo dnf install dotnet-sdk-7.0`

Confirm .Net SDK installed

    `dotnet --list-sdks`

Confirm .NET Runtime installed

    `dotnet --list-runtimes`

Create a New DotNet 7.0 Console App

    `dotnet new console -o MyConsoleApp -f net7.0`

Create a New DotNet 7.0 WebApi App

    `dotnet new webapi -o MyWebApiApp -f net7.0`

## Multi Stage Container file
---
Multi Stage Container files are used to keep the resulting image small and secure (i.e. the final image doesnt need the full SDK to run!)

Multi Stage Container files can be identifed by having more than one `FROM` statement

These demonstrate using the 'Full SDK' base image to build the app, then copy the resulting 'build artifacts' to the smaller 'Runtime Only' base image

These 2 simple projects create a `console` app and `WebApi` app

The [console](/home-DIAMOL/Chapter-4/console-app/MyConsoleApp/Program.cs) app starts, prints out some info and then terminates.

    `podman run quay.io/tonydawson1000/dotnet-console-app-70:latest`

The [WebApi](/home-DIAMOL/Chapter-4/webapi-app/MyWebApiApp/Program.cs) app starts a long running http webserver (WeatherForecast).

    `podman run -it -p 9999:8080 quay.io/tonydawson1000/dotnet-webapi-app-70:latest`

Point your browser to [http://localhost:9999/WeatherForecast](http://localhost:9999/WeatherForecast)