# Run Mutt from a container
#
# docker run -it \
#	-v $(pwd)/config:/home/user/.newsbeuter \
#	--name newsb \
#	ryan/newsbeuter

FROM alpine:3.3
MAINTAINER Ryan Desfosses <ryan@desfo.org>

USER root

RUN apk add --update \
      newsbeuter \
       vim \
    && rm -fr /var/cache/apk/*

RUN addgroup -g 1000 user \
    && adduser -D -G user -u 1000 user

ENV HOME /home/user
ENV TERM xterm-256color

USER user
WORKDIR $HOME

Entrypoint ["newsbeuter"]
