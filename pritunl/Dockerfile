FROM ubuntu:14.04
MAINTAINER Martin Simon <me@martinsimon.me>

RUN \
  apt-get update -q

RUN \
  apt-get install -y software-properties-common python-software-properties

RUN \
  add-apt-repository -y ppa:pritunl

RUN \
  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10 && \
  echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' > /etc/apt/sources.list.d/mongodb.list

RUN \
  apt-get update -q

RUN \
  apt-get install -y mongodb-org pritunl

ADD \
  entry.sh /bin/entry.sh

RUN \
  mkdir -p /data/db

EXPOSE 9700
EXPOSE 1194
EXPOSE 11194
EXPOSE 27017

CMD ["mongod", "--fork", "--logpath", "/var/log/mongodb.log"]

ENTRYPOINT ["/bin/entry.sh"]

CMD ["/usr/bin/tail", "-f","/var/log/pritunl.log"]