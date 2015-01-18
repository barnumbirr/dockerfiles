FROM debian:jessie
MAINTAINER Martin Simon <me@martinsimon.me>

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get -y install \
    lighttpd \
    php5-common \
    php5-fpm \
    php5-cli \
    php5-cgi \
    php5-mcrypt\
    php5-gd \
    php5 \
    sqlite \
    php5-sqlite \
    wget

RUN \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

RUN \
  cd /root && \
  wget http://baikal-server.com/get/baikal-regular-0.2.7.tgz -O baikal.tgz && \
  tar -xf baikal.tgz --strip 1 -C /var/www && \
  rm baikal.tgz

RUN \
  cd /var/www/Specific
  touch ENABLE_INSTALL

RUN \
  chown -R www-data:www-data /var/www && \
  rm /etc/lighttpd/lighttpd.conf

ADD \
  lighttpd.conf /etc/lighttpd/lighttpd.conf

EXPOSE 80

CMD ["/usr/sbin/lighttpd", "-D", "-f", "/etc/lighttpd/lighttpd.conf"]
