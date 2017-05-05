FROM ubuntu:16.04
LABEL maintainer "Ryan Desfosses <ryan@desfo.org>"

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 575159689BEFB442 \
    && echo 'deb http://download.fpcomplete.com/ubuntu xenial main' | tee /etc/apt/sources.list.d/fpco.list

RUN apt-get update \
    && apt-get install -y \
       stack \
       --no-install-recommends \ 
    && rm -rf /var/lib/apt/lists/*

RUN groupadd -g 1000 user \
    && useradd --create-home -d /home/user -g user -u 1000 user

USER user
WORKDIR /home/user

RUN stack setup

ENV LANG "C.UTF-8"
