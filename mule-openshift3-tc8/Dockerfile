FROM registry.access.redhat.com/jboss-webserver-3/webserver30-tomcat8-openshift

USER root

ADD https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.8.0/mule-standalone-3.8.0.tar.gz /mule

RUN chown jboss /mule && chown jboss /mule/mule-standalone-3.8.0.tar.gz

USER jboss

WORKDIR /mule
RUN tar -xzvf mule-standalone-3.8.0.tar.gz

CMD /mule/mule-standalone-3.8.0/bin/mule