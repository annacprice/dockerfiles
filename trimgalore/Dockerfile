FROM ubuntu:16.04

ENV PACKAGES="\
wget \
openjdk-8-jre-headless \
python-cutadapt \
unzip \
libfindbin-libs-perl \
"

RUN apt-get update \
&& apt-get install -y $PACKAGES

RUN wget https://www.bioinformatics.babraham.ac.uk/projects/fastqc/fastqc_v0.11.7.zip \
&& unzip fastqc_v0.11.7.zip \
&& chmod +x FastQC/fastqc \
&& mv FastQC /usr/local/bin \
&& rm -r fastqc*

ENV PATH "${PATH}":/usr/local/bin/FastQC/

RUN wget -O trim_galore.tar.gz https://github.com/FelixKrueger/TrimGalore/archive/0.6.5.tar.gz \
&& tar -xzf trim_galore.tar.gz \
&& mv TrimGalore-0.6.5/trim_galore /usr/local/bin \
&& rm -r trim_galore*

CMD ["/bin/bash"]
