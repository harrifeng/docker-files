FROM debian:6.0.10

MAINTAINER harrifeng "harrifeng@gmail.com"

RUN rm /etc/apt/sources.list
COPY sources.list.squeeze /etc/apt/sources.list

COPY jsl /user/local/bin/jsl
COPY phantomjs /user/local/bin/phantomjs

RUN apt-get update && \
      DEBIAN_FRONTEND=noninteractive apt-get -y install \
      supervisor \
      openssh-server \
      ffmpeg \
      build-essential \
      curl \
      git-core \
      libcurl4-openssl-dev \
      libreadline-dev \
      libssl-dev \
      libxml2-dev \
      libxslt1-dev \
      libyaml-dev \
      p7zip-full \
      zlib1g-dev \
      libmysqlclient-dev \
      mysql-client \
      imagemagick \
      libmagick++-dev \
      openjdk-6-jre \
      poppler-utils \
      opensaml2-tools \
      libicu-dev \
      unixodbc-dev \
      libffi-dev
