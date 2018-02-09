from ubuntu:latest

run set -e && \
    apt update && \
    apt -y dist-upgrade && \
    apt-get -y --no-install-recommends install curl apt-transport-https ca-certificates \
        software-properties-common && \
    curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - && \
    curl https://packages.microsoft.com/config/ubuntu/16.04/prod.list | \
        tee /etc/apt/sources.list.d/microsoft.list && \
    apt-get update && \
    apt-get -y install powershell

cmd ["/usr/bin/pwsh"]

