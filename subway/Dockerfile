FROM debian:jessie
MAINTAINER Martin Simon <me@martinsimon.me>

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get -y install \
    nodejs-legacy \
    npm \
    git

RUN \
  git clone https://github.com/thedjpetersen/subway.git && \
  cd subway && \
  npm install

WORKDIR /subway

EXPOSE 3000

CMD ["./subway.js"]
