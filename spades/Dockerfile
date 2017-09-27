# DOCKERFILE for spades
FROM ubuntu:16.04
MAINTAINER Diogo N. Silva, diogosilva@medicina.ulisboa.pt

RUN apt-get update && apt-get -y install \
	gcc \
	gzip \
	make \
	wget

WORKDIR /NGStools

RUN wget http://cab.spbu.ru/files/release3.11.0/SPAdes-3.11.0-Linux.tar.gz && tar -xf SPAdes-3.11.0-Linux.tar.gz

ENV PATH="SPAdes-3.11.0-Linux/bin:$PATH"
