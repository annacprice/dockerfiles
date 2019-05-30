FROM ubuntu:16.04

ENV PACKAGES="\
wget \
software-properties-common \
python-software-properties \
"

RUN apt-get update && apt-get -y upgrade && apt-get update \
&& apt-get install -y $PACKAGES \
&& add-apt-repository ppa:linuxuprising/java \
&& apt-get update \
&& echo oracle-java11-installer shared/accepted-oracle-license-v1-2 select true | /usr/bin/debconf-set-selections \
&& apt-get install -y oracle-java11-installer \
&& wget http://www.us.apache.org/dist/ant/binaries/apache-ant-1.10.6-bin.tar.gz \
&& tar -xf apache-ant-1.10.6-bin.tar.gz \
&& mv apache-ant-1.10.6 /opt \
&& rm apache-ant* \
&& export LC_ALL=C.UTF-8

ENV PATH ${PATH}:/opt/apache-ant-1.10.6/bin 
