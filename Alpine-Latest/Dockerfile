FROM alpine:latest

ARG workspace_id
ENV wid ${workspace_id}
ARG workspace_key
ENV wkey ${workspace_key}

EXPOSE 25224/tcp

RUN apk update && apk add wget curl sudo python3 gnupg2 && apk upgrade --available

RUN mkdir /opt/la
COPY ubiquiti.conf /opt/la/

WORKDIR /opt/la
RUN wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh
RUN sh onboard_agent.sh -w ${wid} -s ${wkey}

RUN sed -i "s/workspace_id/${wid}}/" ubiquiti.conf
COPY ubiquiti.conf /etc/opt/microsoft/omsagent/${wid}/conf/omsagent.d/