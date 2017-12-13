from ubuntu:latest

run apt-get -y update && \
    apt-get install -y python-all-dev python-pip build-essential && \
    pip install -U pip && \
    rm -rf /var/lib/apt/lists/* && \
    pip install ansible
run mkdir -p /etc/ansible
run echo '[local]\nlocalhost\n' > /etc/ansible/host
