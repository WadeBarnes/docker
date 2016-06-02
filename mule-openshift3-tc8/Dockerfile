FROM registry.access.redhat.com/jboss-webserver-3/webserver30-tomcat8-openshift 

ADD https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.8.0/mule-standalone-3.8.0.tar.gz
RUN tar -xvfz mule-standalone-3.8.0.tar.gz

#CMD mule-standalone-3.8.0/bin/mule