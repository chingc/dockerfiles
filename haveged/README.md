# haveged

A simple entropy daemon.


### Description

Running out of entropy appears to be a common problem when it comes to docker containers.  This `Dockerfile` will build an image containing `haveged` to provide the necessary entropy.  It supplies entropy to the entire docker host, not just its own container.


### Build

`$ docker build -t haveged .`


### Run

`$ docker run --rm -it --cap-add SYS_ADMIN haveged`


### Help

`$ docker run --rm haveged --help`
