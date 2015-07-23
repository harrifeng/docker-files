FROM debian:6.0.10

MAINTAINER harrifeng "harrifeng@gmail.com"

ENV http_proxy http://proxy.sin.sap.corp:8080
ENV https_proxy http://proxy.sin.sap.corp:8080

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get -y install \
    supervisor \
    openssh-server
