FROM quay.io/coreos/etcd:v3.3.3

LABEL name="etcd" \
  version="3.3.3" \
  release="0" \
  architecture="x86_v64" \
  atomic.type="system" \
  summary="Distributed reliable key-value store" \
  maintainer="Dalton Hubble <dghubble@gmail.com>"

COPY manifest.json service.template config.json.template /exports/
COPY start /usr/bin/start
CMD ["/usr/bin/start"]
