# DOCKERFILE for spades
FROM ubuntu:16.04
MAINTAINER Diogo N. Silva, diogosilva@medicina.ulisboa.pt

RUN apt-get update && apt-get -y install \
	python \
	python3 \
	wget


WORKDIR /NGStools

RUN wget https://github.com/ablab/spades/releases/download/v3.10.0/SPAdes-3.10.0-Linux.tar.gz && tar -xf SPAdes-3.10.0-Linux.tar.gz

ENV PATH="/NGStools/SPAdes-3.10.0-Linux/bin:$PATH"
