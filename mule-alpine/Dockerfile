FROM alpine:3.2

ADD https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.8.0/mule-standalone-3.8.0.tar.gz /opt/

RUN adduser -p mule
RUN chown mule /opt
USER mule

WORKDIR /opt
RUN tar -xzvf mule-standalone-3.8.0.tar.gz

CMD /opt/mule-standalone-3.8.0/bin/mule