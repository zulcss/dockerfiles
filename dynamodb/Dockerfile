from ubuntu:xenial

run set -e && \
    apt-get update && \
    apt-get -y dist-upgrade && \
    apt-get install -y openjdk-8-jdk curl && \
    rm -rf /var/lib/apt/lists/*

run mkdir -p /opt/dynamodb && \
    curl \
    https://s3-us-west-2.amazonaws.com/dynamodb-local/dynamodb_local_latest.tar.gz \
    -o /usr/src/dynamodb_local_latest.tar.gz && \
    tar -zxvf /usr/src/dynamodb_local_latest.tar.gz -C /opt/dynamodb

workdir /opt/dynamodb
expose 8000
ENTRYPOINT ["java", "-jar", "DynamoDBLocal.jar"]
