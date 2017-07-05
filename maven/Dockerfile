from ubuntu:latest

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
run export DEBIAN_FRONTEND=noniteractive && \
	apt-get update && \
	apt-get -y upgrade && \
	apt-get install -y vim wget curl git maven openjdk-8-jdk-headless

cmd ["/bin/bash"]
