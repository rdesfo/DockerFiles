FROM rdesfo/stack:latest
LABEL maintainer "Ryan Desfosses <ryan@desfo.org>"

RUN stack setup --compiler ghc-7.10.3

RUN stack install --resolver lts-6.25 hakyll
