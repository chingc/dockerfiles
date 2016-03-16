FROM ubuntu:latest
MAINTAINER Ching Chow

RUN set -x \
        && apt-get -q update && apt-get -qy install openjdk-7-jre-headless \
        && rm -rf /var/lib/apt/lists/*

COPY java_home /usr/local/bin/

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64/jre

ENTRYPOINT ["java"]
CMD ["-help"]
