FROM alpine:latest
MAINTAINER Ching Chow

RUN set -x \
        && apk update && apk add haveged \
        && rm -rf /var/cache/apk/*

COPY entropy_level /usr/local/bin

ENTRYPOINT ["haveged"]
CMD ["--help"]
