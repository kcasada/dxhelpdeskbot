# README

## Pre-requisites

* NodeJS
* .NET Core
* Mono (macOS, Linux)
* .NET Framework (Windows)

## Building

To build the entire solution, you simply run the build script

### macOS / Linux:

```shell
$ ./build.sh
```

### Windows

```shell
c:> build.cmd
```

## Pushing Images

The Build will build a couple of Docker images, these needs to be pushed to the Hub.
You do need to change the name of the images to push them to your account.

### macOS / Linux

```shell
$ ./pushImages.sh
```

### Windows

```shell
c:> pushImages.cmd
```


## Deploying

For deploying the images as Pods and setting up the services for them, you simply run the following:

```shell
$ kubectl create -f k8_bot.yaml
```

> Due to a requirement on the Bot framework of TLS/SSL. At the moment, the configuration will not provide an endpoint that is accessible for registering in the Bot dashboard. You can however run it through the Bot Framework emulator without HTTPS.

### Azure Functions