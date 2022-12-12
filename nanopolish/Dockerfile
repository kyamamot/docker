FROM python:3.10.8-buster
MAINTAINER Keisuke Yamamoto <ke1suke.yamam0t0.123@gmail.com>

WORKDIR /tools

RUN git clone --recursive https://github.com/jts/nanopolish.git && \
    cd nanopolish && \
    git checkout v0.14.0 && \
    make
