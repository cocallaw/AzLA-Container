FROM alpine:latest

RUN mkdir /opt/la && \
    apk update && \ 
    apk upgrade --available

# Copy the ubiquiti.conf file
COPY ubiquiti.conf /opt/la/

WORKDIR /opt/la
RUN wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh