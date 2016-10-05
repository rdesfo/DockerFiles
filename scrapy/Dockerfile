FROM python:2.7.11
MAINTAINER Ryan Desfosses <ryan@desfo.org>

RUN pip install --upgrade pip

RUN pip install scrapy shub

RUN groupadd -g 1000 user && \
    useradd -m -g user -u 1000 user

USER user
WORKDIR /home/user

