#
# ghc 7.8.3 dockerfile
#
# VERSION               0.1.0

# base image
FROM ubuntu:14.04
MAINTAINER Ryan Desfosses <ryan@desfo.org>

RUN \
  apt-get update && \
  apt-get install -y git wget cabal-install && \
  apt-get build-dep -y ghc

RUN cabal update && \
    cabal install alex happy    

RUN cd /tmp && \
    wget https://www.haskell.org/ghc/dist/7.8.3/ghc-7.8.3-x86_64-unknown-linux-deb7.tar.bz2 && \
    tar xvfj ./ghc-7.8.3-x86_64-unknown-linux-deb7.tar.bz2

RUN cd /tmp/ghc-7.8.3 && \
    PATH=/root/.cabal/bin:$PATH ./configure && \
    make install
