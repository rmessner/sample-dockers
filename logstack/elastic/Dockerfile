FROM yaronr/openjdk-7-jre:latest
MAINTAINER Raphael MESSNER

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends tar && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.5.0.tar.gz && \
    tar -xzvf elasticsearch-1.5.0.tar.gz && \
    chmod +x /elasticsearch-1.5.0/bin/elasticsearch

EXPOSE 9200 9300

CMD /elasticsearch-1.5.0/bin/elasticsearch

