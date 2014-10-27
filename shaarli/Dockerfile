FROM debian:jessie
MAINTAINER Martin Simon <me@martinsimon.me>

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get -y install \
    lighttpd \
    php5-common \
    php5-cgi \
    php5 \
    unzip \
    wget

RUN \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

RUN \
  cd /root && \
  wget https://github.com/sebsauvage/Shaarli/archive/master.zip -O shaarli.zip && \
  unzip shaarli.zip -d /var/www && \
  mv /var/www/Shaarli-master/* /var/www/ && \
  rm shaarli.zip && \
  rm -r /var/www/html && \
  rm -r /var/www/Shaarli-master

RUN \
  chown -R www-data:www-data /var/www && \
  rm /etc/lighttpd/lighttpd.conf

ADD \
  lighttpd.conf /etc/lighttpd/lighttpd.conf

EXPOSE 80

CMD ["/usr/sbin/lighttpd", "-D", "-f", "/etc/lighttpd/lighttpd.conf"]