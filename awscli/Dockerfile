from alpine:latest

run set -e && \
    apk -Uuv add groff python py-pip && \
    pip install awscli && \
    rm /var/cache/apk/*

entrypoint ["aws"]
