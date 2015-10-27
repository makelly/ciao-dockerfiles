# Docker container for ciao-transport-dts CIP
# Version 0.1
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-transport-spine zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-transport-dts/ws/target/ciao-transport-dts-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-transport-dts
RUN unzip ciao-transport-dts-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-transport-dts
# Jolokia Agent port
EXPOSE 8778
# Standard ciao configuration file folder
VOLUME ["/root/.ciao/"]
# Entry point
ENTRYPOINT ["/opt/ciao-transport-dts/ciao-transport-dts-1.0.0-SNAPSHOT/run.sh"]