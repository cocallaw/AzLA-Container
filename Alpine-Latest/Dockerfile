FROM alpine:latest

ARG workspace_id
ENV wid ${workspace_id}
ARG workspace_key
ENV wkey ${workspace_key}

RUN mkdir /opt/la && apk update && apk upgrade --available

# Copy the ubiquiti.conf file
COPY ubiquiti.conf /opt/la/

WORKDIR /opt/la
RUN wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh

ENTRYPOINT [ "/opt/la/onboard_agent.sh -w ${wid} -s ${wkey} -d opinsights.azure.com" ]