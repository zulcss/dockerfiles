from alpine

run apk --no-cache add bash tinc && \
    apk --no-cache --update upgrade

expose 655/tcp 655/udp
volume /etc/tinc

entrypoint ["/usr/sbin/tincd"]
cmd ["start" "-D", "-U" "nobody"]
