FROM alpine:3.9.4

RUN apk --update --no-cache upgrade && \
    apk --update --no-cache add \
        libressl \
        ca-certificates \
        curl

RUN adduser -D -G nobody -h /container -g container -s /bin/sh -u 1160 container

ARG NODEJS_VERSION=10.16.0-r0
RUN apk --update --no-cache add nodejs=${NODEJS_VERSION} --repository http://dl-cdn.alpinelinux.org/alpine/edge/main

WORKDIR /container
USER 1160

ONBUILD USER root
