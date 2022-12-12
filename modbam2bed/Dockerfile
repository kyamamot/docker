FROM python:3.10.8-buster
MAINTAINER Keisuke Yamamoto <ke1suke.yamam0t0.123@gmail.com>

WORKDIR /tools

RUN git clone --recursive https://github.com/epi2me-labs/modbam2bed.git -b v0.6.3 && \
    cd modbam2bed && \
    make modbam2bed
