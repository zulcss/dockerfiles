from ubuntu:latest

# install docker
run apt-get update
run apt-get -y install apt-transport-https ca-certificates curl lsb-release \
	software-properties-common
run curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
run apt-add-repository \
	"deb [arch=amd64] https://download.docker.com/linux/ubuntu \
	$(lsb_release -cs) \
	edge"
run apt-get update -y
run apt-get -y install docker-ce
