FROM ubuntu:latest
MAINTAINER Ching Chow

COPY entropy_* /usr/local/bin/

RUN set -x \
        && apt-get -q update && apt-get -qy install haveged \
        && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["haveged"]
CMD ["--help"]
