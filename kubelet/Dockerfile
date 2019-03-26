FROM gcr.io/google_containers/hyperkube:v1.13.5

LABEL name="kubelet" \
  version="1.13.5" \
  release="0" \
  architecture="x86_v64" \
  atomic.type="system" \
  summary="Hyperkube Kubelet" \
  maintainer="Dalton Hubble <dghubble@gmail.com>"

COPY manifest.json service.template config.json.template /exports/
COPY start /usr/bin/start
CMD ["/usr/bin/start"]
