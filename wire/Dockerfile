
FROM ubuntu:16.04
MAINTAINER Ryan Desfosses <ryan@desfo.org>

RUN apt-get update \
    && apt-get install -y \
       libncurses5-dev \
       nodejs \
       wget \
       git \
       gconf2 \
       gconf-service \
       gvfs-bin \
       libgtk2.0-0 \
       libnotify4 \
       libnss3 \
       libxtst6 \
       python \
       xdg-utils \
       ca-certificates \
       --no-install-recommends \
    && rm -rf /var/lib/apt/lists/* \
    && ln -s $(which nodejs) /usr/bin/node

RUN wget https://wire-app.wire.com/linux/wire_2.11.2661_amd64.deb -O /tmp/wire.deb \
    && dpkg -i /tmp/wire.deb

RUN groupadd -g 1000 user \
    && useradd --create-home -d /home/user -g user -u 1000 user

USER user
WORKDIR /home/user
