from ubuntu:latest

run apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install \
    --no-install-recommends \
	ruby-dev \
	build-essential \
	pkg-config \
    libxslt-dev \
    libxml2-dev \
    libvirt-dev \
    zlib1g-dev \
    libvirt-bin \
    openssh-client \
    libvirt-dev \
   && rm -rf /var/lib/apt/lists/*

env VAGRANT_VERSION 2.0.2

add https://releases.hashicorp.com/vagrant/${VAGRANT_VERSION}/vagrant_${VAGRANT_VERSION}_x86_64.deb /srv/vagrant_${VAGRANT_VERSION}_x86_64.deb

run dpkg -i /srv/vagrant_${VAGRANT_VERSION}_x86_64.deb && \
	vagrant plugin install vagrant-libvirt && \
    rm -f /srv/vagrant_${VAGRANT_VERSION}_x86_64.deb && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["vagrant"]
