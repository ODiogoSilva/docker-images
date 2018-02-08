# DOCKERFILE for assemblerflow_base
FROM ubuntu:16.04
MAINTAINER Diogo N. Silva, diogosilva@medicina.ulisboa.pt

RUN apt-get update && apt-get -y install \
	git \
	python3

WORKDIR /assemblerflow_utils

RUN git clone https://github.com/ODiogoSilva/templates.git 

ARG ASSEMBLERFLOW_UTILS
ENV ASSEMBLERFLOW_UTILS="/assemblerflow_utils/templates/"
