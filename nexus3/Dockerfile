FROM sonatype/nexus3:latest
MAINTAINER stuartgmilton@hotmail.com
COPY bash_functions configure_nexus /tmp/
WORKDIR /tmp
USER root
RUN curl -Is -vv https://www.bbc.co.uk && yum install -y --disableplugin=subscription-manager jq
USER nexus
RUN /opt/sonatype/nexus/bin/nexus start && \
    /tmp/configure_nexus && \
    /opt/sonatype/nexus/bin/nexus stop

