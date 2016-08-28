
FROM rdesfo/alpine-bash
MAINTAINER Ryan Desfosses <ryan@desfo.org>

USER root

RUN apk add --update \
      git \
      git-bash-completion \
    && rm -fr /var/cache/apk/*

USER user
WORKDIR /home/user

ENTRYPOINT ["bash"]
