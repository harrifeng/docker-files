FROM debian:6.0.10

MAINTAINER harrifeng "harrifeng@gmail.com"

RUN rm /etc/apt/sources.list
COPY sources.list.squeeze /etc/apt/sources.list

COPY jsl /usr/local/bin/jsl
COPY phantomjs /usr/local/bin/phantomjs

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

COPY ruby-2.1.5.tar.gz /root/

RUN cd /root && \
  tar -zxvf ruby-2.1.5.tar.gz && \
  cd ruby-2.1.5 && \
  CFLAGS="-march=native -O3" ./configure --disable-install-doc && \
  CFLAGS="-march=native -O3" make -j 9 && \
  make install && \
  cd .. && \
  rm -r ruby-2.1.5 ruby-2.1.5.tar.gz && \
  echo 'install: --no-rdoc --no-ri' > /.gemrc && \
  echo 'update: --no-rdoc --no-ri' >> /.gemrc
ENV TZ US/Pacific

RUN gem sources --remove https://rubygems.org/

RUN gem sources -a http://ruby.taobao.org/

RUN gem install bundler
