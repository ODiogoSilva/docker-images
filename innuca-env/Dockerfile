# DOCKERFILE for INNUca environment
FROM ummidock/blast_binaries:2.6.0-binaries
MAINTAINER Diogo N. Silva, diogosilva@medicina.ulisboa.pt

RUN apt-get update && apt-get -y install \
	bzip2 \
	libmoo-perl \
	liblist-moreutils-perl \
	parallel \
	libjson-perl \
	libfile-slurp-perl \
	file \
	git \
	file \
	gzip \
	gcc \
	make \
    openjdk-8-jre \
    perl \
	python \
	python3 \
    unzip \
	bc \
	wget  \
	zlib1g-dev

# FASTQC
ADD http://www.bioinformatics.babraham.ac.uk/projects/fastqc/fastqc_v0.11.5.zip /NGStools/

WORKDIR /NGStools

RUN	unzip fastqc_*.zip && \
	chmod +x FastQC/fastqc && \
	rm -rf fastqc_*.zip

ENV PATH="/NGStools/FastQC:$PATH"

# TRIMMOMATIC
ADD http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/Trimmomatic-0.36.zip /NGStools/

WORKDIR /NGStools

RUN unzip Trimmomatic-0.36.zip 
WORKDIR /NGStools/Trimmomatic-0.36

RUN mv trimmomatic-0.36.jar trimmomatic.jar

# SPADES
WORKDIR /NGStools

RUN wget http://cab.spbu.ru/files/release3.11.0/SPAdes-3.11.0-Linux.tar.gz && tar -xf SPAdes-3.11.0-Linux.tar.gz

ENV PATH="/NGStools/SPAdes-3.11.0-Linux/bin:$PATH"

# SAMTOOLS AND BOWTIE
WORKDIR /NGStools

RUN wget https://sourceforge.net/projects/samtools/files/samtools/1.4.1/samtools-1.4.1.tar.bz2
RUN mkdir samtools && tar jxf samtools-1.4.1.tar.bz2 -C samtools --strip-components=1

WORKDIR /NGStools/samtools/

RUN ./configure --without-curses --disable-bz2 --disable-lzma
RUN make
ENV PATH="/NGStools/samtools:$PATH"

WORKDIR /NGStools/

RUN rm -rf samtools-1.4.1.tar.bz2 

RUN wget https://sourceforge.net/projects/bowtie-bio/files/bowtie2/2.3.3/bowtie2-2.3.3-linux-x86_64.zip && unzip bowtie2-2.3.3-linux-x86_64.zip
ENV PATH="/NGStools/bowtie2-2.3.3:$PATH"

# PILON
WORKDIR /NGStools/
RUN wget https://github.com/broadinstitute/pilon/releases/download/v1.22/pilon-1.22.jar

RUN chmod 744 pilon-1.22.jar

# MLST
RUN git clone https://github.com/tseemann/mlst.git
ENV PATH="/NGStools/mlst/bin:${PATH}"
