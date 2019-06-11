FROM python:2.7-slim

ENV PACKAGES="\
pkg-config \
libopenblas-dev \
liblapack-dev \
build-essential  \
gfortran \
python-dev \
libfreetype6-dev \
libjpeg-dev \
libhdf5-dev \
liblzo2-dev \
libbz2-dev \
"

ENV PY_PACKAGES="\
numpy \
scipy \
scikit-learn \
pandas\
"

RUN apt-get update && \
apt-get install -y $PACKAGES && \
pip install --upgrade pip && \
pip install --no-cache-dir $PY_PACKAGES
