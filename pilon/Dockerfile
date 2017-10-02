# DOCKERFILE for trimmomatic 
FROM ubuntu:16.04
MAINTAINER Diogo N. Silva, diogosilva@medicina.ulisboa.pt

RUN apt-get update && apt-get -y install \
	python3 \
    openjdk-8-jre \
    unzip

ADD https://github.com/broadinstitute/pilon/releases/download/v1.22/pilon-1.22.jar /NGStools/

WORKDIR /NGStools
RUN chmod 744 pilon-1.22.jar

