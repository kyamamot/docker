FROM python:3.7.10-buster
MAINTAINER Keisuke Yamamoto <ke1suke.yamam0t0.123@gmail.com>

WORKDIR /tools

RUN wget https://files.pythonhosted.org/packages/a4/93/626d85f2df4479341bd69272b71e0451a19c54e86383dbdca78ec226162f/nanomath-1.2.1.tar.gz && \
    tar xzf nanomath-1.2.1.tar.gz && \
    sed -i "s#self._qualgroups = \[5, 7, 10, 12, 15\]#self._qualgroups = [10, 20, 30, 35, 40]#" nanomath-1.2.1/nanomath/nanomath.py

RUN pip install file:///tools/nanomath-1.2.1/
RUN pip install NanoStat==1.6.0

