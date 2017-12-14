from ubuntu:latest

run apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install \
	ruby \
	ruby-dev \
	build-essential \
	pkg-config \
        libxslt-dev \
        libvirt-dev \
        ruby-fog \
        zlib1g-dev \
   && rm -rf /var/lib/apt/lists/*

env VAGRANT_VERSION 2.0.1

add https://releases.hashicorp.com/vagrant/${VAGRANT_VERSION}/vagrant_${VAGRANT_VERSION}_x86_64.deb /srv/vagrant_${VAGRANT_VERSION}_x86_64.deb

run dpkg -i /srv/vagrant_${VAGRANT_VERSION}_x86_64.deb && \
	vagrant plugin install vagrant-libvirt

ENTRYPOINT ["vagrant"]
