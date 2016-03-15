FROM ubuntu:16.04
MAINTAINER Ching Chow

RUN set -x \
        && apt-get -q update && apt-get -qy install \
               openjdk-8-jre-headless \
        \
        # see https://bugs.debian.org/775775
        # and https://github.com/docker-library/java/issues/19#issuecomment-70546872
        && /var/lib/dpkg/info/ca-certificates-java.postinst configure \
        \
        && rm -rf /var/lib/apt/lists/*

COPY java_home /usr/local/bin/
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/jre
