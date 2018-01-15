FROM alpine:latest
LABEL maintainer "Ryan Desfosses <ryan@desfo.org>"

RUN apk --no-cache add \
        curl \
        ca-certificates \
        openssl

RUN addgroup -g 1000 user
RUN adduser -D -G user -u 1000 user

USER user
WORKDIR /tmp

RUN curl -LO https://github.com/exercism/cli/releases/download/v2.4.1/exercism-linux-64bit.tgz \
    && tar -xzvf exercism-linux-64bit.tgz \
    && rm exercism-linux-64bit.tgz
RUN mkdir ~/bin \
    && mv exercism ~/bin/ \
    && echo 'export PATH=$HOME/bin:$PATH' >> ~/.bashrc

WORKDIR /home/user

