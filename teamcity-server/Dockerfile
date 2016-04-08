FROM java:openjdk-8-jre
MAINTAINER Ching Chow

ARG VERSION=9.1.6

ENV TEAMCITY_SERVER_MEM_OPTS -Xmx4g -XX:MaxPermSize=270m -XX:ReservedCodeCacheSize=350m

RUN set -x \
        && apt-get -q update && apt-get -qy install haveged \
        && rm -rf /var/lib/apt/lists/*

RUN set -x \
        && wget -nv --show-progress --progress=dot:giga https://download.jetbrains.com/teamcity/TeamCity-${VERSION}.tar.gz \
        && wget -nv -O - https://download.jetbrains.com/teamcity/TeamCity-${VERSION}.tar.gz.sha256 | sha256sum -c - \
        && tar -xf TeamCity-${VERSION}.tar.gz -C /opt \
        && rm TeamCity-${VERSION}.tar.gz

COPY entropy_* /usr/local/bin/

EXPOSE 8111

WORKDIR /opt/TeamCity/
