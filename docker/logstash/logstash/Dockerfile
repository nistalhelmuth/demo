ARG TAG_VERSION
FROM docker.elastic.co/logstash/logstash:${TAG_VERSION}
RUN rm -f /usr/share/logstash/pipeline/logstash.conf
RUN rm -f /usr/share/logstash/templates/custom-template.json
COPY config/logstash.conf /usr/share/logstash/pipeline/logstash.conf
COPY config/custom-template.json /usr/share/logstash/templates/custom-template.json
