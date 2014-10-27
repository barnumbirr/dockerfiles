FROM debian:jessie
MAINTAINER Martin Simon <me@martinsimon.me>

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get -y install \
    build-essential \
    make \
    wget \
    python \
    git

RUN \
  cd && \
  wget https://bootstrap.pypa.io/get-pip.py && \
  python get-pip.py && \
  rm get-pip.py

RUN \
  git clone https://github.com/sh4nks/flaskbb.git && \
  cd flaskbb &&\
  pip install -r requirements.txt && \
  cp flaskbb/configs/development.py.example flaskbb/configs/development.py && \
  python manage.py createall && \
  sed -i 's/^manager.add_command("runserver", Server("localhost", port=8080))$/manager.add_command("runserver", Server("0.0.0.0", port=8080))/' manage.py

WORKDIR /flaskbb
EXPOSE 8080

CMD ["python", "manage.py", "runserver"]