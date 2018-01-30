from ubuntu:latest

run apt-get update && \
    apt-get -y dist-upgrade && \
    apt-get -y --no-install-recommends install git curl vim ca-certificates && \
    rm -rf /var/lib/apt/lists/* 

env HELM_VERSION v2.8.0

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

entrypoint ["helm"]
