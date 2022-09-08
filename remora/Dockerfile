FROM python:3.7.13-buster
MAINTAINER Keisuke Yamamoto <ke1suke.yamam0t0.123@gmail.com>

WORKDIR /tools

RUN pip install --upgrade pip

# torch-1.21.1 + cuda-11.3
RUN pip install torch==1.12.1 torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu113 && \
    pip install onnxruntime-gpu==1.12.1

# remora-1.1.1
RUN wget https://github.com/nanoporetech/remora/archive/refs/tags/v1.1.1.tar.gz && \
    tar xzf v1.1.1.tar.gz && \
    rm -f v1.1.1.tar.gz && \
    pip install remora-1.1.1/

# megalodon-2.5.0
RUN pip install ont-pyguppy-client-lib==6.1.2 && \
    pip install megalodon==2.5.0

# taiyaki-5.3.0
RUN wget https://github.com/nanoporetech/taiyaki/archive/refs/tags/v5.3.0.tar.gz && \
    tar xzf v5.3.0.tar.gz && \
    rm -f v5.3.0.tar.gz && \
    pip install taiyaki-5.3.0/
