FROM alpine:3.14

ARG workspace_id
ENV wid ${workspace_id}
ARG workspace_key
ENV wkey ${workspace_key}

EXPOSE 25224/tcp

RUN mkdir /opt/la && apk update && apk upgrade --available

COPY ubiquiti.conf /opt/la/

WORKDIR /opt/la
RUN wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh

ENTRYPOINT [ "/opt/la/onboard_agent.sh -w ${wid} -s ${wkey} -d opinsights.azure.com" ]