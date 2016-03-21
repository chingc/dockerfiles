FROM alpine:latest
MAINTAINER Ching Chow

COPY entropy_level /usr/local/bin

RUN set -x \
        && apk update && apk add haveged \
        && rm -rf /var/cache/apk/*

ENTRYPOINT ["haveged"]
CMD ["--help"]
