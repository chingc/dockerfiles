FROM alpine:latest
MAINTAINER Ching Chow

COPY entropy_* /usr/local/bin/

RUN set -x \
        && apk update && apk add haveged \
        && rm -rf /var/cache/apk/*

ENTRYPOINT ["haveged"]
CMD ["--help"]
