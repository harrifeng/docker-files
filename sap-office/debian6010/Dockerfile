FROM debian:6.0.10

MAINTAINER harrifeng "harrifeng@gmail.com"

ENV http_proxy http://proxy.sin.sap.corp:8080
ENV https_proxy http://proxy.sin.sap.corp:8080

COPY jsl /user/local/bin
COPY phantomjs /user/local/bin

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
      poppler-utils \
      opensaml2-tools \
      libicu-dev \
      unixodbc-dev \
      default-jdk \
      mysql-server \
      libffi-dev
