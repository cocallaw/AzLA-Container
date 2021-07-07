FROM ubuntu:18.04

RUN mkdir /opt/la && \
    apt update && \ 
    apt upgrade && \
    apt clean

COPY ubiquiti.conf /opt/la/
