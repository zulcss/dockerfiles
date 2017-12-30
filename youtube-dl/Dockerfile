from alpine

run set -xe \
    && apk add --no-cache ca-certificates \
                          ffmpeg openssl python3 \
    && pip3 install youtube-dl

workdir /data
entrypoint ["youtube-dl"]
cmd ["--help"]

