FROM debian:6.0.10

MAINTAINER harrifeng "harrifeng@gmail.com"

ENV http_proxy http://172.28.64.41:8080
ENV https_proxy http://172.28.64.41:8080

COPY jsl /usr/local/bin/jsl
COPY phantomjs /usr/local/bin/phantomjs

RUN apt-get update && \
      DEBIAN_FRONTEND=noninteractive apt-get -y install \
      zip \
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
      libffi-dev

RUN curl -O http://ftp.ruby-lang.org/pub/ruby/ruby-2.1.5.tar.gz && \
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
RUN gem install bundler
