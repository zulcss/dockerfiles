from ubuntu

run apt-get update && \
    apt-get dist-upgrade && \
    apt-get install -y software-properties-common apt-transport-https

run apt-key adv  --keyserver keyserver.ubuntu.com --recv-keys 1484120AC4E9F8A1A577AEEE97A80C63C9D8B80B \
    && apt-add-repository "deb [arch=amd64] https://osquery-packages.s3.amazonaws.com/xenial xenial main"

run apt-get update && apt-get install -y osquery

cmd ["osqueryd", "--verbose"]
