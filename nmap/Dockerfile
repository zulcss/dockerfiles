from ubuntu

run apt-get update && \
    apt-get install -y nmap --no-install-recommends \
    && rm -rf /var/lib/apt/lists/*

entrypoint ["nmap"]
