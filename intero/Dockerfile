
FROM rdesfo/stack
LABEL maintainer "Ryan Desfosses <ryan@desfo.org>"

USER root

RUN apt-get update \
    && apt-get install -y \
       emacs24 \
       libgl1-mesa-glx \
       libncurses5-dev \
    && rm -rf /var/lib/apt/lists/*

COPY emacs /home/user/.emacs

RUN chown -R user:user /home/user

USER user

RUN emacs -batch -l ~/.emacs -eval '(package-initialize)' \
    && emacs -batch -l ~/.emacs -eval '(package-refresh-contents)'


