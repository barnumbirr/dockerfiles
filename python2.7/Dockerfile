FROM alpine:3.1
MAINTAINER Martin Simon <me@martinsimon.me>

RUN \
    apk add --update \
        python \
        curl

RUN \
    rm -rf /var/cache/apk/*

RUN \
    curl -SL 'https://bootstrap.pypa.io/get-pip.py' | python

RUN \
    pip install virtualenv

RUN \
    mkdir -p /var/python

WORKDIR /var/python/

CMD ["python"]