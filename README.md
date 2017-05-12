Alpine Gradle Docker image
==========================

This image is based on Alpine Java (openJDK) image ([cosmomill/alpine-openjdk](https://hub.docker.com/r/cosmomill/alpine-openjdk/)), which is only a 75MB image, and contains Gradle.

Usage Example
-------------

This image is intended to be a base image for your projects, so you may use it like this:

```Dockerfile
FROM cosmomill/alpine-gradle

COPY ./my_app /usr/local/bin/my_app
```

```sh
$ docker build -t my_app .
```

To build a Gradle project run this from the directory of the Gradle project you want to build.

```sh
$ docker run --rm -v "$PWD":/project -w /project --name gradle gradle:latest gradle <gradle-task>
```
