# docker-presto-cluster [![Build Status](https://travis-ci.org/Lewuathe/docker-presto-cluster.svg?branch=master)](https://travis-ci.org/Lewuathe/docker-presto-cluster)

docker-presto-cluster is a timple tool for launching multiple node [Presto](https://prestodb.io/) cluster on docker container.

## Build image

```
$ make
```

## Launch presto

Presto cluster can be launched by using docker-compose.

```
$ make run
```

## docker-compose.yml

Images are uploaded in [DockerHub](https://hub.docker.com/). These images are build with the latest master branch of Presto. You can launch multiple node docker presto cluster with below yaml file.

```
version: '2'

services:
  coordinator:
    image: lewuathe/presto-coordinator
    ports:
      - "8080:8080"
    container_name: "coordinator"
  worker0:
    image: lewuathe/presto-worker
    container_name: "worker0"
    ports:
      - "8081:8081"

```

Run

```
$ docker-compose up -d
```

# LICENSE

[MIT License](https://github.com/Lewuathe/docker-presto-cluster/blob/master/LICENSE)
