FROM ubuntu:16.04

ENV PACKAGES="\
build-essential \
git \
cmake \
pkg-config \
liblapack-dev \
libatlas-base-dev \
libeigen3-dev \
libgomp1 \
"

RUN apt-get update && apt-get install -y $PACKAGES
