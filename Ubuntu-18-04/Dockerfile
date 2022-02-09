FROM ubuntu:18.04

ARG workspace_id
ENV wid ${workspace_id}
ARG workspace_key
ENV wkey ${workspace_key}

EXPOSE 25224/tcp

RUN mkdir /opt/la
RUN /usr/bin/apt-get update && /usr/bin/apt-get install -y wget curl sudo python3 gnupg2 && /usr/bin/apt-get -y upgrade && /usr/bin/apt-get -y clean
COPY ubiquiti.conf /opt/la/

WORKDIR /opt/la
RUN wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh
RUN sh onboard_agent.sh -w ${wid} -s ${wkey}

RUN sed -i "s/workspace_id/${wid}}/" ubiquiti.conf
COPY ubiquiti.conf /etc/opt/microsoft/omsagent/${wid}/conf/omsagent.d/