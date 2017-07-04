from ubuntu:16.04

run rm -rf /var/lib/apt/lists/ \
  && apt-get update \
  && apt-get install -y --no-install-recommends collectd collectd-utils \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/

copy data/collectd.conf /etc/collectd/collectd.conf

expose 25826

cmd ["/usr/sbin/collectd", "-C", "/etc/collectd/collectd.conf", "-f"]
