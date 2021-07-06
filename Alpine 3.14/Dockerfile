FROM alpine:3.14

RUN mkdir /opt/la && \
    apk update && \ 
    apk upgrade --available

COPY ubiquiti.conf /opt/la/