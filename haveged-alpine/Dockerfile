FROM alpine:latest
MAINTAINER Ching Chow

RUN set -x \
        && apk update && apk add haveged \
        && rm -rf /var/cache/apk/*

COPY entropy_* /usr/local/bin/

ENTRYPOINT ["haveged"]
CMD ["--help"]
