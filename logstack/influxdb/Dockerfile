FROM yaronr/openjdk-7-jre:latest
MAINTAINER Raphael MESSNER

RUN wget https://s3.amazonaws.com/influxdb/influxdb_latest_amd64.deb && \
  dpkg -i influxdb_latest_amd64.deb && \
  rm influxdb_latest_amd64.deb && \
  rm -rf /var/lib/apt/lists/*

EXPOSE 8083 8086

CMD /usr/bin/influxdb

