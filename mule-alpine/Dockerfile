FROM alpine:3.2

RUN apk --update add openjdk7-jre openssl
RUN wget https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.5.0/mule-standalone-3.5.0.tar.gz
RUN tar xvfz mule-standalone-3.5.0.tar.gz

#CMD mule-standalone-3.5.0/bin/mule