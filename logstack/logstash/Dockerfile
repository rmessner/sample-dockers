FROM yaronr/openjdk-7-jre:latest
MAINTAINER Raphael MESSNER

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends tar && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN wget http://download.elasticsearch.org/logstash/logstash/logstash-1.5.0.rc2.tar.gz && \
    tar -xzvf logstash-1.5.0.rc2.tar.gz && \
    chmod +x /logstash-1.5.0.rc2/bin/logstash && \
    chmod +x /logstash-1.5.0.rc2/bin/plugin && \
    mkdir /conf

VOLUME ["/conf"]

EXPOSE 8080

CMD /logstash-1.5.0.rc2/bin/logstash agent -f /conf/logstash.conf

