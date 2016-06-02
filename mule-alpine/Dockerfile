FROM alpine:3.2

RUN  apk add --update openjdk7-jre
RUN mkdir /opt && adduser -D mule && chown mule /opt

ADD https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.8.0/mule-standalone-3.8.0.tar.gz /opt/

RUN chown mule /opt/mule-standalone-3.8.0.tar.gz

USER mule

WORKDIR /opt
RUN tar -xzvf /opt/mule-standalone-3.8.0.tar.gz

RUN rm -f /opt/mule-standalone-3.8.0/lib/boot/exec/wrapper-linux-x86-32

CMD /opt/mule-standalone-3.8.0/bin/mule