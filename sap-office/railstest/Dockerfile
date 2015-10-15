FROM ruby:2.1

ENV http_proxy http://proxy.sin.sap.corp:8080
ENV https_proxy http://proxy.sin.sap.corp:8080

ADD . /code
WORKDIR /code

# see update.sh for why all "apt-get install"s have to stay as one long line
RUN apt-get update && apt-get install -y nodejs --no-install-recommends && rm -rf /var/lib/apt/lists/*

# see http://guides.rubyonrails.org/command_line.html#rails-dbconsole
RUN apt-get update && apt-get install -y mysql-client postgresql-client sqlite3 --no-install-recommends && rm -rf /var/lib/apt/lists/*

RUN bundle install
