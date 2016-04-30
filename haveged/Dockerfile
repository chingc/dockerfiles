FROM alpine:latest
MAINTAINER Ching Chow <https://github.com/chingc>

RUN set -x \
        && apk update && apk add haveged \
        && rm -rf /var/cache/apk/*

COPY entropy_* /usr/local/bin/

WORKDIR /usr/local/bin/

ENTRYPOINT ["entropy_fill", "-F"]
CMD [""]
