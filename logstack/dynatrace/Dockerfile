FROM yaronr/openjdk-7-jre:latest
MAINTAINER Raphael MESSNER

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yq --no-install-recommends tar unzip supervisor && \
	mkdir -p /var/log/supervisor && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
	
RUN wget http://archive.apache.org/dist/flume/1.3.1/apache-flume-1.3.1-bin.tar.gz && \
    wget https://github.com/dynaTrace/Dynatrace-Big-Data-Business-Transaction-Bridge/releases/download/v1.0.1/big_data_business_transaction_bridge_1_0_1.zip && \
	wget https://download.elasticsearch.org/logstash/logstash/logstash-1.4.2.zip 
	
RUN tar -xzvf apache-flume-1.3.1-bin.tar.gz && \
	unzip big_data_business_transaction_bridge_1_0_1.zip && \
	unzip logstash-1.4.2.zip 
	
RUN chmod +x logstash-1.4.2/bin/logstash && \
    chmod +x /apache-flume-1.3.1-bin/bin/flume-ng && \
	mkdir -p logstash-1.4.2/conf.d && \
	mkdir -p /data/pp && \
	mkdir -p /data/visit && \
	mkdir -p /data/pa && \
	cp flume-json-conf.properties flume-conf.properties 
    

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY logstash.conf /logstash-1.4.2/conf.d/logstash.conf
	
EXPOSE 4321
	
CMD ["/usr/bin/supervisord"]
