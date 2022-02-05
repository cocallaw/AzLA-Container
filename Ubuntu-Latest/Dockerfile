FROM ubuntu:18.04

ARG workspace_id
ENV wid ${workspace_id}
ARG workspace_key
ENV wkey ${workspace_key}

EXPOSE 25224/tcp

RUN mkdir /opt/la
RUN /usr/bin/apt-get update && /usr/bin/apt-get install -y wget && /usr/bin/apt-get -y upgrade && /usr/bin/apt-get -y clean

COPY ubiquiti.conf /opt/la/

WORKDIR /opt/la
RUN wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh

COPY ubiquiti.conf /etc/opt/microsoft/omsagent/${wid}/conf/omsagent.d/