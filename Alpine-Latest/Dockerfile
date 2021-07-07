FROM alpine:latest

RUN mkdir /opt/la && \
    apk update && \ 
    apk upgrade --available

# Copy the ubiquiti.conf file
COPY ubiquiti.conf /opt/la/