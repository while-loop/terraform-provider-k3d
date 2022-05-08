VERSION			:= 0.0.6
REGISTRY_HOST	:= registry.terraform.io
PLUGIN_DIR		:= ${HOME}/.terraform.d/plugins/${REGISTRY_HOST}/pvotal-tech/k3d/${VERSION}/linux_amd64

default: testacc
.PHONY: testacc install-local

# Run acceptance tests
testacc:
	TF_ACC=1 go test ./... -v $(TESTARGS) -timeout 120m

install-local:
	go install
	mkdir -p ${PLUGIN_DIR}
	cp ${GOPATH}/bin/terraform-provider-k3d ${PLUGIN_DIR}
