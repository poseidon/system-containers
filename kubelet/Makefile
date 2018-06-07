DIR := $(abspath $(dir $(lastword $(MAKEFILE_LIST))))
VERSION=v1.10.4

LOCAL_REPO=poseidon/kubelet
IMAGE_REPO=quay.io/poseidon/kubelet

all: docker-image

.PHONY: docker-image
docker-image:
	@sudo docker build --rm=true -t $(LOCAL_REPO):$(VERSION) .
	@sudo docker tag $(LOCAL_REPO):$(VERSION) $(LOCAL_REPO):latest

.PHONY: docker-push
docker-push: docker-image
	@sudo docker tag $(LOCAL_REPO):$(VERSION) $(IMAGE_REPO):latest
	@sudo docker tag $(LOCAL_REPO):$(VERSION) $(IMAGE_REPO):$(VERSION)
	@sudo docker push $(IMAGE_REPO):latest
	@sudo docker push $(IMAGE_REPO):$(VERSION)

validate:
	@jq . config.json.template
	@cp config.json.template config.json
	@-oci-runtime-tool validate
	@rm config.json
