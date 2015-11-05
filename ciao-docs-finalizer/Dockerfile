# Docker container for ciao-docs-finalizer CIP
# Version 0.3
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-docs-finalizer zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-docs-finalizer/ws/target/ciao-docs-finalizer-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-docs-finalizer
RUN unzip ciao-docs-finalizer-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-docs-finalizer
# Jolokia Agent port
EXPOSE 8778
# Hazelcast Server port
EXPOSE 5701
# Standard ciao configuration file folder
VOLUME ["/root/.ciao/"]
# Entry point
ENTRYPOINT ["/opt/ciao-docs-finalizer/ciao-docs-finalizer-1.0.0-SNAPSHOT/run.sh"]