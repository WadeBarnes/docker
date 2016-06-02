# Dockerfile for containerized Mule ESB
# Inspired by https://github.com/pr3d4t0r/muledocker/blob/master/Dockerfile
# Version:  mule-standalone-3.6.1 (community edition)
# Based on:  dockerfile/java (Trusted Java from http://java.com)

FROM                    FROM java:7

# Mule installation:
ADD                     https://repository.mulesoft.org/nexus/content/repositories/releases/org/mule/distributions/mule-standalone/3.6.1/mule-standalone-3.6.1.tar.gz /opt/
WORKDIR                 /opt
RUN                     tar -xzvf /opt/mule-standalone-3.6.1.tar.gz
#RUN                     ln -s mule-standalone-3.6.1 mule
# Remove things that we don't need in production:
RUN                     rm -f mule-standalone-3.6.1.tar.gz
RUN                     rm -Rf mule-standalone-3.6.1/apps/default*
RUN                     rm -Rf mule-standalone-3.6.1/examples

# Configure external access:

# Mule remote debugger
EXPOSE  5000

# Mule JMX port (must match Mule config file)
EXPOSE  1098

# Default port for HTTP endpoints in AnypointStudio
EXPOSE  8081
# Environment and execution:

ENV             MULE_BASE /opt/mule-standalone-3.6.1
WORKDIR         /opt/mule-standalone-3.6.1

CMD             /opt/mule-standalone-3.6.1/bin/mule
