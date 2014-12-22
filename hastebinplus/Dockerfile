FROM debian:jessie
MAINTAINER Martin Simon <me@martinsimon.me>

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get update && \
  apt-get -y install \
  nodejs \
  nodejs-legacy \
  npm \
  git

RUN \
  git clone https://github.com/MarvinMenzerath/HastebinPlus.git /opt/haste

WORKDIR \
  /opt/haste

RUN \
  npm install

RUN \
  apt-get clean

RUN \
  rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 8080

CMD ["npm", "start"]