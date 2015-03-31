FROM yaronr/openjdk-7-jre:latest
MAINTAINER Raphael MESSNER

RUN wget https://grafanarel.s3.amazonaws.com/builds/grafana_2.0.0-beta1_amd64.deb && \
  dpkg -i grafana_2.0.0-beta1_amd64.deb && \
  rm grafana_2.0.0-beta1_amd64.deb && \
  rm -rf /var/lib/apt/lists/*

VOLUME ["/etc/grafana/grafana.ini"]

EXPOSE 3000

CMD /bin/bash
