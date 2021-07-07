FROM ubuntu:latest

ARG workspace_id
ENV wid ${workspace_id}
ARG workspace_key
ENV wkey ${workspace_key}

RUN mkdir /opt/la && \
    apt update -y && \ 
    apt upgrade -y && \
    apt install wget -y && \
    apt clean -y

COPY ubiquiti.conf /opt/la/

WORKDIR /opt/la
RUN wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh
