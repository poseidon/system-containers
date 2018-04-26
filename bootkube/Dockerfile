FROM quay.io/coreos/bootkube:v0.12.0

LABEL name="bootkube" \
  version="0.12.0" \
  release="0" \
  architecture="x86_v64" \
  atomic.type="system" \
  summary="Bootstrap a Kubernetes cluster" \
  maintainer="Dalton Hubble <dghubble@gmail.com>"

COPY manifest.json service.template config.json.template /exports/
CMD ["/bootkube", "start", "--assets-dir=/var/lib/bootkube/assets"]
