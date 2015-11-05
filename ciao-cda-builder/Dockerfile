# Docker container for ciao-cda-builder CIP
# Version 0.5
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-cda-builder zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-cda-builder/ws/target/ciao-cda-builder-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-cda-builder
RUN unzip ciao-cda-builder-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-cda-builder
# Standard ciao configuration file folder
VOLUME ["/root/.ciao/"]
# Jolokia Agent port
EXPOSE 8778
# Hazelcast Server port
EXPOSE 5701
# Entry point
ENTRYPOINT ["/opt/ciao-cda-builder/ciao-cda-builder-1.0.0-SNAPSHOT/run.sh"]