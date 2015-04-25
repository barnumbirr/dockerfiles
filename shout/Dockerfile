FROM alpine:3.1
MAINTAINER Martin Simon <me@martinsimon.me>

RUN \
   apk add --update \
  nodejs

RUN \
    npm install -g shout

VOLUME /root/.shout

EXPOSE 8081

ENTRYPOINT ["shout"]