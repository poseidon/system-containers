DIR := $(abspath $(dir $(lastword $(MAKEFILE_LIST))))
VERSION=v1.13.4

LOCAL_REPO=poseidon/kubelet
IMAGE_REPO=quay.io/poseidon/kubelet

.PHONY: image
image:
	@buildah bud -t $(LOCAL_REPO):$(VERSION) .
	@buildah tag $(LOCAL_REPO):$(VERSION) $(LOCAL_REPO):latest

.PHONY: push
push:
	@buildah tag $(LOCAL_REPO):$(VERSION) $(IMAGE_REPO):$(VERSION)
	@buildah tag $(LOCAL_REPO):$(VERSION) $(IMAGE_REPO):latest
	@buildah push docker://$(IMAGE_REPO):$(VERSION)
	@buildah push docker://$(IMAGE_REPO):latest

validate:
	@jq . config.json.template
	@cp config.json.template config.json
	@-oci-runtime-tool validate
	@rm config.json
