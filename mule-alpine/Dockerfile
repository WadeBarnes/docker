FROM alpine:3.2

RUN apk --update add openjdk8-jre openssl && mkdir /opt && adduser -D mule && chown mule /opt

ADD https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.8.0/mule-standalone-3.8.0.tar.gz /opt/

RUN chown mule /opt/mule-standalone-3.8.0.tar.gz

USER mule

WORKDIR /opt
RUN tar -xzvf /opt/mule-standalone-3.8.0.tar.gz

CMD /opt/mule-standalone-3.8.0/bin/mule