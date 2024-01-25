SHELL=/bin/bash
.DEFAULT_GOAL := help

.PHONY: help
help:  ## shows the Makefile targets with information
ifeq ($(OS),Windows_NT)
	$(info ***** This target is not supported for windows *****)
else
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) |  awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
endif

IMAGE_NAME := dremio

.PHONY: login
login:  ## docker login to docker registry
	docker login

.PHONY: package
package: ## package
	helm package dremio_v2

.PHONY: publish
publish: package ## publish
	helm push $(IMAGE_NAME)-$(shell cat dremio_v2/Chart.yaml | yq -e ".version").tgz $(REGISTRY)