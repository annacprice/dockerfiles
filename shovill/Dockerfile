FROM conda/miniconda2

RUN conda config --add channels defaults &&\
conda config --add channels bioconda &&\
conda config --add channels conda-forge

RUN conda install spades \
skesa \
megahit \
velvet \
lighter \
flash \
samtools \
bwa \
mash \
seqtk \
pilon \
trimmomatic \
&& conda clean --all

RUN apt-get update && apt-get -y install git pigz parallel

RUN cd /opt && git clone https://github.com/tseemann/shovill.git

ENV PATH="opt/shovill/bin:${PATH}"

RUN parallel -j 8 shovill --R1 /data/{}_1.fastq.gz --R2 /data/{}_2.fastq.gz --cpus 6 --ram 80 --outdir /data/{}_output ::: $(ls *.fastq.gz | rev | cut -c 12- |rev | uniq)
