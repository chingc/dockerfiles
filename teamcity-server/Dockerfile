FROM java:openjdk-8-jre
MAINTAINER Ching Chow <https://github.com/chingc>

ARG TEAMCITY_SERVER_URL=https://download.jetbrains.com/teamcity/TeamCity-9.1.7.tar.gz

ENV TEAMCITY_SERVER_MEM_OPTS -Xmx4g -XX:MaxPermSize=270m -XX:ReservedCodeCacheSize=350m

RUN set -x \
        && wget -nv --show-progress --progress=dot:giga ${TEAMCITY_SERVER_URL} \
        && wget -nv -O - ${TEAMCITY_SERVER_URL}.sha256 | sha256sum -c - \
        && tar -xf $(basename ${TEAMCITY_SERVER_URL}) -C /opt \
        && rm $(basename ${TEAMCITY_SERVER_URL})

EXPOSE 8111

WORKDIR /opt/TeamCity/
