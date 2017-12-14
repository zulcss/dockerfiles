from ubuntu:latest

run apt-get update && \
    apt-get -y dist-upgrade && \
    apt-get -y install git

env HELM_VERSION v2.7.2

add https://storage.googleapis.com/kubernetes-helm/helm-${HELM_VERSION}-linux-amd64.tar.gz /srv/helm-${HELM_VERSION}-linux-amd64.tar.gz

run tar zxvf /srv/helm-${HELM_VERSION}-linux-amd64.tar.gz -C /tmp && \
    mv /tmp/linux-amd64/helm /usr/local/bin/helm && \
    chmod +x /usr/local/bin/helm
