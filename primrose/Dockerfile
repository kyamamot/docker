FROM continuumio/miniconda3
MAINTAINER Keisuke Yamamoto <ke1suke.yamam0t0.123@gmail.com>

WORKDIR /tools

RUN wget https://github.com/PacificBiosciences/pb-CpG-tools/archive/refs/tags/v1.1.0.tar.gz && \
    tar xzf v1.1.0.tar.gz && \
    rm -f v1.1.0.tar.gz && \
    cd pb-CpG-tools-1.1.0 && \
    grep -v "^name" conda_env_cpg.yaml > conda_env.yaml && \
    conda env update -n base -f conda_env.yaml

RUN conda config --add channels conda-forge && \
    conda config --add channels bioconda && \
    conda install -y \
    pbccs=6.4.0 \
    primrose=1.3.0 \
    pbbam=2.1.0

