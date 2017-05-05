
FROM alpine:3.3
LABEL maintainer "Ryan Desfosses <ryan@desfo.org>"

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

COPY bashrc /home/user/.bashrc
RUN chown -R user:user /home/user

USER user
WORKDIR /home/user

ENTRYPOINT ["bash"]
