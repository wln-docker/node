## Node.js Dockerfile


This repository contains **Dockerfile** of [Node.js](http://nodejs.org/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/dockerfile/nodejs/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).


### Base Docker Image

* debian:jessie


### Installation

1. Install [Docker](https://www.docker.com/).

2. Download from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull debian:jessie`

   (alternatively, you can build an image from Dockerfile: `docker build -t="xiechaoyi/node" github.com/xiechaoyi/node`)


### Usage

    docker run -it --rm xiechaoyi/node

#### Run `node`

    docker run -it --rm xiechaoyi/node node

#### Run `npm`

    docker run -it --rm xiechaoyi/node npm
