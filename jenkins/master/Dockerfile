from jenkinsci/jenkins:latest

env JENKINS_USER admin
env JENKINS_PASS admin

run /usr/local/bin/install-plugins.sh git matrix-auth docker-workflow blueocean credentials-binding

# Skip the initial setup
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false
copy files/default-user.groovy /usr/share/jenkins/ref/init.groovy.d/

# Setup jenkins-job-builder
user root
run apt-get update && \
	apt-get install -y sudo curl python-pip libyaml-dev python-dev \
	&& rm -rf /var/lib/apt/lists/*
run echo "jenkins ALL=NOPASSWORD: ALL" >> /etc/sudoers
run git clone https://github.com/openstack-infra/jenkins-job-builder.git /jenkins-job-builder && \
	cd /jenkins-job-builder && pip install -e .
volume /etc/jenkins

