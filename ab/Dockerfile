from ubuntu

run set -e && \
    apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y apache2-utils && \
    rm -rf /var/lib/apt/lists/*

entrypoint ["ab"]
