
FROM alpine:3.5
LABEL maintainer "Ryan Desfosses <ryan@desfo.org>"

USER root

RUN apk add --update \
      vim \
    && rm -fr /var/cache/apk/*

RUN addgroup -g 1000 user \
    && adduser -D -G user -u 1000 user

USER user
WORKDIR /home/user

ENTRYPOINT ["vim"]
