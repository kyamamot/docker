FROM ubuntu:22.04

WORKDIR /tools

RUN apt-get update && \
    apt-get install -y \
    locales \
    rsync \
    wget \
    zip

RUN locale-gen en_US.UTF-8

RUN wget https://downloads.pacbcloud.com/public/software/installers/smrtlink_11.0.0.146107.zip && \
    unzip smrtlink_11.0.0.146107.zip && \
    ./smrtlink_11.0.0.146107.run --rootdir /tools/smrtlink-11.0.0.146107 --smrttools-only && \
    rm -f smrtlink_11.0.0.146107.zip

ENV PATH /tools/smrtlink-11.0.0.146107/smrtcmds/bin:${PATH}
