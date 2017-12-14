from ubuntu:latest

run apt-get update && \
    apt-get -y dist-upgrade && \
    apt-get -y install git curl

env HELM_VERSION v2.7.2

# Install helm
add https://storage.googleapis.com/kubernetes-helm/helm-${HELM_VERSION}-linux-amd64.tar.gz /srv/helm-${HELM_VERSION}-linux-amd64.tar.gz
run tar zxvf /srv/helm-${HELM_VERSION}-linux-amd64.tar.gz -C /tmp && \
    mv /tmp/linux-amd64/helm /usr/local/bin/helm && \
    chmod +x /usr/local/bin/helm

workdir /srv
run curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
run mv /srv/kubectl /usr/local/bin
run chmod +x /usr/local/bin/kubectl
workdir /
