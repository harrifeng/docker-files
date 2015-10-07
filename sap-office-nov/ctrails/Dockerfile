FROM ruby:2.1

MAINTAINER harrifeng "harrifeng@gmail.com"

ENV http_proxy http://172.28.64.41:8080
ENV https_proxy http://172.28.64.41:8080

# see update.sh for why all "apt-get install"s have to stay as one long line
RUN apt-get update && apt-get install -y nodejs --no-install-recommends && rm -rf /var/lib/apt/lists/*

# see http://guides.rubyonrails.org/command_line.html#rails-dbconsole
RUN apt-get update && apt-get install -y mysql-client postgresql-client sqlite3 --no-install-recommends && rm -rf /var/lib/apt/lists/*
