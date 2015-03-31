FROM yaronr/openjdk-7-jre:latest
MAINTAINER Raphael MESSNER

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends tar && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN wget https://download.elasticsearch.org/kibana/kibana/kibana-4.0.1-linux-x64.tar.gz && \
    tar -xzvf kibana-4.0.1-linux-x64.tar.gz && \
    chmod +x /kibana-4.0.1-linux-x64/bin/kibana 

VOLUME ["/kibana-4.0.1-linux-x64/config/kibana.yml"]

EXPOSE 5601

CMD /kibana-4.0.1-linux-x64/bin/kibana

