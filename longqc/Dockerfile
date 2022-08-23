# build minimap2-coverage
FROM continuumio/miniconda3

WORKDIR /tools

MAINTAINER Yoshinori Fukasawa <yoshinori.fukasawa@kaust.edu.sa>

### Basic dependency ###
RUN apt-get clean all && \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y  \
    git \
    build-essential \
    libc6-dev \
    zlib1g-dev && \
    apt-get clean && \
    apt-get purge

### LongQC installation ###
ADD https://api.github.com/repos/yfukasawa/longqc/git/refs/heads/minimap2_update version.json
RUN git clone https://github.com/yfukasawa/LongQC.git
RUN cd /tools/LongQC/minimap2-coverage && make
RUN cd /tools/LongQC && \
    sed -i \
    -e '1{s;^;#!/opt/conda/bin/python\n;}' \
    longQC.py && \
    chmod +x longQC.py

### install LongQC's dependency ###
RUN conda config --add channels conda-forge && \
    conda config --add channels bioconda && \
    conda install -y \
    python=3.9 \
    numpy \
    pandas'>=0.24.0' \
    scipy \
    jinja2 \
    h5py'<3.2' \
    matplotlib'>=2.1.2' \
    scikit-learn && \
    conda install -y -c bioconda \
    edlib \
    pysam \
    python-edlib

### Define PATH ###
ENV PATH="/tools/LongQC:$PATH"
