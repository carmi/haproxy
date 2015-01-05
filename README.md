## Haproxy Dockerfile


This repository contains my modified version of the **Dockerfile** of [Haproxy](http://haproxy.1wt.eu/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/dockerfile/haproxy/).


### Base Docker Image

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Build an image from github Dockerfile: `docker build -t="haproxy" github.com/carmi/haproxy`)


### Usage

    docker run -d -p 80:80 haproxy

#### Customizing Haproxy

    docker run -d -p 80:80 -v <override-dir>:/haproxy-override haproxy

where `<override-dir>` is an absolute path of a directory that could contain:

  - `haproxy.cfg`: custom config file (replace `/dev/log` with `127.0.0.1`, and comment out `daemon`)
  - `errors/`: custom error responses

After few seconds, open `http://<host>` to see the haproxy stats page.
