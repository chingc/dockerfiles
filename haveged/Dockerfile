FROM ubuntu:latest
MAINTAINER Ching Chow

RUN set -x \
        && apt-get -q update && apt-get -qy install haveged \
        && rm -rf /var/lib/apt/lists/*

COPY entropy_level /usr/local/bin

ENTRYPOINT ["haveged"]
CMD ["--help"]
