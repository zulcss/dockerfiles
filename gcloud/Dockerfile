from python:2.7.14-alpine3.7

run set -x \
    && apk update \
    && apk add curl ca-certificates tar \
    && curl -sSL -o /tmp/google-cloud-sdk.tar.gz \
        https://dl.google.com/dl/cloudsdk/release/google-cloud-sdk.tar.gz \
    && mkdir -p /usr/src/google-cloud-sdk \
    && tar -xzf /tmp/google-cloud-sdk.tar.gz -C /usr/src/google-cloud-sdk --strip-components 1 \
    && rm /tmp/google-cloud-sdk.tar.gz \
    && ( \
        cd /usr/src/google-cloud-sdk \
        && ./install.sh \
            --usage-reporting false \
            --path-update true \
        )

workdir /root
env PATH $PATH:/usr/src/google-cloud-sdk/bin

entrypoint ["/usr/src/google-cloud-sdk/bin/gcloud"]
