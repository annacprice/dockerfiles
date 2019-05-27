FROM alpine:latest

ENV PACKAGES="\
lapack-dev \
freetype-dev \
gcc \
"

ENV VIRTUAL_PACKAGES="\
gfortran \
g++ \
musl-dev \
"

ENV ADD_PYTHON="\
python \
py-pip \
python-dev \
"

# lapack is in community repostitory
RUN echo "http://dl-4.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories

RUN apk update --no-cache && apk upgrade --no-cache && apk update --no-cache \
&& apk add --no-cache $PACKAGES \
&& apk add --no-cache $ADD_PYTHON \
&& apk add --no-cache --virtual .build-deps $VIRTUAL_PACKAGES \
&& ln -s /usr/include/locale.h /usr/include/xlocale.h \
&& pip install --no-cache-dir seaborn \
&& apk del .build-deps 
