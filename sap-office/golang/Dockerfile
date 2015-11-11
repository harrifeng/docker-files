FROM golang

ENV http_proxy http://proxy.sin.sap.corp:8080
ENV https_proxy http://proxy.sin.sap.corp:8080

RUN go get github.com/harrifeng/todo/todo
CMD todo
