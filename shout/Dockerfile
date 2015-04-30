FROM alpine:latest
MAINTAINER Martin Simon <me@martinsimon.me>

RUN \
    apk add --update \
        nodejs && \
        rm -rf /var/cache/apk/*

RUN \
    npm install -g shout

VOLUME /root/.shout

EXPOSE 8081

ENTRYPOINT ["shout"]