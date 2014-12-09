FROM debian:jessie
MAINTAINER Martin Simon <me@martinsimon.me>

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get update && \
  apt-get -y install \
  build-essential \
  curl \
  git

RUN \
  git clone https://github.com/MarvinMenzerath/HastebinPlus.git /opt/haste

RUN \
  curl -sL https://deb.nodesource.com/setup | bash -

RUN \
  apt-get install -y \
  nodejs

WORKDIR \
  /opt/haste

RUN \
  npm install

EXPOSE 8080
CMD ["npm", "start"]