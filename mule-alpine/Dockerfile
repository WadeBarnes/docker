FROM alpine:3.2

# 8.77.03-r0
ENV JAVA_VERSION_MAJOR 8
ENV JAVA_VERSION_MINOR 77
ENV JAVA_VERSION_BUILD 03
ENV JAVA_VERSION_REVIS r0

RUN echo '@edge http://nl.alpinelinux.org/alpine/edge/main' >> /etc/apk/repositories \
 && echo '@community http://nl.alpinelinux.org/alpine/edge/community' >> /etc/apk/repositories \
 && apk update && apk upgrade \
 && apk add openjdk8-jre-lib@community=${JAVA_VERSION_MAJOR}.${JAVA_VERSION_MINOR}.${JAVA_VERSION_BUILD}-${JAVA_VERSION_REVIS} \
 && apk add openjdk8-jre-base@community=${JAVA_VERSION_MAJOR}.${JAVA_VERSION_MINOR}.${JAVA_VERSION_BUILD}-${JAVA_VERSION_REVIS} \
 && rm -rf /var/cache/apk/*

ENV JAVA_HOME /usr/lib/jvm/java-1.8-openjdk/jre
ENV PATH ${PATH}:${JAVA_HOME}/bin

CMD ["java", "-version"]
RUN mkdir /opt && adduser -D mule && chown mule /opt

ADD https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.8.0/mule-standalone-3.8.0.tar.gz /opt/

RUN chown mule /opt/mule-standalone-3.8.0.tar.gz

USER mule

WORKDIR /opt
RUN tar -xzvf /opt/mule-standalone-3.8.0.tar.gz

CMD /opt/mule-standalone-3.8.0/bin/mule