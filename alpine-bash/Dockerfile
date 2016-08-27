
FROM alpine:3.3
MAINTAINER Ryan Desfosses <ryan@desfo.org>

USER root

RUN apk add --update \
      bash \
      bash-completion \
      util-linux \
      pciutils \
      usbutils \
      coreutils \
      binutils \
      findutils \
      grep \
      less \       
    && rm -fr /var/cache/apk/*

RUN addgroup -g 1000 user \
    && adduser -D -G user -u 1000 user

USER user
WORKDIR /home/user

COPY bashrc /home/user/.bashrc

ENTRYPOINT ["bash"]
