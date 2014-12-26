FROM debian:jessie
MAINTAINER Martin Simon <me@martinsimon.me>

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get -y install \
    ircd-hybrid \
    hybserv

RUN \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

RUN \
  rm /etc/ircd-hybrid/ircd.conf && \
  rm /etc/hybserv/settings.conf && \
  rm /etc/ircd-hybrid/ircd.motd && \

ADD \
  ircd.conf /etc/ircd-hybrid/ircd.conf

ADD \
  settings.conf /etc/hybserv/settings.conf

ADD \
  ircd.motd /etc/ircd-hybrid/ircd.motd

RUN \
  /etc/init.d/ircd-hybrid restart

EXPOSE 6667
EXPOSE 6697