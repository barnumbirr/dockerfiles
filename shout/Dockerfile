FROM debian:jessie
MAINTAINER Martin Simon <me@martinsimon.me>

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get -y install \
    nodejs-legacy \
    npm

RUN \
  npm install -g shout

EXPOSE 8081

ENTRYPOINT ["shout"]
