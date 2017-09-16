FROM alpine:latest
LABEL maintainer "Ryan Desfosses <ryan@desfo.org>"

RUN apk --no-cache add \
      python3 \
      openjdk8-jre-base

RUN pip3 install --no-cache-dir html5validator

RUN addgroup -g 1000 user \
    && adduser -D -G user -u 1000 user

USER user
WORKDIR /home/user

ENV LANG "C.UTF-8"

