# Imacry

**WARNING: these instructions work best on a unix based system**

## **THIS WAS MADE FOR EDUCATIONAL PURPOSES**

*Technically* this isnt a ransomware bot. There is no ransom to be payed.
This does mimic a ransomware bot in the fact it encrypts all the files, talks to a server, and then decrypts all the files. 

## Setup

We use [Earthly](https://earthly.dev) to build files and images

You need Earthly dependencies
* Docker
* Git 

## Building

``` sh
earthly +build
```

This only builds the binary and saves it to an earthly artifact. Kinda useless by itself
If you want to build and then download the binary to your local machine run 

``` sh
earthly +save-binary
```

again **THIS IS A RANSOMWARE BOT** so be careful

## Testing

Because this is a ransomware bot, we highly suggest you run inside a container

To build the container, run

``` sh
earthly +docker
```

This stage creates an image called `imacry-run:latest`

and then to run

``` sh
docker run -it imacry-run:latest /bin/bash
```

## Benchmarking

To make a benchmarking container, run

``` sh
earthly +benchmarking
```

and to run it, run

``` sh
docker run imacry-benchmark
```

## Command & Control Server
You can checkout the cc servers README at `./cc-server/README`

## Contributing
You can read all about contributing to this project in `CONTRIBUTING.md`

## Architecture
You can read about it in `ARCHITECTURE.md`

## State and Communication Sequence

![Sequence Diagram](pictures/imacry_sequence_diagram.png)



